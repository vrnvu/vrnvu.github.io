---
title: "jujutsu techniques"
date: 2025-12-17T00:00:00+00:00
comment: true
tags: ["code"]
---

I was upgrading a project to Spring Boot 4. Multiple modules and libraries. Java, Gradle, AWS, CI, Docker... The kind of change that usually demands long-lived branches, careful sequencing, and a lot of trial and error.

What surprised me wasn't the technical complexity. It was how much the shape of the work changed once the cost of being wrong went to zero.

This is what my tree looked like:
```sh
➜  java-upgrade git:(5561fa3) ✗ jj
@    nruuvkns arnau@local 2025-12-12 20:31:20 spring4 27d4b705
├─╮  upgrade to spring boot 4.0
│ ○  rzoyrzpv arnau@local 2025-12-12 20:30:29 jackson3 d76dcecc
│ │  upgrade from jackson2 to jackson3
○ │  yyxuxnmk arnau@local 2025-12-12 20:31:17 aws-cloud git_head() 5561fa39
├─╯  upgrade aws cloud 4
○  ttusytzr arnau@local 2025-12-12 20:30:29 spring35 5a817998
│  upgrade to spring boot 3.5
○      uolmolxo arnau@local 2025-12-12 20:30:29 java-25 26dda0de
├─┬─╮  upgrade to java sdk 25
│ │ ○  yvklzspu arnau@local 2025-12-12 20:29:47 aws-sdk-2 e2045bf6
│ │ │  upgrade to java aws sdk 2
│ ○ │  mkwpqylt arnau@local 2025-12-12 20:30:18 refactor-cache 36105341
│ ├─╯  simplifies cache by removing external dependencies
○ │  qxmnvtxp arnau@local 2025-12-12 20:29:56 docker-image 49a19a38
├─╯  ci uses in-house image and new action gradle tasks
○  kpqwwnkk arnau@local 2025-12-12 20:29:42 gradle bf2b0dad
│  upgrade gradle 8 to gradle 9
◆  zzzzzzzz root() 00000000
```

**Nothing was planned in advance**. 

Every change in that log became a pull request. One [stacked](http://stacking.dev) on top of another. My team reviewed the smallest possible [diff](https://gist.github.com/thoughtpolice/9c45287550a56b2047c6311fbadebed2) as best as Github allowed it. 

There's a video of [Brian Anderson reading a code review](https://www.youtube.com/watch?v=7F4jAz8liV8&list=PL9eL-xg48OM0iMz7n4bggGlFGdwB4Y6Sh&index=23&pp=iAQB) where he talks about being afraid of feedback. About needing time to process it. Brian is phenomenal. I respect his honesty because that fear never really goes away. We know we aren't the code we write. Even when you know you aren’t your code, mistakes still feel expensive.

I don't need a clean history to make progress. I don't need to get it right before sharing. I don't even need it to work. I can try something, show it to my team, and throw it away without shame. I reverted commits. I shared wip ideas. I could say "this might be stupid" and still push it.

Commands like `duplicate`, `squash`, and `restore` aren't just technical operations. They're psychological tools because they remove the cost of being wrong. 

Understanding how your teammate thinks is often more valuable than the code they wrote. **Conflicts aren't failures. They're conversations.**

Many tools and methodologies encourage you to decide on a solution before you understand the problem. This way of working does the opposite. It rewards motion: thinking, prototyping, writing, breaking things, fixing them. Fearless [Sledgehammer Programming](https://www.youtube.com/watch?v=ubWB_ResHwM). It's a creative process. Friction slows progress. I need movement.

I don't want to teach `jj`. I want to share what it taught me.

When experimentation is cheap, you stop optimizing for correctness up front and start optimizing for feedback. And once the cost of being wrong drops low enough, fear quietly gets out of the way.