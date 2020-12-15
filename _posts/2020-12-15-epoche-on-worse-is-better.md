---
layout: post
title: Epoche on worse is better
slug: epoche-on-worse-is-better
---

# Worse is better

The rise of "Worse is better"[^1], by Richard Gabriel

In the commentary Richard introduces and compares different schools of design and philosophies applied to software engineering.

# Right thing philosophy

The essence of this style can be captured by the phrase "the right thing.".Most programmers (lisp) have an extreme exposure to the MIT/Stanford style of design. To such a designer it is important to get all of the following characteristics right:

- **Simplicity**: The design must be simple. Both in implementation and interface. It is more important for the interface to be simple than the implementation
- **Correctness**: The design must be correct in all observable aspects. Incorrectness is simply not allowed
- **Consistency**: The desgin must not be inconsistent. A design is allowed to be slightly less simple and less complete to avoid inconsitency. Consistency is as important as correctness.
- **Completeness**: The desgin must cover as many important situations as is practical. All reasonably expected cases must be covered. Simplicity is not allowed to ovelry reduce completeness.

# Worse is better philosophy

Slightly different from the "MIT approach".

-**Simplicity**: The design must be simple, both in implementation and interface. It is more important for the implementation to be simple than the interface. Simplicity is the most important consideration in a design
-**Correctness**: The design must be correct in all observable aspects. It is slightly better to be simple than correct 
-**Consistency**: The design must not be overly inconsistent. Consistency can be sacrificed for simplicity in some cases, but it is better to drop those parts of the design that deal with less common circumstances than to introduce either implementational complexity or inconsistency 
-**Completeness**: The design must cover as many important situations as is practical. All reasonably expected cases should be covered. Completeness can be sacrificed in favor of any other quality. In fact, completeness must sacrificed whenever implementation simplicity is jeopardized. Consistency can be sacrificed to achieve completeness if simplicity is retained

Early Unix and C are examples of the use of this school of design, Richard calls this school **"New Jersey approach"**.

---
{: data-content="footnotes"}

[^1]: *The Rise of "Worse is Better" By Richard Gabriel* [worse-is-better](https://www.jwz.org/doc/worse-is-better.html) 