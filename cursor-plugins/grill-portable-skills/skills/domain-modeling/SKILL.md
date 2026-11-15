---
name: domain-modeling
description: "Use only when the user explicitly asks for domain modeling, a glossary, or ADRs, or when grill-with-docs has already been explicitly invoked in this turn. Do not use automatically."
disable-model-invocation: true
---

# domain-modeling

Portable adaptation of Matt Pocock's `domain-modeling` skill from [mattpocock/skills](https://github.com/mattpocock/skills/tree/main/skills/engineering/domain-modeling) at commit `5863806dd4e15c63174bee4e7515a4256792ecfa`. MIT License, Copyright (c) 2026 Matt Pocock.

**Opt-in only.** Run this skill only when the user has explicitly asked for domain modeling, a glossary, or architecture decision records, or when `grill-with-docs` has already been explicitly invoked in this turn.

Actively build and sharpen the project's domain model as you design: challenge terms, invent edge-case scenarios, and write the glossary and decisions down the moment they crystallise. Merely reading an existing glossary for vocabulary is not this skill.

## Where to write

Only write `GLOSSARY.md` and `docs/adr/` inside the software project the user is clearly working on in this turn. If there is no such project, show the draft in chat and wait; do not create files yet. Never write Cursor user config, Grok Bot core files, or unrelated folders. Create files lazily: only when you have something to write.

Most repos have a single context, with `GLOSSARY.md` at the repo root and decision records in `docs/adr/`. If a `GLOSSARY-MAP.md` exists at the root, the repo has multiple contexts; follow that map. If neither a map nor a root glossary exists, create a root `GLOSSARY.md` when the first term is resolved, and create `docs/adr/` when the first decision record is needed.

## During the session

- When the user uses a term that conflicts with `GLOSSARY.md`, call it out immediately and ask which meaning is right.
- When the user uses vague or overloaded terms, propose a precise canonical term.
- When domain relationships are discussed, stress-test them with specific edge-case scenarios.
- When the user states how something works, check whether the code agrees, and surface contradictions.
- When a term is resolved, update `GLOSSARY.md` right there. Do not batch these up. The glossary must contain no implementation details; it is a glossary and nothing else.

## Glossary format

```md
# {Context Name}

{One or two sentence description of what this context is and why it exists.}

## Language

**Order**:
{A one or two sentence description of the term}
_Avoid_: Purchase, transaction
```

Be opinionated: when multiple words exist for the same concept, pick the best one and list the others under `_Avoid_`. Keep definitions to one or two sentences. Only include terms specific to this project's context, not general programming concepts. Group terms under subheadings when natural clusters emerge.

For a multi-context repo, `GLOSSARY-MAP.md` lists each context, where it lives, and how the contexts relate. If the current topic's context is unclear, ask.

## Decision records

ADRs live in `docs/adr/` as `0001-slug.md`, `0002-slug.md`, and so on. Scan for the highest existing number and increment by one. An ADR can be a short title plus one to three sentences: the context, the decision, and why. Optional sections (status, considered options, consequences) only when they add genuine value.

Offer an ADR only when all three are true: it is hard to reverse; a future reader would wonder why it was done this way; and it was the result of a real trade-off. If any of the three is missing, skip the ADR.
