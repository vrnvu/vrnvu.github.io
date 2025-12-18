---
title: "writing hard things"
date: 2025-11-09T00:00:00+00:00
comment: true
tags: ["code"]
---

I've worked on hard problems: implemented AI papers, optimized backend services, troubleshot networking issues in production, databases. Some for work, some for fun.

Building hard things gives you **understanding** and **skills**. Everyone talks too much about understanding. Nobody talks enough about skills. If you don't build hard things, you won't know these skills exist. You won't learn them.

Understanding:

> What I cannot create I don't understand! - Richard Feynman

Skills:

> Know how to solve every problem that has been solved. - Richard Feynman

Write hard things. Build a VM from scratch. Write a compiler. Implement a database. These projects teach you skills you won't develop any other way.


## Easy advice

Most programming advice targets simple and easy problems. This advice will fail.

Try applying "keep functions small" to a complex concurrent and parallel [state machine](https://raft.github.io/raft.pdf). Try applying "use design patterns" when you're optimizing for cache locality. Try applying "write tests first" when you don't know [how to solve](https://en.wikipedia.org/wiki/How_to_Solve_It) the problem yet. It doesn't work.

Traditional unit testing doesn't work for distributed systems or databases. You need [formal methods](https://groups.csail.mit.edu/tds/papers/Lynch/Lifetime_Contributions_Book-1.pdf), [deterministic simulation testing](https://notes.eatonphil.com/2024-08-20-deterministic-simulation-testing.html), [OS-level fault injection](https://antithesis.com), and [deep analysis](https://jepsen.io) that validate correctness.

["Clean code"](https://www.computerenhance.com/p/clean-code-horrible-performance) abstractions that help with simple problems become performance bottlenecks in systems programming. A memory allocator isn't "clean." It can be hard, dirty, and ugly. It has pointer arithmetic, bit manipulation, low-level operations. But it can be [readable](https://arnaudiaz.com/posts/code-readibility/). The code shows what it does, why it does it, what invariants it maintains.

Simplifying a paper is difficult. Implement it first as you understand it. Write tests and benchmarks. Compare it to alternatives. Prove it. Iterate on the [invariants and properties](https://arnaudiaz.com/posts/invariants/) until you minimize them to a successful local minimum. Then simplify by removing state, improving efficiency or performance. If you reach this point, congratulations! You've achieved a new state of the art result for your field. Publish it.

And more: [Workflows](https://temporal.io), manual memory management, concurrency runtimes, network protocols. Writing public APIs for widely adopted tools, debugging and performance tracing. These hard problems need different skills.

## Hard advice

You can't understand it without implementing it. You can't simplify it without first making it work. You can't test without knowing what correctness means and how to test reliably. You need to profile and debug. You may need to read assembly and target different CPU architectures. You may need to open a math book.

- **Code**. [Algorithms](https://courses.csail.mit.edu/6.006/fall11/notes.shtml), [CodeForces](https://codeforces.com/blog/entry/125210), [Competitive programming](https://cses.fi/book/index.php), [Project Euler](https://projecteuler.net).
- **Study**. [Databases](https://15445.courses.cs.cmu.edu/fall2025/), [Distributed Systems](https://pdos.csail.mit.edu/6.824/schedule.html), [OS](https://pdos.csail.mit.edu/6.1810/2024/schedule.html).
- **Hack**. [Hack](https://www.catb.org/~esr/faqs/hacker-howto.html) PyTorch, React, Kubernetes, Postgres, Kafka...
- **Write**. Start a blog, share guides, what you learned, help your teammates.

Write hard things.