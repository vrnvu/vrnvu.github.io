
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

In a coroutine you can suspend the execution. You return the control to where you were but without popping the stack. This is an async function.

[code]
1 main () {
2   foo()
3 }
4 foo() {
5   suspend 
6 }
[/code] 