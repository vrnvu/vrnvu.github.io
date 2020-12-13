---
layout: post
title: Epoche on forth elegance
slug: epoche-on-forth-elegance
---

# Thinking Forth

> Everything old is new again. There are no new ideas. Modern software development is not so modern. 

# Elegance

## An armchair history of software elegance

### Memorability 

The first computer programs looked something like this:

```
00110101
11010011
11011001
```

Programmers entered these programs by setting rows of switches—“on” if the digit was “1,” “oﬀ” if the digit was “0.” These values were the “machine instructions” for the computer, and each one caused the computer to perform some mundane operation like “Move the contents or Register B to Register A,” or “Add the contents of Register C into the contents of Register A.” 

Some clever programmers realized that the computer itself could be used to help. so they wrote a program that translated easy-to-remember abbreviations into the hard-to-remember bit patterns. The new language looked something like this:

```
MOV B,A
ADD C,A
JMC REC1
```

The translator program was called an **assembler**, the new language assembly language. Each instruction “assembled” the appropriate bit pattern for that instruction, with a **one-to-one** correspondence between assembly instruction and machine instruction. But names are easier for programmers to remember. For this reason the new instructions were called mnemonics.

### Power

In practice, programmers found themselves often repeating the same sequence of instructions over and again to accomplish the same thing in diﬀerent parts of the program. How nice it would be to have a name which would represent each of these common sequences.

This need was met by the “macro assembler,” a more complicated assembler that could recognize not only normal instructions, but also special names (“macros”). For each name, the macro assembler assembles the ﬁve or ten machine instructions represented by the name, just as though the programmer had written them out in full.

### Abstraction

A major advance was the invention of the “high-level language.” Again this was a translator program, but a more powerful one. High-level languages make it possible for programmers to write code like this:


```
X = Y (456/A) - 2
```

### Manageability

Most computer programs involve much more than lists of instructions to work down from start to ﬁnish. They also involve testing for various conditions and then “branching” to the appropriate parts of the code depending upon the outcome. They also involve “looping” over the same sections of code repeatedly, usually testing for the moment to branch out of the loop.

### Modularity

A signiﬁcant advance arose with the invention of **“Structured Programming,”** a methodology based on the observation that large problems are more easily solved if treated as collections of smaller problems [^1]. Each piece is called a module. Programs consist of modules within modules.

Structured programming eliminates spaghetti coding by insisting that control ﬂow can be diverted only within a module. You can’t jump out from the middle of one module into the middle of another module.

### Writeability

Yet another breakthrough encouraged the use of structured programs: structured programming languages. These languages include control structures in their command sets, so you can write programs that have a more modular appearance.

Structured programming languages include control structure operators such as IF and THEN to ensure a modularity of control ﬂow.

### Designing from the top

How does one go about designing these modules? A methodology called “topdown design” proclaims that modules should be designed in order starting with the most general, overall module and working down to the nitty-gritty modules. 

> Write no code until you have planned every last detail.

### Subroutines

All high-level programming languages incorporate techniques that allow modules of design to be coded as modules of code—discrete units that can be given names and “invoked” by other pieces of code. These units are called **subroutines**, **procedures**, or **functions**, depending on the particular high-level language and on how they happen to be implemented.

When the subroutine has ﬁnished being executed, control returns back to the calling program at the point following the call. Subroutines obey the rules of structured programming. 

### Successive refinement
 
The idea [^2] is that you begin by writing a skeletal version of your program using natural names for procedures for data structures. Then you write versions of each of the named procedures. You continue this process to greater levels of detail until the procedures can only be written in the computer language itself. 

At each step the programmer must make decisions about the algorithms being used and about the data structures they’re being used on. Decisions about the algorithms and associated data structures should be made in parallel. 

If an approach doesn’t work out the programmer is encouraged to back track as far as necessary and start again. 

Notice this about successive reﬁnement: You can’t actually run any part of the program until its lowest-level components are written. Typically this means you can’t test the program until after you’ve completely designed it. 

Also notice: Successive reﬁnement forces you to work out all details of control structure on each level before proceeding to the next lower level.

### Structured design

By the middle of late ’70s, the computing industry had tried all the concepts we’ve described, and it was still unhappy. The cost of maintaining software— keeping it functional in the face of change—accounted for more than half of the total cost of software, in some estimates as much as ninety percent!

About this time a new philosophy arose, described in an article called “Structured Design” [^3]. One of its principles is stated in this paragraph:

> Simplicity is the primary measurement recommended for evaluating alternative designs relative to reduced debugging and modiﬁcation time. Simplicity can be enhanced by dividing the system into separate pieces in such a way that pieces can be considered, implemented, ﬁxed and changed with minimal consideration or eﬀect on the other pieces of the system.

By dividing a problem into simple modules, programs were expected to be **easier to write, easier to change, and easier to understand**. But what is a module, and on what basis does one make the divisions? “Structured Design” outlines three factors for designing modules.

### Functional strength

A measure of the uniformity of purpose of all the statements within a module. If all the statements inside the module collectively can be thought of as performing a single task, they are functionally bound.

