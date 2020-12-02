---
layout: post
title: Epoche on elements of programming style
slug: epoche-on-elements
---

Elements of programming style. (1978)

Brain Kernighan and P.J Plauger

---
{: data-content="Introduction"}

> Write clearly - don't be to clever.

---
{: data-content="Expression"}

> Say what you mean, simply and directly.

Explicit. Intention. 

> Use library functions.

Don't re-invent the wheel. Copy. Even better. Steal. Good artist copy, genius steal.

> Avoid temporary variables.

Avoid mutable data structures when it makes sense.

> Write clearly - don't sacrifice clarity for "efficiency".

Never.

> Let the machine do the dirty work.

Computers are fast. More than you think.

> Replace repetitive expressions by calls to a common function.

But don't add abstractions you won't need.

> Parenthesize to avoid ambiguity.

Rename, rewrite.

> Choose variable names that won't be confused.


> Avoid unnecessary branches.

Algorithm design code smell.

> Use the good features of a language; avoid the bad ones.

Use the right tool for the job.

> Don't use conditional branches as a substitue for a logical expression.

Think in expressions. Write with expressions. Always.

---
{: data-content="Control structure"}

> Delimit group of statements.

Consisteny. 

> Use IF-ELSE to emphasize that only one of two actions is to be performed.

> Use DO and DO-WHILE to emphasize the presence of loops.

> Make your programs read from top to bottom.

> Use the fundamental control flow constructs.

> Write first in an easy-to-understand pseudo-language; then translate into whatever language you have to use.

> Avoid THEN-IF and null ELSE.

> Avoid ELSE GOTO and ELSE RETURN.

> Follow each decision as closely as opssible with its associated action.

> Use data arrays to avoid repetitive control sequences.

> Choose a data representation that makes the program simple.

> Don't stop with your first draft.

---
{: data-content="Program structure"}

> Modularize. Use subroutines.

> Make the coupling between modules visible.

> Each module should do one thing well.

> Make sure every module hides something.

> Let the data structure the program.

> Don't patch bad code - rewrite it.

> Write and test a big program in small pieces.

> Use recursive procedures for recursively-defined data structures.

---
{: data-content="Input and output"}

> Test input for validity and plausiblity

> Make sure input cannot violate the limits of the program.

> Terminate input by end-of-file or marker, not by count.

> Identify bad input; recover if possible.

> Treat end of file conditions in a uniform manner.

> Make input easy to prepare and output self-explanatory.

> Use uniform input formats.

> Make input easy to proofread.

> Use self-identifying input. Allow defaults. Echo both on output.

> Localize input and output in subroutines.

---
{: data-content="Common blunders"}

> Make sure all variables are initialized before use.

> Don't stop at one bug.

> Use debuggin compilers.

> Initialize constants with DATA statements or INITIAL attributes; initialize variable with executable code.

> Watch out for off-by-one errors.

> Take care to branch the right way on equality.

> Avoid multiple exits from loops.

> Make sure your code "does nothing" gracefully.

> Test programs at their boundary values.

> Program defensively.

> 10.0 times 0.1 is hardly ever 1.0.

---
{: data-content="Efficiency and insturmentation"}

> Make it right before you make it faster.

> Keep it right when you make it faster.

> Make it clear before you make it faster.

> Don't sacrifice clarity for small gains in "efficiency".

> Let your compiler do the simple optimizations.

> Don't strain to re-use code; reorganize instead.

> Make sure special cases are truly special.

> Keep it simple to make it faster.

> Don't didle code to make it faster - find a better algorithm.

> Instrument your programs. Measure before makign "efficiency" changes.


---
{: data-content="Documentation"}

> Make sure comments and code agree.

> Make every comment count.

> Don't comment bad code. Rewrite it.

> Use variable names that mean something.

> Format a program to help a reader understand it.

> Indent to show the logical structure of a program.

> Document your data layouts.

> Don't over comment.

