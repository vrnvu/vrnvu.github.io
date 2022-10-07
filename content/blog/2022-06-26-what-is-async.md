
+++
title = "what is async"
date = 2022-06-26
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

# What is async?

First of all if a function is a routine/subroutine, an async is a corrutine.

Second, basic context. In the main you have the main stack. The memory space allocated to execute a function where you put the local variables and parameters is a stack frame. In the stack you have variables and stack frames of the functions executing.

When you do a return of a function, you discard the stackframe from the main stack. You lose the local variables of that function.

In a coroutine you can `suspend` the execution. You return the control to where you were but without popping the stack. This is an `async` function.

Imagine the following code snippet, we have a `main` and a `foo` corroutine that I want to suspend.

```rust
1 main () {
2   foo()
3 }
4 foo() {
5   suspend 
6 }
```

I'm going to use the `async` keyword to indicate that `foo` will return us a pointer to the stackframe of the coroutine. This way from main you can return to where you were. Note that this behavior is normally only a convention, we could return more data about the coroutine if we wanted. And I'm going to use the `resume` keyword to indicate that I want to go back to the stackframe. Again, just some common syntax I invented.

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

1. You start by loading the main in LOC 1.
2. In your stack you have the execution line and the variables of the main and the frames...
3. In LOC 2 you invoke foo(), and you save the pointer to the frame.
4. You are in LOC 6 inside the stackfram of foo(), there you make a `suspend` call and you return the execution to the caller without popping the frame.
5. You are in LOC 3, there you `resume` the frame.
6. You are in LOC 7, now you make `return` of the 10 and pop the frame. 
7. Now you are in LOC 4, there if you would have saved the value in a varaible then you can use it normally... it is just another variable in the stack right?

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

And what about this one?

```rust
1 var global = 0
2 main () {
3   f = foo()
4   while (global != 3) {
5     resume f
6  }
7 foo() {
8   global++
9 }
```

Then you have the keyword `await`. It will wait in the main instead of following the execution... It doesn't have any secret... instead of following the code it waits for the frame to return... This is a perfect fit for IO tasks for example, sometimes we do some work in the background sometimes we await the response!

## Function coloring

OMG this topic... Okay.

Why do you need that the `async` things go with `async` and there are functions that can not be `async` as the main? Because if you are modifying memory and the code is executing it will come out to situations where you are pointing to uninitialized variables, if you don't do `await` and execute the code before the foo() that returned 2 at the end. What happens? it will print whatever you have in memory for the stack or pointer. Some things the compiler detects them as using the stack, but if you have an uninitialized pointer waiting for a value it will print garbage.

And at the end as you can see we are only using some pointers to execute the functions and coroutines. If you want to run it in one thread or in another... just write an scheduler! Whatever you need. As a conclusion I hope you understand that that parallelism has nothing to do with the coroutines.

## Blocking, non-blocking

A "normal" function the caller always waits for the return value. A corroutine, an `aync` function, the caller will only wait for the result if you wait. It has nothing to do with the `suspend` in the body if the caller has to block or not to block. It is the `await` that matters. Because waiting or not it is the caller who decides, `async` has nothing to do with blocking or non-blocking.

## Sync

Does sync means that the execution of one function goes after the previous? It doesn't have to actually. Depends on your runtime, you could load some pages and execute them in random order. And actually at low level there are a lot of situations where functions are executed out of order. 

## Scheduling for dummies

So coroutine, from "cooperative". It is a cooperative routine because it returns the execution. We have a `suspend` in the body!

If the scheduler can stop the execution from outside and give the CPU to another routine, then it would be a preemptive routine.  If it is not preemptive, the scheduler has to wait for the routine to finish and after its comletion it will start the new function.

If it is a cooperative routine, the coroutine can do a `suspend` and return control. That's why it's called "cooperative" because it allows the scheduler to take control if required. This is what we call preemptive cooperative scheduling.

