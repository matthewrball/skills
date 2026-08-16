---
name: model-router
description: >-
  Use when the user asks which Codex, Claude, or Gemini model/subscription to
  use, mentions account routing, token use, Max/Pro/business subscriptions,
  high-effort agents, handoffs, or wants a handoff prompt for another agent.
---
# Model Router

Decide where AI work should run and prepare a handoff when it should leave this session.

1. Read `/workspace/user-skills/model-router/references/routing-policy.md`.
2. Classify ownership: Onramp, Delegance, Personal, or mixed. Ask if mixed and it matters.
3. Classify work mode (planning, UI review, backend, frontend, debug, review, docs, long refactor).
4. Account boundary wins over model preference. Do not cross company/personal subscriptions unless the user overrides.
5. Do not auto-launch external agents. Create a full-context handoff prompt (objective, success criteria, repo/state, decisions, constraints, files to inspect, spec, verification, stop conditions, return format).

Handoff extras: `/workspace/user-skills/model-router/`
