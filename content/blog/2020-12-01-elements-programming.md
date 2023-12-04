+++
title = "elements of programming"
date = 2020-12-01
draft = true
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
Elements of programming style. (1974)

Brian Kernighan and P.J Plauger
<!-- more -->

# Introduction

- **Write clearly - don't be to clever.**


# Expression

- **Say what you mean, simply and directly.** Explicit. Intention. 

- **Use library functions.** Don't re-invent the wheel. Copy. Even better. Steal. Good artist copy, genius steal.

- **Avoid temporary variables.** Avoid mutable data structures when it makes sense.

- **Write clearly - don't sacrifice clarity for "efficiency".** Benchmark.

- **Let the machine do the dirty work.** Computers are fast. More than you think.

- **Replace repetitive expressions by calls to a common function.** But don't add abstractions you won't need.

- **Parenthesize to avoid ambiguity.** Rename, rewrite.

- **Choose variable names that won't be confused.**

- **Avoid unnecessary branches.** Algorithmic design code smell.

- **Use the good features of a language; avoid the bad ones.** Use the right tool for the job. Don't use conditional branches as a substitue for a logical expression. Think in expressions. Write with expressions. Always. 

# Control structure

- **Delimit group of statements.** Consisteny. 

- **Use IF-ELSE to emphasize that only one of two actions is to be performed.**

- **Use DO and DO-WHILE to emphasize the presence of loops.**

- **Make your programs read from top to bottom.**

- **Use the fundamental control flow constructs.**


- **Write first in an easy-to-understand pseudo-language; then translate into whatever language you have to use.** Paper first. 

- **Avoid THEN-IF and null ELSE.**

- **Avoid ELSE GOTO and ELSE RETURN.**

- **Follow each decision as closely as opssible with its associated action.**

- **Use data arrays to avoid repetitive control sequences.**

- **Choose a data representation that makes the program simple.** Data oriented programming. Data first. Data moves your code.

- **Don't stop with your first draft.** Forth philosophy. Thinking Forth.

# Program structure

- **Modularize. Use subroutines.** Write cohesive. Build languages. Extend your program as needed.

- **Make the coupling between modules visible.** Port. Adapter.

- **Each module should do one thing well.** One thing.

- **Make sure every module hides something.** It's not about what you hide. It's more about what rules you expose. An interface is a contract.

- **Let the data structure the program.**

Data first.

- **Don't patch bad code - rewrite it.** Opportunistic programming. A program evolves. Always keep it in mind.

- **Write and test a big program in small pieces.** You don't write test to check if it works. You write it assert it won't break.

- **Use recursive procedures for recursively-defined data structures.**

# Input and output

- **Test input for validity and plausiblity** Don't validate. Parse. Use your type system.

- **Make sure input cannot violate the limits of the program.**

- **Terminate input by end-of-file or marker, not by count.**

- **Identify bad input; recover if possible.** If your code can recover it's well written. 

- **Treat end of file conditions in a uniform manner.**

- **Make input easy to prepare and output self-explanatory.**

- **Use uniform input formats.**

- **Make input easy to proofread.**

- **Use self-identifying input. Allow defaults. Echo both on output.**

- **Localize input and output in subroutines.** Limit side effects in the process.

# Common blunders

- **Make sure all variables are initialized before use.**

- **Don't stop at one bug.**

- **Use debuggin compilers.** Invest in your environment.

- **Initialize constants with DATA statements or INITIAL attributes; initialize variable with executable code.**

- **Watch out for off-by-one errors.**

- **Take care to branch the right way on equality.**

- **Avoid multiple exits from loops.** Algorithmic design code smell.

- **Make sure your code "does nothing" gracefully.**

- **Test programs at their boundary values.**

- **Program defensively.**

- **10.0 times 0.1 is hardly ever 1.0.**

# Efficiency

- **Make it right before you make it faster.** You probably won't ever need to make everything faster.

- **Keep it right when you make it faster.**

- **Make it clear before you make it faster.** Requirements will change anyway.

- **Don't sacrifice clarity for small gains in "efficiency".** You don't even know what a GC is.

- **Let your compiler do the simple optimizations.** Help the compiler. Smaller chunks of code usually help.

- **Don't strain to re-use code; reorganize instead.** Don't add complexity. Don't add unnecesarry abstractions.

- **Make sure special cases are truly special.**

- **Keep it simple to make it faster.**

- **Don't diddle code to make it faster - find a better algorithm.** Algorithmic design code smell.

- **Instrument your programs. Measure before makign "efficiency" changes.** Code so it's easy to test. Code so it's easy to benchmark.


# Documentation

- **Make sure comments and code agree.** Use your type system. Use auto generated docs. 

- **Make every comment count.**

- **Don't comment bad code. Rewrite it.**

- **Use variable names that mean something.**

- **Format a program to help a reader understand it.** Explain the why.

- **Indent to show the logical structure of a program.**

- **Document your data layouts.**

- **Don't over comment.**