1. Does the description have to be a compound sentence?
2. Does it use words involving time, such as “ﬁrst”, “next”, “then,” etc.? 
3. Does it use a general or nonspeciﬁc object following the verb? 
4. Does it use words like “initialize” which imply a lot of different functions being done at the same time?

If the answer to any of these four questions is “yes,” you’re looking at some less cohesive type of binding than functional binding. Weaker forms of binding include:

- **Coincidental binding**: (the statements just happen to appear in the same module)
- **Logical binding**: (the module has several related functions and requires a ﬂag or parameter to decide which particular function to perform) 
- **Temporal binding**: (the module contains a group of statements that happen at the same time, such as initialization but have no other relationship) 
- **Communicational binding**: (the module contains a group of statements that all refer to the same set of data)
- **Sequential binding**: (where the output of one statement serves as input for the next statement

### Coupling

A measure of how modules inﬂuence the behavior of other modules. Strong coupling is considered bad form. The worst case is when one module actually modiﬁes code inside another module. Even passing control ﬂags to other modules with the intent to control their function is dangerous. 

### Information-Hiding

In a paper [^4] published back in 1972, Dr. David L. Parnas showed that the criteria for decomposing modules should not be steps in the process, but rather pieces of information that might possibly change. Modules should be used to hide such information.

## The superficiality of structure

Parnas proposes two criteria for decomposition:

1. possible (though currently unplanned) reuse, and 
2. possible (though unplanned) change.

This new view of a “module” is different than the traditional view. This “module” is a collection of routines, usually very small, which together hide information about some aspect of the problem.

Two other writers describe the same idea in a diﬀerent way, using the term “data abstraction” [^5].

The word uses plays an important role in this concept.

> Systems that have achieved a certain “elegance”... have done so by having parts of the system use other parts...
> If such a hierarchical ordering exists then each level oﬀers a testable and usable subset of the system...
> The design of the “uses” hierarchy should be one of the major milestones in a design eﬀort. The division of the system into independently callable subprograms has to go in parallel with the decisions about uses, because they inﬂuence each other.

## Component programming

Having a larger set of simpler words makes it easy to use a technique we’ll call “component programming.” To explain, let’s ﬁrst reexamine these collections we have vaguely described as “things that may change.” 

- The **question** is: “How can we minimize the impact of any such change? What is the smallest set of other things that must change along with such a change?” 
- The **answer** is: “The smallest set of interacting data structures and algorithms that share knowledge about how they collectively work.” We’ll call this unit a “component.” 

![component-programming](./assets/forth/forth0.PNG)

The figure contrasts the results of structured design with the results of designing by components. Instead of modules called READ-RECORD, EDIT-RECORD, and WRITE-RECORD, we’re concerned with components that describe the structure of records, provide a set of editor commands, and provide read/write routines to storage. 

What have we done? We’ve inserted a new stage in the development process: We decomposed by components in our design, then we described the sequence, hierarchy, and input-process-output in our implementation. Yes, it’s an extra step, but we now have an extra dimension for decomposition—not just slicing but dicing.

Suppose that, after the program is written, we need to change the record structure. In the sequential, hierarchical design, this change would aﬀect all three modules. In the design by components, the change would be conﬁned to the record-structure component. No code that uses this component needs to know of the change. 

Aside from maintenance, an advantage to this scheme is that programmers on a team can be assigned components individually, with less interdependence. The principle of component programming applies to team management as well as to software design. We’ll call the set of words which describe a component a "lexicon".

In this book, the term “lexicon” refers only to those words of a component that are used by name outside of a component. A component may also contain deﬁnitions written solely to support the externally visible lexicon. We’ll call the supporting deﬁnitions “internal” words. 

The lexicon provides the logical equivalents to the data objects and algorithms in the form of names. The lexicon veils the component’s data structures and algorithms—the “how it works.” It presents to the world only a “conceptual model” of the component described in simple words—the “what it does.” 

These words then become the language for describing the data structures and algorithms of components written at a a higher level. The “what” of one component becomes the “how” of a higher component. 

## Hide from whom?

The newest traditional languages bend over backwards to ensure that modules hide internal routines and data structures from other modules. The goal is to achieve module independence (a minimum coupling). The fear seems to be that modules strive to attack each other like alien antibodies. Or else, that evil bands of marauding modules are out to clobber the precious family data structures.

This is **not** what we’re concerned about. The purpose of hiding information, as we mean it, **is simply to minimize the effects of a possible design-change by localizing things that might change within each component**. 

---
{: data-content="footnotes"}

[^1]: *O.J. Dahl, E.W. Dijkstra, and C.A.R. Hoare, Structured Programming, London, Academic Press, 1972.* [strctured-programming](https://dl.acm.org/doi/book/10.5555/1243380) 
[^2]: *Niklaus Wirth, “Program Development by Stepwise Reﬁnement,” Communications of ACM, 14, No. 4 (1971), 221-27.* [refinement-development](https://dl.acm.org/doi/10.1145/357980.358010) 
[^3]: *W.P. Stevens, G.J. Myers, and L.L. Constantine, “Structured Design,” IBM Systems Journal, Vol. 13, No. 2, 1974.* [structured-design](https://dret.net/biblio/reference/ste74) 