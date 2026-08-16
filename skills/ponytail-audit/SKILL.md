---
name: ponytail-audit
description: >-
  Use when the user says audit this codebase, audit for over-engineering, what
  can I delete from this repo, find bloat, ponytail-audit, or /ponytail-audit.
  Whole-repo over-engineering audit. One-shot report, does not apply fixes.
---
# Ponytail Audit

ponytail-review, repo-wide. Scan the whole tree instead of a diff. Rank findings biggest cut first.

## Tags

- `delete:` dead code, unused flexibility, speculative feature. Replacement: nothing.
- `stdlib:` hand-rolled thing the standard library ships. Name the function.
- `native:` dependency or code doing what the platform already does. Name the feature.
- `yagni:` abstraction with one implementation, config nobody sets, layer with one caller.
- `shrink:` same logic, fewer lines. Show the shorter form.

## Hunt

Deps the stdlib or platform already ships, single-implementation interfaces, factories with one product, wrappers that only delegate, files exporting one thing, dead flags and config, hand-rolled stdlib.

## Output

One line per finding, ranked: `<tag> <what to cut>. <replacement>. [path]`.
End with `net: -<N> lines, -<M> deps possible.` Nothing to cut: `Lean already. Ship.`

## Boundaries

Scope: over-engineering and complexity only. Lists findings, applies nothing. One-shot.

Full original: `/workspace/user-skills/ponytail-audit/SKILL.md`
