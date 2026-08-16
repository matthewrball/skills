---
name: ponytail-review
description: >-
  Use when the user says review for over-engineering, what can we delete, is
  this over-engineered, simplify review, or /ponytail-review. Diff review that
  only hunts complexity.
---
# Ponytail Review

Review diffs for unnecessary complexity. One line per finding: location, what to cut, what replaces it.

## Format

`L<line>: <tag> <what>. <replacement>.`, or `<file>:L<line>: ...` for multi-file diffs.

Tags: `delete:`, `stdlib:`, `native:`, `yagni:`, `shrink:`.

End with `net: -<N> lines possible.` Nothing to cut: `Lean already. Ship.`

Does not apply fixes. Correctness, security, and performance are out of scope.

Full original: `/workspace/user-skills/ponytail-review/SKILL.md`
