+++
title = "syntax vs semantics"
date = 2022-06-07
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

Ok. I'm tired of this topic.

Two definitions quoting one of my favourite courses [^1].

- **Syntax**. By syntax, we mean the rules that define what constitutes a textually well-formed program in the language, including the keywords, restrictions on whitespace and formatting, punctuation, operators, etc. 

- **Semantics**. By semantics, we mean the rules that define the behavior of programs. In other words, semantics is about the meaning of a program—what computation a particular piece of syntax represents. Note that although “semantics” is plural in form, we use it as singular. That’s similar to “mathematics” or “physics”.


So then, what is code readibility?

- Code readability = syntax that make semantics obvious.

If a block of code is written in an imperative style or functional style doesn't matter. Ask yourself instead, are the semantics clear? Are we coping or moving the values? Are we cloning the references? Are we iterating over mutable references or copies of the value?

A good language, with good code readability, makes semantics obvious. A good programmer, encourages good readability. With good readability we don't have doubts about what a piece of code is doing. 

<!-- more -->

---
# Footnotes

[^1]: *Cornell Ocaml cs3110* [cs3110](https://cs3110.github.io/textbook/chapters/basics/intro.html?highlight=syntax)