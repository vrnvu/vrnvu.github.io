---
layout: post
title: Etude on teaching I
slug: etude-on-teaching-part-i
---

# Teaching

## On teaching tech together

How to create and deliver lessons that work and build a teaching community around them. [^1].

# Mental Models and Formative Assesment

The first task in teaching is to figure out who your learners are.

- **Novies:** don’t know what they don’t know, i.e. they don’t yet have a usable mental model of the problem domain. 

- **Competent practitioners:** have a mental model that’s adequate for everyday purposes. They can do normal tasks with normal effort under normal circumstances, and have some understanding of the limits to their knowledge (i.e. they know what they don’t know). 

- **Experts:** have mental models that include exceptions and special cases, which allows them to handle situations that are out of the ordinary. We will discuss expertise in more detail in Chapter 3. 

## Mental model

So what is a **mental model?** As the name suggests, it is a simplified representation of the most important parts of some problem domain that is good enough to enable problem solving.

Presenting a novice with a pile of facts is counter-productive because they don’t yet have a model to fit those facts into. In fact, presenting too many facts too soon can actually reinforce the incorrect mental model they’ve cobbled together. 

Your goal when teaching novices should therefore be to help them construct a mental model so that they have somewhere to put facts. 

# Are People Learning?

Mark Twain once wrote, “It ain’t what you don’t know that gets you into trouble. It’s what you know for sure that just ain’t so.” One of the exercises in building a mental model is therefore to clear away things that don’t belong. Broadly speaking, novices’ misconceptions fall into three categories:

- **Factual errors:** like believing that Vancouver is the capital of British Columbia (it’s Victoria). These are usually simple to correct.

- **Broken models:** like believing that motion and acceleration must be in the same direction. We can address these by having novices reason through examples where their models give the wrong answer.

- **Fundamental beliefs:** such as “the world is only a few thousand years old” or “some kinds of people are just naturally better at programming than others”. These errors are often deeply connected to the learner’s social identity, so they resist evidence and rationalize contradictions.

**People learn fastest when teachers identify and clear up learners’ misconceptions as the lesson is being delivered.** This is called formative assessment because it forms (or shapes) the teaching while it is taking place. **Learners don’t pass or fail formative assessment; instead, it gives both the teacher and the learner feedback on how well they are doing and what they should focus on next.**

## Formative assessment vs summative assessment

The counterpoint to formative assessment is summative assessment, which takes place at the end of the lesson. Summative assessment is like a driver’s test: it tells the learner whether they have mastered the topic and the teacher whether their lesson was successful. **One way of thinking about the difference is that a chef tasting food as she cooks it is formative assessments, but the guests tasting it once it’s served is summative.**

Unfortunately, school has trained most people to believe that all assessment is summative.

# Notional Machines

The term computational thinking is bandied about a lot, in part because people can agree it’s important while meaning very different things by it. Rather than arguing over what it does and doesn’t include, it’s more useful to think about the notional machine that you want learners to understand. A notional machine:

- is an idealized abstraction of computer hardware and other aspects of programs’ runtime environments.

- enables the semantics of programs to be described.

- correctly reflects what programs do when executed.

## Example Notional Machine: Python


1. Running programs live in memory, which is divided between a call stack and a heap.

2. Memory for data is always allocated from the heap.

3. Every piece of data is stored in a two-part structure. The first part says what type the data is, and the second part is the actual value.

4. Booleans, numbers, and character strings are never modified after they are created.

5. Lists, sets, and other collections store references to other data rather than storing those values directly. They can be modified after they are created, i.e. a list can be extended or new values can be added to a set. 

6. When code is loaded into memory, Python converts it to a sequence of instructions that are stored like any other data. This is why it’s possible to assign functions to variables and pass them as parameters. 

7. When code is executed, Python steps through the instructions, doing what each one tells it to in turn. 

8. Some instructions make Python read data, do calculations, and create new data. Other instructions control what instructions Python executes, which is how loops and conditionals work. Yet another instruction tells Python to call a function. 

9. When a function is called, Python pushes a new stack frame onto the call stack. 

10. Each stack frame stores variables’ names and references to data. Function parameters are just another kind of variable. 

11. When a variable is used, Python looks for it in the top stack frame. If it isn’t there, it looks in the bottom (global) frame.

12. When the function finishes, Python erases its stack frame and jumps backs to the instructions it was executing before the function call. If there isn’t a “before,” the program has finished.



---
{: data-content="footnotes"}

Additional reading.

[^1]: *Greg Wilson* [tech togheter](https://teachtogether.tech/)
