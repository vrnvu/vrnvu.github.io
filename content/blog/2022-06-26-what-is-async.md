
+++
title = "what is async"
date = 2022-06-26
draft = false
authors = ["arnau"]

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

# What is async?

To start, if a function is a routine or a subroutine, then an async function is a coroutine.

In the main program, there is a main stack that contains the memory space allocated to execute a function. This space is called a stack frame, and it stores local variables and parameters. The stack also contains the variables and stack frames of the functions being executed.

When you return from a function, you get rid of the stack frame from the main stack, and you lose the local variables of that function.

In a coroutine, you can pause the execution and return control to where you were before without removing anything from the stack. This is an `async` function.

Let's consider this code snippet, which includes a `main` function and a `foo` coroutine that you can pause.


```rust
1 main () {
2   foo()
3 }
4 foo() {
5   suspend 
6 }
```

We can use the `async` keyword to indicate that `foo` will give us a pointer to the stack frame of the coroutine. This allows us to return to where we were in the main function. Keep in mind that this behavior is only a convention, and we could return additional data about the coroutine if we wanted to. Similarly, we can use the `resume` keyword to indicate that we want to return to the stack frame. It's worth noting that this is a syntax convention that I've created.

```rust
1 main () {
2   f = async foo()
3   resume f()
4 }
5 foo() {
6   suspend 
7   return 10
8 }
```

1. Begin by loading the main function at LOC 1.
2. The stack contains the execution line and the variables of the main function and its frames.
3. At LOC 2, call the `foo()` function and save the pointer to the frame.
4. At LOC 6, you are inside the stack frame of `foo()`, where you make a `suspend` call and return execution to the caller without popping the frame.
5. At LOC 3, you `resume` the frame.
6. At LOC 7, you `return` the value 10 and pop the frame.
7. Now you are at LOC 4. If you had saved the value in a variable, you could use it normally. After all, it's just another variable in the stack, right?

How does the following example work? What does it print?

```rust
1 main () {
2   f = async foo()
3   v = resume f()
4   print(v)
5 }
6 foo() {
7   suspend 
8   return 10
9 }
```

And what about this one? What does it print?

```rust
1 var global = 0
2 main () {
3   f = foo()
4   while (global != 3) {
5     resume f
6   }
7   print(global)
8 }
9 foo() {
10   while (1) {
10     global++
11     suspend
12  }
13}
```

The `await` keyword causes the program to wait in the main function instead of continuing with the execution. There's nothing mysterious about it, it simply waits for the frame to return. This makes it ideal for IO tasks, where you may need to wait for a response. For example, you might do some work in the background and then await the response.

## Function coloring

The reason that `async` functions need to go with async is that when managing memory, there can be situations where you have uninitialized variables. If you execute code before the `await` and after the `async` function, it could print garbage because there are uninitialized pointers waiting for a value. Sometimes the compiler can detect this, but other times it can't.

It's worth noting that we're just using pointers to execute the functions and coroutines. This means that you can run them in any thread or scheduler you need, depending on your requirements.

In conclusion, **it's important to understand that coroutines have nothing to do with parallelism**. They are simply a way to manage memory and handle IO tasks in an efficient and elegant way.

## Blocking, non-blocking

In a subroutine, the caller always waits for the return value. However, with coroutines and `async` functions, the caller only waits for the result if they use the `await` keyword. The use of `suspend` in the function body doesn't determine whether the caller has to block or not.

**The decision to wait or not is up to the caller**, and whether a function is `async` or not doesn't determine whether it blocks or is non-blocking. Instead, it's the use of `await` that matters in determining whether a caller needs to block or not.

## More

This post was an introduction with some inaccuracies. Read [this](https://arnaudiaz.com/blog/types-of-coroutines/) for more.