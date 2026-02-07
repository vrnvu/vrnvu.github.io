---
title: "you will be google"
date: 2026-01-28T00:00:00+00:00
comment: true
tags: ["culture"]
---

Early in my career I worked with a Google team on an open-source project. **I
didn't like it**. Strict reviews, rigid style, heavy testing discipline.
Everything felt slow and overengineered. A waste of time. I moved on, and
everyone said the obvious thing: you’re not Google, you don’t need to do what
Google does. That’s true. But it’s incomplete.

Teams don’t stay small and stable. People move. Engineers leave. New ones
arrive. Managers become directors. Projects change owners. Roadmaps change.
Priorities shift. What started as a greenfield project, written with the latest
tools, becomes [legacy](https://laike9m.com/blog/avoid-mini-frameworks,171/)
faster than expected.

Sometimes it happens all at once: a reorganization, a new leadership layer, a
strategic pivot. The people who understood the system are gone. At that point,
some ideas stop looking like overengineering and start looking like foresight.
What remains is the [code](https://www.hyrumslaw.com) and whatever
[discipline](https://drewdevault.com/2021/04/02/Go-is-a-great-language.html) was
baked into it.

The first time I worked on a service handling millions of requests per second, I
didn’t understand how everything broke. Constantly. Libraries everyone trusted
started failing in strange ways. And somehow I was the one fixing them. At
scale, edge cases stop being edges. **A billion requests is next Thursday.**

You gain an intuition that’s hard to explain and slow to acquire. Maybe you’ll
never have that volume. Even without volume, time applies pressure.

Most objections come from not seeing the forest because of the trees. You may
not understand why using assertion libraries is discouraged in Go. It looks
arbitrary, ideological, pointless. But the
[reasons](https://matttproud.com/blog/posts/testing-frameworks-and-mini-languages.html)
are not for today. They are for two, five, ten years from now. You don’t plant a
tree to enjoy its shadow.

No. You’re not Google. But given enough time, you will face similar problems:
scale, rotation, decay, loss of context. Not in size, but in complexity. Entropy
doesn't care how small your codebase is.

So don’t copy them. But don’t dismiss them either. Read what they
[write](https://abseil.io/resources/swe-book/html/toc.html). Pay attention to
why they do things that seem unnecessary. One day, something will click.
