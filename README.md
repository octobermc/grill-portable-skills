# grill-portable-skills

Cursor plugin with four text skills: `grill-me`, `grilling`, `grill-with-docs`, and `domain-modeling`. It is the only plugin listed by this repository marketplace at `.cursor-plugin/marketplace.json`.

This repository contains only that marketplace and plugin. It does not contain the rest of [mattpocock/skills](https://github.com/mattpocock/skills), and it has no hooks, rules, agents, commands, MCP configuration, or installer scripts.

Install it from the marketplace entry whose `source` is `cursor-plugins/grill-portable-skills`.

All four skills have `disable-model-invocation: true`. They load only when someone explicitly invokes them (for example `/grill-me` or `/grill-with-docs`).

Source review commit of mattpocock/skills: `5863806dd4e15c63174bee4e7515a4256792ecfa`. The skill text is a reviewed portable adaptation. The MIT notice is embedded in each `SKILL.md`.
