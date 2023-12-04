
+++
title = "write shorter lines"
date = 2022-09-05
draft = true
 

[taxonomies]
categories = ["culture"]
tags = ["culture"]

[extra]
lang = "en"
toc = true
show_comment = true
math = false
mermaid = false
+++
---

# Long text lines

Lately I've been re-visiting this email that Russ Cox wrote in 2008. Why? Because bad decisions stress me out more than bad code. I start believing in the theory that some programmers write bad code on purpose to later maintain it. Let's write awful architectures so nobody else understands them. Well, the problem starts with writing long lines. It does. You start writing long lines and it snowballs into maintaining a 5k Haskell project that prints a `hello world`.

<!-- more -->

I found this funny story in this post about Acme[^1]. It touches some of the recurrent topics in software minimalism. Engineering essentialism. UNIX and forth philosophy. I stop in the "Less is More" section and jump into the email that Russ Cox wrote answering some questions. I selected a few answers and removed unnecessary text. I want to focus in Russ answers. Let's jump into them:

```
> what is the Acme way of approaching it?
> 01. Toggle on/off line wrapping
> 02. Toggle on/off EOL character display

Write shorter lines.
```

Here we go. Just don't write long lines. Write shorter lines. 

Can you see the space between this pharagraph and the previous? Took me milliseconds to fix **your** "problem". Honestly, it surprises me that a key stroke is a problem to someone.

```
> 04. Display ruler

(...). Just say no.

> 05. Rectangluar block selection

(...).  But again, just say no.
```

Why someone needs all these to write code in an editor? People use to write code in punch cards you know?


```
> 07. Automatic insertion of spaces for tabs

Just say no. (...)

> 08. Syntax highlighting of code

Just say no.
```

Again, why do you need all tools to write text in a file? Why are all the questions about personal preference configurations? I could imagine someone reporting a bug in the editor. But, how are the lack of these features any bug? How is the lack of these features a problem?

```
> 09. Code folding

(...)

You're better off writing code that doesn't need folding
to be read.
```

This one is funny. I love how Russ inserted
a new line.

## Don't make problems to solve problems

The idea behind the message is that most of these problems are not real problems. If you are writing a CLI it doesn't matter the color of your syntax highlight or if you wrote the code in VIM or EMACS. The problem is to write a CLI to solve something right? What is the CLI going to do?

A good example of this unix philosophy of not writting unecessary code is found the unix kernel[^3] itself. By Kernighan and Pike has to be one of my favourites examples. Page XXX.

A bad example is most of your code and designs. 

## The best code is the one that you don't write

Following the Unix philosophy and design there is famous meme[^3] about the topic. It's kind of sad that most people staring the project think it's just a joke. What apparently seems to be a satire is a really explored topic in engineering. From hardware to software. Going back to the forth philosophy or 60s minimalism to hardware and compiler design. The art of simplicity. The art of not doing unecesary work. The art of solving THE problem. The art of not create new problems to solve a problem...  Maybe this is a topic for another post.

Overengineering starts with long lines of text.  Bad engineering starts when you start creating problems out of thin air.  Just write shorter lines.

---
# Footnotes

[^1]: *Tao of acme* [acme](https://benghancock.github.io/blog/2022/tao-of-acme.html)

[^2]: *Github nocode repository* [nocode](https://github.com/kelseyhightower/nocode)

[^3]: *The unix programming environment* [unix programming environment](http://files.catwell.info/misc/mirror/the-unix-programming-environment-kernighan-pike.pdf)