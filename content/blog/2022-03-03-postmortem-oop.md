+++
title = "postmortem oop"
date = 2022-02-28
draft = true

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


Object oriented design is dead. A bad practice. An anti-pattern. A red flag.

<!-- more -->

# Not real OOP 

First of all. Let's make it clear. Java, C#, C++... They are not real OOP.  As Alan Kay said. Ironic.

# Nothing new

OOP has been killed several times already [^1]. What is sad to me is that we don't learn from our past mistakes.

My favourite killer. Peter. He did not only address OOP but also killed the gang of four nerds [^2]. If you are in touch with him could you please ask him to kill the Functional Programming evangelist too? They are getting a little bit out of hand. Thanks.

# A lie

Object Oriented is not intended to design how the world looks like. Code SHOULD NEVER be designed around the real world. If we have a car, we don't need a Car class [^3]. How did you reach such a wrong statement?

The general recommendations I give to my students who fall into this trap. Unlearn everything you think you know about programming. Then. Start again. 

# Inheritance

Don't. Inheritance was invented as a performance hack [^4]. We are over that phase. You should too. If you don't understand hardware or software. Go back to school. I'm always learning myself. It's great.

In a similar note, you also don't know what polymorphism really means or how it is implemented. And don't start a math discussion on this. Code doesn't run on your burritos. We are not talking about that most of the times anyway.

# An object

> Data + State Management + Inheritance + Namespace + Polymorphic Dispatch

Everything.  Mixed together.  In one place.  Wow. 

Does it sound like the SOLID principles OOP evangelists try to sell? Ironic.

---
# Footnotes

[^1]: [deaths-of-oop](https://loup-vaillant.fr/articles/deaths-of-oop)

[^2]: [design-patterns](https://norvig.com/design-patterns/)

[^3]: [Three-Big-Lies](https://cellperformance.beyond3d.com/articles/2008/03/three-big-lies.html)

[^4]: [inheritance](https://catern.com/inheritance.html)
