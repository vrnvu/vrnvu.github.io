---
title: "this is ci"
date: 2025-10-21T00:00:00+00:00
comment: true
tags: ["code"]
---

Last month, a developer updated a library version. The application worked fine in development, but production crashed at 2 AM. The deployment pipeline had passed all tests—but it hadn't tested the actual change. This is why most CI fails: it tests code, not changes. When CI fails, production breaks, teams lose trust, and changes become dangerous.

Most teams think CI is about running tests on GitHub. They're wrong. CI is about correctness and detecting changes automatically. We test to have correct code and detect changes, and CI is that process being [continuous](https://graydon2.dreamwidth.org/1597.html).

That the team has the same code, versioned with tags and releases, the same functional and reproducible setup, are [consequences](https://matklad.github.io/2024/03/22/basic-things.html) of CI.

## What Can We Test?

Continuous Integration succeeds when every change becomes visible through failing tests. Everything else—pipelines, environments, tools—are just means to this end.

Test [everything](https://kobzol.github.io/rust/2025/03/25/just-write-a-test-for-it.html): code, operations, environments, migrations and rollbacks. Test GitHub: releases, tags and workflows. Test observability: logs and metrics. Test binary size and lines of code.

Make linting and formatting part of the test, not separate steps. Make benchmarks part of the test: regression performance test. Test Docker and environment setup, automate everything and verify it. Test CI/CD pipelines: that scripts, actions and workflows work after changes.

Everything that can break your workflow must be tested automatically.

When CI works properly:
- If we change our environment from AWS to Azure, a test must fail.
- If we update the version of a library and something breaks, a test must fail.
- If we change a path in a pipeline, a test must fail.
- If we run a migration script and we forgot a prerequisite, a test must fail.
- If the code does something with logs or metrics that we didn't expect, a test must fail.

The limit is set by you and your team. The time you have and how good you are at programming.

Now let's see how this works in practice. The most common scenario is when a software engineer adds new behavior.

## Detecting Changes in Practice

How do we detect this change? How do you make a test fail when introducing new untested code? This is where code coverage comes in.

Code coverage doesn't measure code correctness, or how "complete" testing is, only what code is being executed by tests. When you add or remove code, coverage changes. We can create a test that fails if coverage drops below a threshold. This automatically ensures any change is detected and must be managed. This aligns with the [risk-driven testing approach](https://googletesting-test.blogspot.com/2014/05/testing-on-toilet-risk-driven-testing.html) that emphasizes testing the areas that matter most.

Similar ideas apply to removing or changing behavior. The key is making any change visible through tests.

## This is CI

If something changes, a test must fail or force us to add a check! Read this sentence ten times. This is CI.