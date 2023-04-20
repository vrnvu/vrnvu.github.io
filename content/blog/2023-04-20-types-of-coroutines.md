+++
title = "types of coroutines"
date = 2023-04-20
draft = false

[taxonomies]
categories = ["programming"]
tags = ["programming"]

[extra]
lang = "en"
toc = true
show_comment = true
math = false
mermaid = false
+++
---

# Types of coroutines

Coroutines have been used in programming since 1958 and were defined by Knuth as a way to generalize a subroutine. While regular subroutines start at the beginning and end at the end, coroutines can pause their execution and resume later from where they left off. An explanation of this can be found [here](https://arnaudiaz.com/blog/what-is-async/).

The topic is complex because we normally mix "what a coroutine is" with "how it is going to run".

There are two common ways to use coroutines: 

- **stackless**, where the code is transformed into a state machine by the compiler.
- **stackful**, also known as fibers, which are user-mode threads that run on top of a regular operating system thread.

We can identify two types of coroutines based on their need for a stack:

- **stackless**, only require a stack while the coroutine is running. Once the coroutine suspends, its local variables can be serialized into a fixed-size structure, and the current call stack can be used for executing the next coroutine.
- **stackful**, allows you to suspend your coroutines at any point, providing more flexibility than stackless coroutines.

The lack of a stack is what allows the compiler to transform and use a stackless coroutine, while the need for a stack requires a runtime.