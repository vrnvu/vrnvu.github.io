---
title: "invariants"
date: 2025-10-21T00:00:00+00:00
comment: true
tags: ["code"]
---

# making impossible states impossible

Last week, a race condition crashed production at 3 AM. The bug was impossible to reproduce in development, but a single assertion would have caught it immediately. This is why assertions exist: they make impossible states impossible.

Some developers think assertions are just debugging tools. Not true. Assertions are contracts that prevent your code from reaching invalid states. Without assertions, bugs hide in impossible states. With assertions, impossible states become impossible. When combined with good [CI](https://arnau.bearblog.dev/this-is-ci/), every change becomes visible, every assumption gets tested, and every deployment becomes predictable. As [this analysis](https://typesanitizer.com/blog/assertions.html) shows, assertions are crucial for catching correctness violations that types cannot prevent.

- **precondition:** condition that must be met just before executing a block of code.  
- **postcondition:** condition that must always be met just after executing a block of code.  
- **invariant:** something that doesn't change during a block of code when applying a set of transformations.

### Preconditions

Consider a payment processor that can only be enabled when disabled, and disabled when enabled. Without assertions, you get subtle bugs that are impossible to reproduce in development but crash production:

```
@dataclass
class StateManager:
    state: bool = False
    
    def enable(self) -> None:
        assert self.state == False, "Cannot enable: state must be False"
        self.state = True
    
    def disable(self) -> None:
        assert self.state == True, "Cannot disable: state must be True"
        self.state = False
```

This simple example demonstrates the power of preconditions:
- We reduced our tree of states and transitions to only valid ones
- Test coverage improved because we eliminated invalid state combinations
- We can do simulations and fuzzy testing without worrying about invalid preconditions
- Concurrency errors and race conditions become immediately visible
- We can add postconditions to complete the contract

### Why Assertions Over Types

Type systems catch some errors at the cost of some overhead. Assertions catch the impossible and act as railways for programmers: they guide you to correct code and prevent you from going off track. We can use types for business rules, but programming correctness is best expressed with assertions. When your code reaches a state it should never reach, better to panic than continue executing incorrectly. Why would your program be in an invalid state?

Assertions work in any language. Type systems don't. Assertions catch runtime errors that types miss. Most importantly, assertions make your assumptions explicit and testable. This approach aligns with the [error handling philosophy](https://typesanitizer.com/blog/errors.html): make errors impossible rather than just catching them after they occur.

Use both.

### Advanced Concepts

Preconditions are just the beginning. Postconditions and invariants require deeper understanding of your domain, algorithms, and system constraints. But they enable greater correctness in complex scenarios: concurrency, race conditions, dynamic environments, and distributed systems.

**Postconditions** establish contracts between functions and their callers. Sometimes preconditions alone aren't enough to catch invalid results.

**Invariants** ensure properties hold throughout code execution, especially useful in algorithms and data structures. Combined with system constraints (CPU, memory, networking), they help detect errors and resource leaks.

### Invariants

Invariants ensure properties hold throughout execution. Useful in algorithms and data structures, especially when combined with system constraints:

- Static memory allocation: no malloc, everything pre-allocated
- Algorithm bounds: all values positive, checked each iteration to prevent overflows  
- Logical implications: [if-then relationships](https://tigerbeetle.com/blog/2025-05-26-asserting-implications/) that must hold

### Postconditions

Postconditions establish the other half of the function contract. Having both pre- and postconditions creates a complete specification:

```
processed := process(numbers)
assert len(processed) > 0 # postcondition

def process(numbers):
  assert len(numbers) > 0 # precondition
```

This [contract-based approach](https://tigerbeetle.com/blog/2023-12-27-it-takes-two-to-contract/) makes impossible states impossible and catches bugs that preconditions alone miss. As [this bug analysis](https://typesanitizer.com/blog/bug-analysis.html) demonstrates, many correctness bugs only appear under specific conditions that traditional testing misses.