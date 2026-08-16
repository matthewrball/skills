# Matthew Ball's Skills

Open-source [Agent Skills](https://agentskills.io/) for repeatable AI coding workflows. Each skill has one portable source of truth in its own repository; compatible agents load the same instructions instead of maintaining vendor-specific copies. This collection is the catalog.

## Standalone projects

| Project | Purpose | Source of truth |
| --- | --- | --- |
| [Baton](https://github.com/matthewrball/baton) | Save a private project handoff that another session or agent can resume. | [`matthewrball/baton`](https://github.com/matthewrball/baton) |
| [Shipcheck](https://github.com/matthewrball/shipcheck) | Review, repair, verify, and watch PR feedback before landing code. | [`matthewrball/shipcheck`](https://github.com/matthewrball/shipcheck) |

## Install

The [GitHub CLI skill commands](https://cli.github.com/manual/gh_skill_install) install the canonical skill into the location expected by a chosen agent.

```bash
gh skill install matthewrball/shipcheck shipcheck --agent universal --scope user
```

```bash
gh skill install matthewrball/baton baton --agent universal --scope user
```

Use `--scope project` to share a skill with one repository. If a host does not read the universal `.agents/skills` location, replace `universal` with one of the host names shown by `gh skill install --help`, for example:

```bash
gh skill install matthewrball/shipcheck shipcheck --agent claude-code --scope user
```

No custom installer or generated wrapper is required.

## Compatibility

These are standard `SKILL.md` folders. Current vendor documentation confirms support in the following major coding agents:

| Host | Documented skill locations | Documentation |
| --- | --- | --- |
| OpenAI coding agents | `.agents/skills`, `$HOME/.agents/skills` | [Build skills](https://learn.chatgpt.com/docs/build-skills) |
| Claude Code | `.claude/skills`, `$HOME/.claude/skills` | [Agent Skills](https://code.claude.com/docs/en/skills) |
| GitHub Copilot | `.agents/skills`, `.github/skills`, user skill directories | [About Agent Skills](https://docs.github.com/en/copilot/concepts/agents/about-agent-skills) |
| Gemini CLI | `.agents/skills`, `.gemini/skills`, user skill directories | [Agent Skills](https://geminicli.com/docs/cli/using-agent-skills/) |
| Google Antigravity | `.agents/skills`, user skill directories | [Skills](https://antigravity.google/docs/skills) |
| Cursor | `.cursor/skills` | [Agent Skills](https://cursor.com/docs/skills) |
| Cline | `.cline/skills`, user skill directories | [Skills](https://docs.cline.bot/customization/skills) |
| Devin | `.devin/skills`, user skill directories | [Skills overview](https://docs.devin.ai/cli/extensibility/skills/overview) |

Other Agent Skills-compatible hosts can load the same folders. Products without Agent Skills support can still be given the relevant `SKILL.md` as instructions, but automatic discovery is host-dependent.

## Design principles

- One portable skill definition; no vendor forks.
- Optional host metadata may tighten invocation safety without changing the core workflow.
- Progressive disclosure through standard `SKILL.md` folders.
- Native host delegation when available, with honest fallback reporting.
- Signed-in subscription usage by default; no silent API billing.
- Local, bounded, reviewable changes with explicit evidence.
- No dependency added when Git, GitHub CLI, the standard library, or plain Markdown is enough.

## References

- [Agent Skills specification](https://agentskills.io/specification)
- [Agent Skills best practices](https://agentskills.io/skill-creation/best-practices)
- [GitHub CLI: install skills](https://cli.github.com/manual/gh_skill_install)
