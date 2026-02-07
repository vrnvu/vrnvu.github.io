---
title: "resource driven design"
date: 2025-10-28T00:00:00+00:00
comment: true
tags: ["code"]
---

In this post we explore how starting from resources (CPU, RAM, DISK, NETWORK)
can drive clearer, simpler and more robust system design — rather than beginning
with features, frameworks or fancy architecture.

Modern software don’t fail because they lack abstractions. They fail because
they ignore hardware.

## Cultural disconnect

Engineering is about solving a problem in a specific context: time, team,
budget, tools, and both functional and non-functional requirements.

Yet many projects start from features, then pick tools, patterns, and scaling
strategies without ever asking what hardware they actually need. It's what the
[Three Big Lies](https://cellperformance.beyond3d.com/articles/2008/03/three-big-lies.html)
of software engineering called out years ago, abstraction sold as progress.

Does it even make sense to "design for a million users"? A system running on
what? With how much memory, how many cores, how fast a disk? As discussed in
[thinking in 3d](https://arnaudiaz.com/posts/think-3d/) we have to understand
the full picture.

Software ultimately spends its time doing one of two things: computing (CPU) or
dispatching I/O (DISK and NETWORK). By thinking in terms of resources, we draw
clear boundaries between them. These boundaries make performance and efficiency
decisions deliberate, not accidental.

## RAM

A classic bottleneck appears when data no longer fits in memory. The "de facto"
best practice is to horizontally scale the system with queues, logs, sharding
and distributed processing tools.

But consider the [math](https://github.com/sirupsen/napkin-math).

- 1 GB of RAM costs roughly $2 per month.
- 1 TB costs around $2000 per month.

Before we reinvent distributed systems, maybe we should ask why is the "best
practice" more complex, expensive, and harder to maintain than simply buying
more RAM?
[Scale, but at what cost?](https://www.usenix.org/system/files/conference/hotos15/hotos15-paper-mcsherry.pdf)

## CPU

CPU-bound loads are those where data lives entirely in memory:

- read from RAM → compute in RAM → write to RAM.

Performance depends on computation and memory throughput, not on I/O. Optimizing
such systems means minimizing cache misses, data movement, and context switching
— not spinning up more message brokers.

To stay CPU-bound data must be at least in
[RAM](https://people.freebsd.org/~lstewart/articles/cpumemory.pdf). If we
accessed data from DISK or NETWORK, which are more expensive than CPU, we
wouldn't be CPU-bound anymore.

## Ask the Right Questions

At a higher level, **resource-driven design** invites simpler questions:

- What resources do we have, and how will they be used?
- What kind of traffic and data patterns will the system face?
- What skills and tooling does our team already have?

From those answers,
[architecture](https://www.allthingsdistributed.com/2023/07/building-and-operating-a-pretty-big-storage-system.html)
emerges naturally. A system that matches reality, not aspiration.

Once you view the system through resources, submodules appear on their own.

- **Read**: Is it RAM, DISK, or NETWORK? What are the hardware
  [limits](https://notes.eatonphil.com/2025-03-27-things-that-go-wrong-with-disk-io.html)?
- **Process**: Where does the computation happen, and what resource does it
  saturate?
- **Write**: Where does the output go? Can we batch or buffer? Can we batch
  operations to reduce syscalls?

Boundaries follow resources. Thinking in resources helps reveal coupling,
bottlenecks, and waste. It’s less about
[imaginary problems](https://blog.cerebralab.com/Imaginary_Problems_Are_the_Root_of_Bad_Software),
more about physics.
