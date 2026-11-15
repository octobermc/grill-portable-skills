---
name: grilling
description: "Use only when the user explicitly asks to grill a plan, or when grill-me or grill-with-docs has already been explicitly invoked in this turn. Do not use automatically."
disable-model-invocation: true
---

# grilling

Portable adaptation of Matt Pocock's `grilling` skill from [mattpocock/skills](https://github.com/mattpocock/skills/tree/main/skills/productivity/grilling) at commit `5863806dd4e15c63174bee4e7515a4256792ecfa`. MIT License, Copyright (c) 2026 Matt Pocock.

**Opt-in only.** Run this skill only when the user has explicitly asked to grill a plan, or when `grill-me` or `grill-with-docs` has already been explicitly invoked in this turn.

Interview the user relentlessly until you reach a shared understanding. Map this as a **design tree**: every decision branches into the decisions that hang off it.

Work the tree in **rounds**. The **frontier** is every decision whose prerequisites are already settled: the questions you can ask now without guessing at answers you have not heard yet. Ask the whole frontier in one round: number each question and give your recommended answer. Then wait for the user's answers before the next round.

Format a round like so:

```
❓ **Q1** - **<question title>**: <question body, might be multiple paragraphs, including multiple choices>

➡️ <your recommended answer>

---

❓ **Q2** - **<question title>**: <question body, might be multiple paragraphs, including multiple choices>

➡️ <your recommended answer>
```

Word each question so "yes" accepts your recommended answer.

Each round the user answers reshapes the tree: settled decisions push the frontier outward and unblock questions that depended on them. Recompute the frontier and ask the next round. A question whose answer depends on another question still open in this round belongs to a later round, not this one.

Finding facts is your job, never the user's. When a frontier question needs a fact you can look up yourself, look it up; don't ask the user for anything you could find. Don't block the rest of the frontier on a lookup that is still running. The decisions are the user's: put each to them and wait.

The session is done when the frontier is empty: every branch of the design tree visited, nothing left silently assumed. Do not act on the plan until the user confirms you have reached a shared understanding.
