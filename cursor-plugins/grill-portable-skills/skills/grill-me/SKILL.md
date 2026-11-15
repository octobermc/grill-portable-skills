---
name: grill-me
description: "Use only when the user explicitly asks to grill a plan, names grill-me, or uses /grill-me. Do not use automatically."
disable-model-invocation: true
---

# grill-me

Portable adaptation of Matt Pocock's `grill-me` skill from [mattpocock/skills](https://github.com/mattpocock/skills/tree/main/skills/productivity/grill-me) at commit `5863806dd4e15c63174bee4e7515a4256792ecfa`. MIT License, Copyright (c) 2026 Matt Pocock.

**Opt-in only.** Run this skill only when the user has explicitly asked for it in this turn. Do not start it because a plan, idea, or design came up in conversation.

This skill is an entry point. Call the Skill tool with `grilling`. Do not begin work on the plan until the grilling session is done and the user confirms you have reached a shared understanding.
