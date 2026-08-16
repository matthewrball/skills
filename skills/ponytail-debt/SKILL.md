---
name: ponytail-debt
description: >-
  Use when the user says ponytail debt, /ponytail-debt, what did ponytail defer,
  list the shortcuts, ponytail ledger, or what did we mark to do later. Harvests
  ponytail: comments into a ledger. One-shot, changes nothing.
---
# Ponytail Debt

Grep the repo for `(#|//) ?ponytail:` comments (skip node_modules, .git, build output). One ledger row per hit:

`<file>:<line>, <what was simplified>. ceiling: <limit>. upgrade: <trigger>.`

Tag `no-trigger` if the comment names no upgrade path. End with `<N> markers, <M> with no trigger.` Nothing found: `No ponytail: debt. Clean ledger.`

Reads only. Persist to `PONYTAIL-DEBT.md` only if asked.

Full original: `/workspace/user-skills/ponytail-debt/SKILL.md`
