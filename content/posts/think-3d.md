---
title: "think in 3d"
date: 2022-01-12T00:00:00+00:00
comment: true
tags: ["culture"]
---

As traffic increases and performance degrades, teams default to two approaches:

- **Horizontal scaling**: adding more instances
- **Vertical scaling**: upgrading to bigger machines

Pause for a moment. Did you notice something missing? If not, you might be seeing in 2D.

Both approaches treat symptoms, not causes. They assume the application is already optimal. This assumption adds cost, complexity, and technical debt: more machines, more moving parts, slower teams.

Don't limit yourself to 2D. Add the third dimension: optimize the application. Think in 3D.

### The Third Dimension

Application optimization often delivers outsized returns. Examples:

- **Database queries**: Adding an index can improve performance by orders of magnitude
- **Caching**: A Redis cache can reduce database load dramatically
- **Algorithm optimization**: Switching an algorithm from O(n²) to O(n log n) can make a difference
- **Memory usage**: Reducing allocations and memory footprint translates directly to performance
 - **Memory management**: Using arenas or bump allocators reduces allocation overhead and fragmentation
 - **Garbage collection**: Lowering short‑lived allocations reduces GC pressure and pauses
 - **Serialization**: Avoiding unnecessary serialization/deserialization removes avoidable CPU work
 - **Kernel crossings**: Reducing user-kernel copies and syscalls cuts context switching overhead
 - **I/O patterns**: Batch writes, use zero-copy, and align buffers to improve throughput
 - **Indirection**: Flatten pointer-chasing data structures to improve cache locality
 - **Data-oriented design**: Use struct-of-arrays vs array-of-structs to match access patterns 

These optimizations compound. A major improvement in code efficiency means you need far fewer servers. Your infrastructure costs drop, your system becomes simpler, and you have more room for growth.

### Why the third dimension is overlooked

Application optimization requires different skills than infrastructure scaling. It demands:

- **Deep code analysis**: Understanding bottlenecks and inefficiencies
- **Performance measurement**: Profiling before and after changes
- **Algorithm knowledge**: Knowing when O(n) becomes O(n²)
- **Hardware understanding**: CPU, RAM, kernel, and low-level system behavior
- **System thinking**: Understanding how components interact

Many teams lack these skills or don't prioritize them. It's easier to throw hardware at problems than to fix the underlying code. Invest in these [skills](https://www.brendangregg.com) and apply them deliberately.

### Measure first, then optimize

Measure first. Profile your application to find [bottlenecks](https://github.com/tigerbeetle/tigerbeetle/blob/main/docs/TIGER_STYLE.md#performance) across CPU, memory, disk, and network:

- Database query performance
- Memory allocation patterns
- CPU usage by function
- Network I/O efficiency

Then optimize the biggest wins first. A single optimization often outperforms multiple infrastructure changes.

### Optimization compounds

Application optimization compounds over time. Each improvement makes the next one easier. Your code becomes more maintainable, your system more reliable, and your costs more predictable.

When you think in 3D, you don't just scale—you [evolve](https://arnau.bearblog.dev/engineers-as-gardeners/). Your application becomes more efficient, your team becomes more skilled, and your business becomes more sustainable.

Think in 3D.