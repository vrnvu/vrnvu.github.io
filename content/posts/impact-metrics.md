---
title: "impact metrics"
date: 2023-04-11T00:00:00+00:00
comment: true
tags: ["code"]
---
Impact isn't about how many operations you have. It's about which operations matter most to your users.

Some teams measure the wrong things. They track total traffic, average response times, and aggregate error rates. But these metrics hide the real story.

**The real question**: Which endpoints have the highest user impact when they fail?

Consider a user trying to set up your tool for the first time. If the onboarding API fails, they might abandon your product entirely. That single failure has massive impact—not because of volume, but because it's the user's first impression.

## The hidden failure problem

Aggregate metrics lie. Consider three operations in the same service:

- **Operation A**: 10,000 requests, 10 failures → 0.1% error rate
- **Operation B**: 100 requests, 10 failures → 10% error rate  
- **Operation C**: 100 requests, 50 failures → 50% error rate

The combined error rate looks like 0.03%. But that hides serious issues.

- Which operations fail most?
- Which ones block user workflows?
- Which are critical even if rare?

A rare operation like account creation might break the entire user experience when it fails. Users care about this a lot.

**The pattern**: Rare and manual operations often have the highest user impact when they fail.


## Weight endpoints by impact

Not all requests are equal. A payment failure affects users more than a search timeout. A profile update matters more than a recommendation request.

**Measure what users care about:**

We need to understand our product to define impact.

- **Critical operations**: Login, payments, data saves
- **High-frequency operations**: Search, feeds, navigation  
- **User-blocking operations**: Account creation, password resets
- **Revenue-impacting operations**: Checkout, subscriptions, upgrades

Weight each endpoint by its business impact, not just traffic volume. This is the foundation of impact metrics.


## The result

When you measure and optimize by impact metrics:

- **You understand the product**: A requirement to define a metric.
- **Better user experience**: Critical operations work reliably
- **Focused effort**: Fix what matters most to users
- **Clear priorities**: Data-driven decisions about what to fix
- **Real performance**: Measured by user impact, not server metrics

Measure what users care about. Use impact metrics to weight endpoints by their real impact. Fix the problems that matter most.