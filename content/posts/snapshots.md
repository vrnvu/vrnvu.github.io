---
title: "snapshots, property and simulation testing"
date: 2025-10-21T00:02:00+00:00
comment: true
tags: ["code"]
---
Your test suite passes. Your coverage is 90%. You deploy to production. Your software breaks.

Traditional testing measures the wrong things. It counts lines of code covered, not bugs prevented. It tests components in isolation, not how they interact in the real world. It catches the bugs you expect, not the ones that actually matter.

You ship correctness bugs that unit tests never catch. The best way to avoid bugs is to [not write them in the first place](https://www.teamten.com/lawrence/programming/dont-write-bugs.html)—but when you do, you need tests that actually catch them.

Most developers think testing is about writing assertions on business rules. This is not the full picture. As mentioned in [this is ci](https://arnau.bearblog.dev/this-is-ci/), we need to validate correctness as well. [Assertions](https://arnau.bearblog.dev/invariants/) combined with the methods we are going to see are the tool for that.

- **Snapshot tests** catch API contract changes and fix tests automatically. 
- **Property tests** validate invariants, preconditions, and postconditions across thousands of random inputs.
- **Simulation tests** catch complex interactions that only appear under specific sequences of operations.

Together, they catch correctness bugs that traditional unit testing misses.

## Unit Tests Are Bad

The testing pyramid—with unit tests at the base—is fundamentally flawed. Unit tests give you false confidence because they test code in isolation, missing the complex interactions that cause real-world failures.

- **Isolated testing** misses integration bugs that only appear when components interact.
- **Mock-heavy tests** test your mocks, not your actual code.
- **High coverage** doesn't mean high quality—you can have 100% coverage and still ship correctness bugs.
- **False confidence** leads to deploying untested code paths.

As the [Testing on the Toilet](https://testing.googleblog.com/2007/01/introducing-testing-on-toilet.html) series emphasized, testing culture matters—but the wrong kind of testing gives false confidence. This aligns with the [analysis of unit vs integration tests](https://matklad.github.io/2022/07/04/unit-and-integration-tests.html): unit tests are fast but miss the interactions that cause real failures.

Focus on integration tests that encompass real-world scenarios and interactions. Test the system as a whole, not just individual pieces in isolation.

We need a good [testing methodology](https://matklad.github.io/2021/05/31/how-to-test.html), where the key is testing the right things at the right level—not just testing everything at the unit level.

## The Real Problem: Correctness is Hard

Correctness means your program cannot reach an impossible or invalid state—no matter what inputs or code paths are taken. Every piece of state in your program can be corrupted, overflowed, or misused.

**The three main sources of correctness violations:**
- **Type/Data Misusage:** Using data in ways that violate its intended purpose, like numeric overflow (e.g., `u8` wraps from 255 back to 0) or treating a string as a number, leading to logical errors or security vulnerabilities.
- **Out-of-Bounds Access:** Reading or writing outside array bounds causes undefined behavior and can crash your program or open security holes.
- **Reference Safety:** Dangling or null references cause pointer errors, crashes, or strange data corruption. Modern languages (like Rust) put correctness "rails" around reference usage.

**How we defend against these correctness problems:**
- **Invariants**—properties that must always be true at specific points in your program—like "all account balances must be non-negative" or "references never point to freed memory." Violate an invariant, and your program enters an impossible state.
- **Types** try to make certain invalid states unrepresentable, but most languages' types aren't strong enough to eliminate all possible incorrect states. An `int` type can't prevent accidental division by zero or ensure an array index is always valid.
- **Assertions** are runtime checks (e.g., `assert!(index < array.len())`) that enforce invariants the type system cannot represent.

As [this analysis](https://typesanitizer.com/blog/assertions.html) shows, assertions are crucial for catching correctness violations that types cannot prevent.

Snapshot, property, and simulation testing make invisible state changes, edge cases, and subtle invariant violations visible.

## Snapshot Testing

Snapshot testing captures the output of a function or component and compares it to a previously stored version to detect unintended changes. This is particularly powerful for API contract validation using tools like [insta](https://docs.rs/insta/latest/insta/) in Rust.

When APIs change their response format, your tests break even if the change is intentional. You need to manually update every test that checks the response structure, or your tests fail on every API evolution.

Consider an API that returns user data. Traditional testing requires manual maintenance when the API response changes:

```rust
#[test]
fn test_user_api_traditional() {
    let response = get_user(123);
    assert_eq!(response.status, 200);
    // Manual maintenance: update this when API adds fields
    assert_eq!(response.data.name, "John");
    assert_eq!(response.data.email, "john@example.com");
    // What happens when API adds response.data.last_login?
}
```

A snapshot test captures the entire response and compares it to a stored snapshot, automatically detecting any changes:

```rust
#[test]
fn test_user_api_as_snapshot() {
    let response = get_user(123);
    assert_eq!(response.status, 200);
    
    // Automatically detects any changes to the response structure
    insta::assert_snapshot!(response.data);
}
```

Snapshot tests automatically detect any changes to your API responses and let you review them before accepting. When you run tests, snapshot tools show you the exact differences and let you accept or reject changes, making API evolution explicit and intentional. This catches both intentional changes (which you can approve) and unintended changes (which you can reject). This approach is used extensively by companies like [Jane Street](https://blog.janestreet.com/testing-with-expectations/) for testing complex systems.

This aligns with the [risk-driven testing approach](https://googletesting-test.blogspot.com/2014/05/testing-on-toilet-risk-driven-testing.html), which emphasizes testing the areas that matter most for correctness.

## Property Testing

Property testing defines general properties or invariants that a function should satisfy, then generates a wide range of random inputs to verify these properties hold. This approach uncovers edge cases that traditional example-based testing misses, as demonstrated by [proptest](https://proptest-rs.github.io/proptest/) in Rust.

Human-written tests only cover the cases you think of. Property tests generate thousands of random inputs, finding edge cases you never considered.

Property tests generate thousands of random inputs, finding edge cases you never considered. Your payment system might work fine with amounts under $1000, but what happens with $2,147,483,647 (integer overflow)? Property tests find these correctness violations automatically.

**Example:** Testing a payment system with property tests using [proptest](https://proptest-rs.github.io/proptest/):

```rust
#[cfg(test)]
mod tests {
    use proptest::prelude::*;
    
    proptest! {
        #[test]
        fn test_payment_amount_properties(
            amount in 0..i32::MAX
        ) {
            let payment = Payment::new(amount);
            
            // Property: payment amount should never be negative
            prop_assert!(payment.amount() >= 0);
            
            // Property: payment should handle edge cases without overflow
            let doubled = payment.amount() * 2;
            prop_assert!(doubled >= payment.amount());
            
            // This will catch integer overflow with large numbers
            // like 2,147,483,647 (i32::MAX)
        }
    }
}
```

Property tests validate that your invariants hold across thousands of random operations, automatically finding edge cases that break your contracts. This technique is particularly effective when combined with [fuzz testing](https://github.com/rust-fuzz/cargo-fuzz) for comprehensive input validation.

Property tests catch bugs that only appear with specific input combinations—like integer overflow with large numbers or memory corruption with specific array sizes.

As [this bug analysis](https://typesanitizer.com/blog/bug-analysis.html) demonstrates, many correctness bugs only appear under specific input conditions that traditional testing misses.

## Simulation Testing

Simulation testing creates a model that mimics system behavior to test how it responds under various conditions. It extends property testing to complex sequences of operations, testing system behavior in scenarios difficult to reproduce in real-world testing, as described in [deterministic simulation testing](https://notes.eatonphil.com/2024-08-20-deterministic-simulation-testing.html).

Some bugs only appear under specific sequences of operations. A simple property test might miss the interaction between operations that causes the bug.

Generate random sequences of operations (add, remove, count, etc.), execute operations on both implementation and model, verify invariants hold after each operation, and test complex interaction patterns that simple property tests miss.

**Example:** Testing a bounded array with simulation testing:

```rust
#[cfg(test)]
mod tests {
    use proptest::prelude::*;
    
    proptest! {
        #[test]
        fn test_bounded_array_simulation(
            operations in prop::collection::vec(any::<Operation>(), 0..1000)
        ) {
            let mut array = BoundedArray::new(100);
            
            for op in operations {
                match op {
                    Operation::Push(item) => {
                        if !array.full() {
                            array.push(item);
                            // Property: count never exceeds capacity
                            prop_assert!(array.count() <= array.capacity());
                        }
                    }
                    Operation::Pop => {
                        if !array.empty() {
                            array.pop();
                            // Property: count never goes negative
                            prop_assert!(array.count() >= 0);
                        }
                    }
                }
            }
        }
    }
}
```

[TigerBeetle](https://tigerbeetle.com/blog/2025-02-13-a-descent-into-the-vortex/) uses simulation testing extensively to validate their database invariants under complex operation sequences. Their approach, detailed in [A Descent into the Vortex](https://tigerbeetle.com/blog/2025-02-13-a-descent-into-the-vortex/), demonstrates how simulation testing can catch bugs that traditional testing misses.

This approach addresses the [database testing challenges](https://calpaterson.com/against-database-teardown.html) of avoiding the complexity of database teardown while still testing real interactions.

Simulation tests catch complex bugs that only appear under specific sequences of operations. They're especially powerful for concurrent data structures where timing and order matter.

Simulation tests can run for hours, testing millions of operation combinations that would be impossible to test manually.

## How to Build Software That Doesn't Break

- **Snapshot tests** catch API changes and test logic. 
- **Property tests** catch invariants, precondition and postcondition errors.
- **Simulation tests** run complex interactions to cover a tree of possible states.

But the real power comes from combining them with assertions that make impossible states impossible:

```zig
pub fn push(array: *BoundedArray, item: T) void {
    assert(!array.full());  // Precondition
    array.buffer[array.count_u32] = item;
    array.count_u32 += 1;
    assert(array.count() == array.count_u32);  // Postcondition
}
```

Assertions make impossible states impossible. Tests make changes visible. Together, they create software that maintains correctness and doesn't break.

This approach aligns with the [error handling philosophy](https://typesanitizer.com/blog/errors.html): make errors impossible rather than just catching them after they occur.

## The Testing Methodology That Actually Works

Snapshot, property, and simulation testing don't just catch bugs—they make impossible states impossible. When combined with good CI and assertions, every change becomes visible, every assumption gets tested, and every deployment becomes predictable. Your code maintains correctness under all conditions.

- **CI** makes changes visible through failing tests.
- **Assertions** make impossible states impossible.
- **Advanced testing** catches complex scenarios that traditional testing misses.

You ship software that doesn't break. This is how companies like [TigerBeetle](https://www.amplifypartners.com/blog-posts/why-tigerbeetle-is-the-most-interesting-database-in-the-world) and [Jane Street](https://blog.janestreet.com/using-ascii-waveforms-to-test-hardware-designs/) build reliable systems at scale.