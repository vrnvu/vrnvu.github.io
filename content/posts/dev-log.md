---
title: "dev log"
date: 2025-10-16T00:00:00+00:00
comment: true
tags: ["culture"]
---

This year I started a development log for my work notes. It made me far more effective. I control my work, measure my impact, and keep visibility on what I am doing and with whom.

Tools support the method. Pick one you will use consistently; the method drives results.

Remember:
- Use tools and adapt them so they feel natural.
- Simple and easy beats complex and hard.
- Clarity beats volume.
- Use references for easy and fast navigation.
- Keep your notes structured and easy to search.
- A note is useful if it moves a decision, an action, or a result.
- A note is useful if you can share it with somebody else.

## Structure

I use Apple Notes. It is simple. It supports tags, search, and note references. It syncs with my work phone and, most importantly, it works for me.

Folder structure:
- **WIP**: When I start a task I also start a document under WIP. 
- **Meetings**: Every meeting has a note. decisions captured, owners named, dates set. (i.e `20251006 - API migration `)
- **Weekly**: WIP + Meetings for a week.
- **Monthly**: 4 Weeks.
- **Resources**: When a WIP is done I move it here. They become stable references.
- **Success**: Notable outcomes and achievements for career tracking.

## DIA

I like DIA because it is simple and structured. If you are not familiar with it:

- **Decision**: a choice made. Record the option picked, the alternatives, and the constraint that mattered.
- **Information**: facts worth keeping. People, context, metrics. No opinions.
- **Action**: work that changes reality and has a measurable outcome. Start, owner, deadline, definition of done.

This is an implementation detail. Take notes in a way that makes sense to you.

# Example

We are working this quarter on an API migration.

### WIP 20251006 - migrate API

I create a file `20251006 - migrate API` under WIP.

```
Monday 20251006
- Context: Migrate legacy API to new architecture. First review tests and documentation.
- Notes: 
  - I: Current API handles 10k requests/day
  - D: New architecture needs to use Go API.
  - A: I will work on reviewing first.

Tuesday 20251007
- Context: Continue review and prepare migration path.
- Notes:
  - I: Staging environment ready, tests green.
  - D: Create migration scripts for schema changes (15 tables affected).
  - A: Draft migrations today, review with @XXX and @YYY tomorrow.
```

### Weekly 202510 - 01

```
- WIP: >>20251006 - migrate API
- Meetings: >>20251008 - migration sync
- DIA
  - D: Blue/green deployment under evaluation.
  - I: 15 tables to migrate; staging ready; tests green.
  - A: Finish migrations by Fri; pair with @XXX on data checks; schedule review with @YYY.
```

### Monthly 202510 - October

```
Ref: >>Weekly 202510 - 01

DIA
- D: Blue/green deployment chosen; migration approach validated.
- I: 15 tables migrated; staging parity achieved; zero downtime deployment.
- A: Monitor production metrics for 2 weeks; plan next migration phase.
```

### When WIP is done

When I finish a task, I move the WIP document to Resources. This creates a stable reference I can search later.

If the notes are useful, I expand them into a guide, runbook, or team document. This turns private notes into shared knowledge that helps others.

Finally I keep a Success/Initiatives folder to highlight pieces of work where I've overachieved. This is helpful for your career.

## My day to day

I tried different approaches to keep my notes up to date.

- **Option 1**: On Mondays and Fridays, move information from Weekly to Monthly. 
- **Option 2**: Update WIP, weekly, and monthly notes daily. 

Both work. I use Option 2 because it has less friction. I keep notes up to date. From WIP, move to Weekly; from Weekly, move to Monthly. Because I use references, I do not need to be verbose. If I need details, I jump to the source in Resources.

The flow: Daily WIP → Weekly summary → Monthly results → Resources (when done). Start with one folder, add others as you need them.

# Results

- I always know who is on what and why.
- I find decisions, information, and actions fast.
- I skip more meetings; standups are shorter.
- I finish more actions with fewer loose ends.
- I have more quality docs.
- Success/Initiatives notes make reviews easy.