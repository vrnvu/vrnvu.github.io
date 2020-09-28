---
layout: post
title: Epoche on Art
slug: epoche-on-art 
---

One of my favorite papers is Knuth’s ACM Turing lecture from 1974 [Computer programming is an art](https://amturing.acm.org/award_winners/knuth_1013846.cfm). A lot of water has flowed under the bridge since then but today there are still a lot of engineers who don't see their work as art, as craftsmanship and it's a topic of discussion that we often hear from time to time.

I will quote Knuth directly for the body of the commentary since I liked his original narrative and how it evolved from the etymological origin of the word art to his contemporary work and programming as engineering. There is nothing better to understand why programming is indeed art than reading the author of "The Art of Computer Programming" right?

---
{: data-content="Art"}

> Going back to Latin roots, we find ars, artis meaning "skill." It is perhaps significant that the corresponding Greek word was τεχνη, the root of both "technology" and "technique."

> Nowadays when someone speaks of "art" you probably think first of "fine arts" such as painting and sculpture, but before the twentieth century the word was generally used in quite a different sense. Since this older meaning of "art" still survives in many idioms, especially when we are contrasting art with science.

> In medieval times, an "art" meant something devised by man's intellect, as opposed to activities derived from nature or instinct. During the middle ages the word "art" by itself usually meant logic, which usually meant the study of syllogisms.

> As civilization and learning developed, the words took on more and more independent meanings, "science" being used to stand for knowledge, and "art" for the application of knowledge. Thus, the science of astronomy was the basis for the art of navigation. The situation was almost exactly like the way in which we now distinguish between "science" and "engineering."

---
{: data-content="Works of art"}

After a sweet introduction our first stop will be the following fragment.

> When I speak about computer programming as an art, I am thinking primarily of it as an art form, in an aesthetic sense. The chief goal of my work as educator and author is to help people learn how to write beautiful programs. 

> My feeling is that when we prepare a program, it can be like composing poetry or music; as Andrei Ershov has said, programming can give us both intellectual and emotional satisfaction, because it is a real achievement to master complexity and to establish a system of consistent rules.

> Furthermore when we read other people's programs, we can recognize some of them as genuine works of art. 

> Some programs are elegant, some are exquisite, some are sparkling. My claim is that it is possible to write grand programs, noble programs, truly magnificent ones!


If we discuss our work in engineering and programming as an art, specifically as delivering products as works of art, and we want to judge it, it is obvious that the appreciation of these products can be focused on several factors and people will have several criteria to apply. Let's highlight the obvious, without first defining clearly what these criteria are, it would only lead us to absurd discussions like the typical argument about syntaxis that you will usually read on the Internet. Judging a work is undoubtedly complex and can lead to communicative misunderstandings. First you must make clear what the pillars of the work are in order to judge them individually. And all this without going into questions of taste and style, which we will comment on later, we must first talk about aesthetics. The analysis of aesthetics, which is objective, allows us to share a common mental model [^1] and debate without entering into personal preferences. Even so, even focusing on the objective aspects of engineering today we still do not have a common ground to address, so therefore I will first give a categorization that makes sense to programming and engineering as works of art. Let's depart from essentialism, first of all I guess we should ask "Why do we program? What is our purpose? "

We program to solve a problem, we build solutions, products or services. We have certain requirements and we fulfill them. That is the foundation on which all engineering is built. This is our goal. Given a problem, we determine the steps to be applied to reach the solution and we execute them accordingly. The path is not an end as many claim. We also create patterns and establish constructions to organize teams, define protocols and guidelines of style, in order to efficiently execute the plan. At the end of the day, engineering is based on the process of executioning a plan. But how did we come to pick that particular path? Today we mostly understand that once we have the specific domain (client) requirements established, there is a bifurcation according to the type of problem we are solving:

- Hard problems, where performance and efficiency are critical: real time, kernels, hardware, proxies, networking... We are facing problems that not only have requirements on a specific domain, but the context of execution of the latter adds new requirements regarding the efficient use of hardware/network/resources... The beauty is found in the correct usage of tools and proficiency. For example, the famous solution of [fast inverse square root in Doom](https://en.wikipedia.org/wiki/Fast_inverse_square_root) is a genius.
- Soft problems, relaxed problems where there is flexibility regarding performance and efficiency of the solution. These problems allow the investment of human resources (time/cost) in the development environment. From the use of languages at a high level, development of testing or benchmarking environments, development of infrastructure solutions that speed up deployments... Etc. The beauty does not lie in the raw code. The beauty is found in engineering. An example could be from ML to an IDE or a static analyzer. Janestreet in the use of Ocaml. Netflix solutions to your scalability problems. The tribes of Spotify [^5].

Given this categorization, I don't see where there could be a software product that is not a balance of these two categories. Always having one component dominant over the other. Perhaps I have not chosen the best names, nor do I care. We should not lose our track. Our goal is to comment on the article [^2].


---
{: data-content="Taste and Style"}

> The idea of style in programming is now coming to the forefront at last, and I hope that most of you have seen the excellent little book on Elements of Programming Style by Kernighan and Plauger [^3]. In this connection it is most important for us all to remember that there is no one "best" style; everybody has his own preferences, and it is a mistake to try to force people into an unnatural mold. We often hear the saying, "I don't know anything about art, but I know what I like." The important thing is that you really like the style you are using; it should be the best way you prefer to express yourself.

I would like to make an observation and comment on some psychoanalysis. A recent article that I found fascinating about programming languages is fue [The Perverts Guide to computer programming](https://www.youtube.com/watch?v=mZyvIHYn2zk). Programming languages are created to concisely model a specific problem or to maximize expression while solving a broad range of problems. Psychoanalysts have noted that manydecisions we make as humans are not based on rational premises, but rather are based on fears and desires that stem from upbringing and our societal ideologies. In the paper they use the psychoanalysis of Jacques Lacan and Slavoj Zizek [^4] to critique programming languages. I will not go too deep into the article, I highly recommend you to scrim over it just for fun.

What I don’t agree with is the claim “there is no best style”, if we focus more in detail on the concept of style, we can all conclude that there are tools more suitable for one job than another. A style of programming is nothing but a manifestation, a causality of the tools and context from which it originates. Every style is composed of fundamental elements and limited by external factors. When external factors change, the style will evolve like water adapting to a container. To give some specific examples about programming, most of the changes about paradigms, languages and tooling have been caused by an external factor you may be familiar with, the hardware. Multi core and multi thread CPUs, contemporary CPU microarchitectures... Hardware evolution and performance improvements are external factors that have affected the software we write and the tools we use. In a similar way, distributed systems, scalability needs, growing source code repositories and project requirements are other external elements that directly affect methodologies and engineering. We don't use a control version like git because we think it's the perfect solution, we use it because it's the best solution we know at this moment in time and I really hope that when there's a superior alternative, we'll be able to see the beauty of it and adopt it.


---
{: data-content="Beauty"}

> There are many senses in which a program can be "good," of course. In the first place, it's especially good to have a program that works correctly. Secondly it is often good to have a program that won't be hard to change, when the time for adaptation arises. Both of these goals are achieved when the program is easily readable and understandable to a person who knows the appropriate language.

> Another important way for a production program to be good is for it to interact gracefully with its users, especially when recovering from human errors in the input data. It's a real art to compose meaningful error messages or to design flexible input formats which are not error-prone.

> Another important aspect of program quality is the efficiency with which the computer's resources are actually being used. I am sorry to say that many people nowadays are condemning program efficiency, telling us that it is in bad taste. The reason for this is that we are now experiencing a reaction from the time when efficiency was the only reputable criterion of goodness, and programmers in the past have tended to be so preoccupied with efficiency that they have produced needlessly complicated code; the result of this unnecessary complexity has been that net efficiency has gone down, due to difficulties of debugging and maintenance.

> The real problem is that programmers have spent far too much time worrying about efficiency in the wrong places and at the wrong times; premature optimization is the root of all evil (or at least most of it) in programming.

Knuth also was encouraged to analyze what constitute programming a work of art and what makes it beautiful, he decided not do it in a categoric/schematic way as we attempted previously, he constructed his discourse referring to his contemporaries and just named some of the components, unfortunately he lacked the perspective of the 42 years of software development that we have. It would be interesting to know how he would define the beauty of the art of programming after so many decades of banging our heads against walls.

---
{: data-content="final thoughts"}

Some people are fascinated by how the “classics” have predicted the future. They actually did not predict anything. We have built on them. I like this perspective way more. We walk over the shoulders of giants don’t we?

We haven’t yet agreed on the components of aesthetics and beauty because humans are emotional and we do get offended easily. Still, we evolve. Even if we do not verbalise it, we advance in the right path, it just takes us more time to reach our destination or fulfill our true potential. Even though I'd like people to encourage and accept criticism way more openly. I’m not criticizing you, it's just an opinion about your art. Your work does not define you, you define your art piece. We are artists, we should act as such. Love your craft and be responsible for it. Live and learn. 


---
{: data-content="footnotes"}

[^1]: [Wiki](https://en.wikipedia.org/wiki/Mental_model) I'm thinking about Piaget and constructivism. Please do share your mental model always.

[^2]: I gave a categorization that plays nicely with opportunistic programming, data oriented + functional programming, hexagonal/onion/polylith and similar contemporary ideas that I probably expand in the future 

[^3]: Please do read and recommend classic content like this, Peter Norvig's style guide on common lisp will also please you :P . Contemporary Computer sci literature is poluted by low quality books.

[^4]: I personally suggest Zizek or Jung over Freud for starters. For learning/communication dig into constructivism.

[^5]: [Spotify engineering](https://engineering.atspotify.com/2014/03/27/spotify-engineering-culture-part-1/) I was giving some examples of modern methodologies or how companies hold a major role in software development and engineer. The work of Yaron Minsky in Jane Street... I could also mention open source projects but I didn't want to get too deep. 