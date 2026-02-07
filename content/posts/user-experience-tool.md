## Tools

When I use a tool, I want the tool to care about me. I want it to be good. I
want it to explain itself. I don't want to search Google for documentation, skim
blog posts, or click through SEO just to remember how something works.

I want examples. I want clarity. Everything I need should be part of the tool
itself. That's not how most software works anymore. Everything is monetized.
Everything is optimized for ads, engagement, and searches.

Recently I built a small [TUI](https://github.com/rnaudi/gh-log) to explore
GitHub PR analytics in the terminal. I wanted summaries and basic metrics
without leaving the command line.

> tool: something that helps you do a particular activity

```
gh-log print | claude “Summarize into 3 key accomplishments”
```

This is how I think about building tools.

## Onboarding

Onboarding is speed. **How fast someone goes from curiosity to action**.
Download. Run. Everything else slows things down. I have a soft spot for
one-line installers. If it can’t be one line, it should be one block that’s easy
to copy and paste.

If it’s a CLI, ship a binary. You’re an engineer. You live in the terminal. You
use GitHub every day. I support Mac, Linux, and Windows, current versions only.
The deal is simple: download the binary, put it in your PATH, run it. If this
sounds hard, you’re not the user.

## Discoverability

A tool should explain itself. Good CLIs have short help and long help. The long
help matters. A giant README or an external docs site is a warning sign.
**Documentation belongs in the tool**. Write
[comments](https://antirez.com/news/124). If you have to search the web to learn
basic usage, the tool failed you.

Less is more. Back to UNIX principles. There are no visualizations. Output is
CSV, text, or JSON.
[Always bet on text](https://graydon2.dreamwidth.org/193447.html).

There’s also a `doctor` command. It shows what’s cached, where files live, which
config is loaded, and where the binary is. You shouldn't have to guess whether
something is working. If you're guessing, the tool failed again.

I don't integrate LLM APIs. I don't manage API keys. That’s not the tool’s job.
I won’t hide things behind abstractions. **When writing code is cheap, saying no
matters more.**

## Dependencies

I revisited [Our Software Dependency Problem](https://research.swtch.com/deps)
by Russ Cox recently, and it clicked with how I already felt. **If a dependency
is core, treat it like source control: commit to maintaining it like a product.
If it’s not core, it’s a liability.** This is close to the
[Build vs. Buy](https://entropicthoughts.com/build-vs-buy) dilemma.

## Who is the tool?

Configuration should respect you. A good tool doesn't force you to change how
you work. You already use GitHub and pull requests. The tool adapts to you, not
the other way around. You can ignore projects, exclude repos, filter with regex.

Bad tools do the opposite. They invent a process and make you fit into it. They
create a workflow and turn you into the tool.

## User experience

Design is choice. UX is the tool.
