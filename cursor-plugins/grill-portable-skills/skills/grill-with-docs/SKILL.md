---
name: grill-with-docs
description: "Use only when the user explicitly asks for grill-with-docs, or to grill a plan and write docs as you go. Do not use automatically."
disable-model-invocation: true
---

# grill-with-docs

Portable adaptation of Matt Pocock's `grill-with-docs` skill from [mattpocock/skills](https://github.com/mattpocock/skills/tree/main/skills/engineering/grill-with-docs) at commit `5863806dd4e15c63174bee4e7515a4256792ecfa`. MIT License, Copyright (c) 2026 Matt Pocock.

**Opt-in only.** Run this skill only when the user has explicitly asked for it in this turn. Do not start it because a plan, idea, or design came up in conversation.

This skill is an entry point. Call the Skill tool twice, for `grilling` and `domain-modeling`. Grill the plan in rounds, and write the glossary and decision records as terms and decisions crystallise. Do not begin implementing the plan until the grilling session is done and the user confirms you have reached a shared understanding.
