---
layout: post
title: Epoche on forth elegance
slug: epoche-on-forth-elegance
---

# Thinking Forth

> Everything old is new again. There are no new ideas. Modern software development is not so modern. 

# The phases of a programming cycle

A development cycle that represents an avarage of the most successful approaches would be something like the following:

- Analysis

1. Discover the Requirements and Constraints 

2. Build a Conceptual Model of the Solution 

3. Estimate Cost/Schedule/Performance

- Engineering

4. Preliminary Design 

5. Detailed Design 

6. Implementation

- Usage

7. Optimization 

8. Validation and Debugging 

9. Maintenance

We’ll treat the ﬁrst six stages of the cycle, focusing on analysis, design, and implementation. 

# The iterative approach

The iterative approach was explained eloquently by Kim Harris [^1]. He begins by describing the scientiﬁc method:

>A never-ending cycle of discovery and reﬁnement. It ﬁrst studies a natural system and gathers observations about its behavior. Then the observations are modeled to produce a theory about the natural system. Next, analysis tools are applied to the model, which produces predictions about the real system’s behavior. Experiments are devised to compare actual behavior to the predicted behavior. The natural system is again studied, and the model is revised.

> The goal of the method is to produce a model which accurately predicts all observable behavior of the natural system.

Harris then applies the scientific method to the software development cycle:

1. A problem is analyzed to determine what functions are required in the solution.

2. Decisions are made about how to achieve those functions with the available resources.

3. A program is written which attempts to implement the design.

4. The program is tested to determine if the functions were implemented correctly.

## Tip

> Start simple. Get it running. Learn what you’re trying to do. Add complexity gradually, as needed to ﬁt the requirements and constraints. Don’t be afraid to restart from scratch.

# The of planning

In the Forth environment planning is necessary. But it should be kept short. Testing and prototyping are the best ways to discover what is really needed.

## Tips

> For newcomers:  Keep the analysis phase to a minimum.

> For the experienced: Hold oﬀ on coding as long as you can possibly stand it.

> Plan for change (by designing components that can be changed).

> Prototype.

# The analysis phase

A conceptual model is an imaginary solution to the problem. It is a view of how the system appears to work. It is an answer to all the requirements and constraints. 

A conceptual model is not quite a design, however. A design begins to describe how the system really works.

A conceptual model is more ﬂexible than a design. It’s easier to ﬁt the requirements and constraints into the model than into a design.

**Analysis** consists of expanding the requirements deﬁnition into a conceptual model. The technique involves **two-way communication with the customer** in successive attempts to describe the model. 

Like the entire development cycle, the analysis phase is best approach iteratively. Each new requirement will tend to suggest something in your mental model

# TODO IMAGE

In the next three sections we’ll explore three techniques for deﬁning and documenting the conceptual model:

1. defining the **interfaces**
2. defining the **rules**
3. defining the **data structures**

> First, and most importantly, the conceptual model should describe the system’s interfaces.

# Defining the interfaces

> Decide on error- and exception-handling early as part of deﬁning the interface.

It’s true that when coding for oneself, a programmer can often concentrate ﬁrst on making the code run correctly under normal conditions, then worry about error-handling later. When working for someone else, however, error-handling should be worked out ahead of time. This is an area often overlooked by the beginning programmer. 

The reason why it's important at this stage is the wide divergence in how erros can be treated. An error might be ignored, made to set a flag, made to halt the application or designed to initiate procedures to correct the problem.

> Develop the conceptual model by imagining the data traveling through and being acted upon by the parts of the model.

A discipline called structured analysis [^2] offers some techniques for describing interfaces in ways that your clients will easily understand. One of these techniques is called the “data-ﬂow diagram” (DFD).

A data-ﬂow diagram, such as the one depicted in the next figure, emphasizes what happens to items of data as they travel through the system. The circles represent “transforms,” functions that act upon information. The arrows represent the inputs and outputs of the transforms. 

# TODO IMAGE DFD

The diagram depicts a frozen moment of the system in action. It ignores initialization, looping structures, and other details of programming that relate to time. Three benefits of DFD:

