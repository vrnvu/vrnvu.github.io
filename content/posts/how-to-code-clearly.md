---
title: "how to code clearly"
date: 2024-12-22T00:00:00+00:00
comment: true
tags: ["code"]
---
This piece adapts the wisdom from the [International Paper Company's famous writing campaign](https://davedye.com/2019/07/12/how-to-write-good/)

## How to code clearly

If you are afraid to code, don't be. If you think you've got to string together big fancy constructs and high-flying functions, forget it. To code well, you only need to know how to get your ideas across simply and clearly.

It's not easy. But it's easier than you might imagine. There are only three basic requirements:

1. You must **want** to code clearly. And I believe you really do, if you've stayed this far with me.
2. You must be willing to **work** hard. Thinking means work - and that's what it takes to do anything well.
3. You must know and follow some basic guidelines.

If, while you're coding for clarity, some lovely, dramatic, or inspired ideas come to you, fine. Put them in.

But then with cold, objective eyes and mind ask yourself: *"Do they detract from clarity?"* If they do, grit your teeth and cut the frills.

## Follow some basic guidelines

I can't give you a complete list of *"dos and don'ts"* for every code problem you'll ever face. But I can give you some fundamental guidelines that cover the most common problems.

### 1. Outline what you want to do

I know that sounds grade-schoolish. But you can't code clearly until, *before you start*, you know where you will stop. Ironically, that's even a problem in writing an outline. I.e knowing the solution before solving the problem.

1. Grab pen and paper. Or a sophisticated modern device of your preference. Start by drawing the problem with different representations.

2. Think about the simplest possible problem you have. Solve it by hand. Iterate. Think about alternatives. You can't solve what you don't understand. Fall in love with the problem.

3. Group your ideas, move them around. Play and have fun.

4. Think **concretely**. What data do you have? What data transformations will you need? What are the inputs and outputs? How do you represent the state of the problem?

There you have your outline, needing only to be coded. This is a practical way to outline. It's also flexible. You can add, delete or change ideas as you go along.

### 2. Start where you are

How much do you know about your problem? Don't code to a level higher than your knowledge is. If you haven't coded your solution yet, you can't be sure you have solved it. Code your solution, nothing more.

Code it again. Repeat until satisfied. Every iteration should be clearer than the last.

**CAUTION:** Forget that old - and wrong - advice about writing clean code, using smart patterns and making architecture decisions. That's insulting. But do remember your prime purpose is to explain your solution clearly, not to prove that you're smarter than others.

### 3. Avoid jargon

Don't use patterns, algorithms and obscure ideas known only to people with specific knowledge or interests. Example: A *"software architect"*, using jargon, said in a meeting: *"I'm going to use CQRS and Event Sourcing to read and write to a non-relational database."* He could have said: *"I'm going to read and write from an Excel file".* And everyone in the room would have understood.

### 4. Use familiar tools

When reviewing code, I once saw a magician calling this a smart solution:
```js
const numbers = [4, 12, 15, 3, 18, 21, 9, 11]
const groups = numbers.reduce((acc, num) => {
    num > 10 && (acc[num % 3] = [...(acc[num % 3] || []), num].sort((a, b) => a - b))
    return acc
}, {})
```
We ended up with coding clearly what we wanted:
```js
const numbers = [4, 12, 15, 3, 18, 21, 9, 11]
const largeNumbers = numbers.filter(num => num > 10)

const groups = {
    0: [],  // numbers that divide evenly by 3
    1: [],  // numbers that give remainder 1
    2: []   // numbers that give remainder 2
}

for (let num of largeNumbers) {
    const remainder = num % 3
    groups[remainder].push(num)
}

for (let remainder in groups) {
    groups[remainder].sort()
}
```

Unfortunately, we are not smart anymore. We just have clear code. Lord forgive us, we have comments.

### 5. Use "first-degree" tools

Use the standard library. Use your if, loop, while and functions etc. Don't invent abstractions.

These immediately bring an image to your mind. Other tools must be *"translated"* through the first-degree tools before you see.

1. Prefer functions over classes and traits.
2. Prefer static functions over methods.
3. Prefer arrays, sets and maps over complex data structures.

### 6. Stick to the point

Your outline now saves you work. Because now you can ask about any line of code: *"Does it relate to an idea in the outline?"* If it doesn't, delete it.

### 7. Be as brief as possible

Whatever you code, shortening and first-degree tools always make it tighter, easier to read and understand.

1. Present your ideas in logical order.
2. Don't waste words telling people what they already know.
3. Cut out excess and unnecessary work.

### 8. Stop coding

Finally, to code more clearly by saying it in fewer words: **when you've solved the problem, stop.**