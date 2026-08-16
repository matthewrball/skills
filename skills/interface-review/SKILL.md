---
name: interface-review
description: >-
  Use when reviewing a change rather than a whole screen: uncommitted work, the
  current branch, or a PR. Triggers on interface-review, review my branch,
  review my PR, review the diff, review my changes, review before pushing,
  design regression check.
---
# Interface Review

Review the change, not just the leftover code. Resolve scope (ahead-of-base + dirty, else dirty, else HEAD~1). Expand changed files to affected surfaces. Read removed lines for regressions. Classify each finding: Introduced, Regression, or Pre-existing. Hand the review to better-interface for domain routing, severity, and verdict.

Correctness/tests/security are out of scope.

Sibling refs: `/workspace/user-skills/interface-review/` (scope-resolution.md, removed-signals.md).