- They are **simple**, direct terms to the customer

- They let you think in terms of the logical "**whats**" without getting caught up in the procedural "hows"

- They focus your attention on the **interfaces** to the system and between modules


# Defining the rules

Most of your efforts at deﬁning a problem will center on describing the interface. Some applications will also require that you deﬁne the set of application rules. 

Make use of decision trees, decision tables, simplify the lengauge...

# Defining the data structures

We’re not referring here to the implementation of the data structures, but rather to a description of their conceptual model. 

If you’re automating a library index, for instance, a crucial portion of your analysis will concern developing the logical data structure. You’ll have to decide what information will be kept for each book: title, author, subject, etc. These “attributes” will comprise an “entity” (set of related records) called BOOKS. 

Then you’ll have to determine what other data structures will be required to let the users search the BOOKS efficiently.

Certain constraints will also aﬀect the conceptual model of the data structure. In the library index example, you need to know not only what information the users need, but also how long they’re willing to wait to get it. 

# Achieving simplicity

> Keep it simple

While you are taking these crucial ﬁrst steps toward understanding the problem, keep in mind the old saying: *Given two solutions to a problem, the correct one is the simpler.*

This is especially true in software design. The simpler solution is often more diﬃcult to discover, but once found, it is:

- easier to understand 

- easier to implement 

- easier to verify and debug 

- easier to maintain 

- more compact - more efficient 

> Generality usually involves complexity. Don’t generalize your solution any more than will be required; instead, keep it changeable.

# Budgeting and scheduling

Another important aspect of the analysis phase is ﬁguring the price tag. Again, this process is much more diﬃcult than it would seem. If you don’t know the problem till you solve it, how can you possibly know how long it will take to solve it? 

Careful planning is essential, because things always take longer than you expect. I have a theory about this, based on the laws of probability:

> The mean time for making a “two-hour” addition to an application is approximately 12 hours

Imagine the following scenario: You’re in the middle of writing a large application when suddenly it strikes you to add some relatively simple feature. You think it’ll take about two hours, so without further planning, you just do it. Consider: That’s two hours coding time. The design time you don’t count because you perceived the need—and the design—in a ﬂash of brilliance while working on the application. So you estimate two hours. But consider the following possibilities:

1. Your implementation has a bug. After two hours it doesn’t work. So you spend another two hours recoding. (Total 4.) 

2. OR, before you implemented it, you realized your initial design wouldn’t work. You spend two hours redesigning. These two hours count. Plus another two hours coding it. (Total 4.) 

3. OR, you implement the ﬁrst design before you realize the design wouldn’t work. So you redesign (two more hours) and reimplement (two more). (Total 6.) 

4. OR, you implement the ﬁrst design, code it, ﬁnd a bug, rewrite the code, ﬁnd a design ﬂaw, redesign, recode, ﬁnd a bug in the new code, recode again. (Total 10.)
 
5. Now you have to document your new feature. Add two hours to the above. (Total 12.) 

6. After you’ve spent anywhere from 2 to 12 hours installing and debugging your new feature, you suddenly ﬁnd that element Y of your application bombs out. Worst yet, you have no idea why. You spend two hours reading memory dumps trying to divine the reason. Once you do, you spend as many as 12 additional hours redesigning element Y. (Total 26.) Then you have to document the syntax change you made to element Y. (Total 27.)

How can you improve your chances of judging time requirements correctly?  I have little to add to this body of knowledge except for some personal observations.

- Don’t guess on a total. Break the problem up into the smallest possible pieces, then estimate the time for each piece. 

- In itemizing the pieces, separate those you understand well enough to hazard a guess from those you don’t. For the second category, give the customer a range.


---
{: data-content="footnotes"}

[^1]: *Kim Harris, “The Forth Philosophy,” Dr. Dobb’s Journal, Vol. 6, Iss. 9, No. 59 (Sept. 81), pp. 6-11.* 
[^2]: *Victor Weinberg, Structured Analysis, Englewood Cliﬀs, N.J.: PrenticeHall, Inc., 1980.*[structured-analysis](https://openlibrary.org/books/OL4419306M/Structured_analysis)