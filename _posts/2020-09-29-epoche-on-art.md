---
layout: post
title: Epoche on Art
slug: epoche-on-art 
---

One of my favorite papers is Knuth’s ACM Turing lecture from 1974 "Computer programming is an art"[^1]. A lot of water has flowed under the bridge since then but today there are still a lot of engineers who don't see their work as art, as craftsmanship and it's a topic of discussion that we often hear from time to time.

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


If we discuss our work in engineering and programming as an art, specifically as delivering products as works of art, and we want to judge it, it is obvious that the appreciation of these products can be focused on several factors and people will have several criteria to apply. Let's highlight the obvious, without first defining clearly what these criteria are, it would only lead us to absurd discussions like the typical argument about syntaxis that you will usually read on the Internet. Judging a work is undoubtedly complex and can lead to communicative misunderstandings. First you must make clear what the pillars of the work are in order to judge them individually. And all this without going into questions of taste and style, which we will comment on later, we must first talk about aesthetics. The analysis of aesthetics, which is objective, allows us to share a common mental model and debate without entering into personal preferences. Even so, even focusing on the objective aspects of engineering today we still do not have a common ground to address, so therefore I will first give a categorization that makes sense to programming and engineering as works of art. Let's depart from essentialism, first of all I guess we should ask "Why do we program? What is our purpose? "

We program to solve a problem, we build solutions, products or services. We have certain requirements and we fulfill them. That is the foundation on which all engineering is built. This is our goal. Given a problem, we determine the steps to be applied to reach the solution and we execute them accordingly. The path is not an end as many claim. We also create patterns and establish constructions to organize teams, define protocols and guidelines of style, in order to efficiently execute the plan. At the end of the day, engineering is based on the process of executioning a plan. But how did we come to pick that particular path? Today we mostly understand that once we have the specific domain (client) requirements established, there is a bifurcation according to the type of problem we are solving:

- Hard problems, where performance and efficiency are critical: real time, kernels, hardware, proxies, networking... We are facing problems that not only have requirements on a specific domain, but the context of execution of the latter adds new requirements regarding the efficient use of hardware/network/resources... The beauty is found in the correct usage of tools and proficiency. For example, the famous solution of https://en.wikipedia.org/wiki/Fast_inverse_square_root is a genius.
- Soft problems, relaxed problems where there is flexibility regarding performance and efficiency of the solution. These problems allow the investment of human resources (time/cost) in the development environment. From the use of languages at a high level, development of testing or benchmarking environments, development of infrastructure solutions that speed up deployments... Etc. The beauty does not lie in the raw code. The beauty is found in engineering. An example could be from ML to an IDE or a static analyzer. Janestreet in the use of Ocaml. Netflix solutions to your scalability problems. The tribes of Spotify.

Given this categorization, I don't see where there could be a software product that is not a balance of these two categories. Always having one component dominant over the other. Perhaps I have not chosen the best names, nor do I care. We should not lose our track. Our goal is to comment on the article.


---
{: data-content="footnotes"}

[^1]: https://amturing.acm.org/award_winners/knuth_1013846.cfm