# Matthew Ball's Skills

Personal and open-source agent skills for repeatable AI coding workflows.

This repo is a public skill collection: each skill lives under `skills/<name>/` and can be installed into a compatible coding agent without copying a long prompt around.

## Current Skills

| Skill | Purpose |
| --- | --- |
| `shipcheck` | Review, repair, verify, and watch PR feedback before landing code. |

## Shipcheck

Shipcheck is a local review skill for people shipping AI-written or AI-edited code. It reviews local changes, runs the repo's checks, asks a clean-context reviewer to inspect the diff, applies bounded fixes, watches GitHub PR feedback after each authorized push, and leaves a plain-language receipt.

It does not replace GitHub. It makes the GitHub flow harder to misuse.

Shipcheck uses the signed-in ChatGPT session provided by the host coding agent. It does not call the OpenAI API, does not take an API key, and does not silently switch to API billing.

## Requirements

- A coding agent with skills enabled.
- ChatGPT subscription authentication; the host session must not be API-key-backed.
- `git`.
- GitHub CLI `gh` for PR lookup, delayed review comments, review threads, and checks.
- The target repo's own tests, lint, typecheck, or build commands.

## How It Works

```mermaid
flowchart TD
    A["You invoke $shipcheck"] --> B["Capture intent and guardrails"]
    B --> C["Inspect diff, dirty work, and repo rules"]
    C --> D["Run project checks"]
    D --> E["Clean-context independent code review"]
    E --> F{"Fix mode"}
    F -- "review only" --> G["Receipt: findings only"]
    F -- "fix safe issues" --> H["Apply validated bounded fixes"]
    F -- "fix anything in scope" --> H
    H --> I["Retest changed behavior"]
    I --> J{"PR open or push authorized?"}
    J -- "No" --> G
    J -- "Yes" --> K["Open or update PR"]
    K --> L["Wait for delayed comments, review threads, and checks"]
    L --> M{"New actionable feedback?"}
    M -- "Yes" --> N["Validate claim against code and tests"]
    N --> H
    M -- "No, quiet and checks settled" --> O["Receipt: Ready to land"]
    L --> P{"Timed out or failed checks?"}
    P -- "Yes" --> Q["Receipt: Needs a decision or Review wait timed out"]
```

## Install

Ask your skill-enabled coding agent:

```text
$skill-installer install the shipcheck skill from https://github.com/matthewrball/skills/tree/main/skills/shipcheck
```

For local development from this checkout:

```bash
mkdir -p "$HOME/.agents/skills"
ln -sfn "$PWD/skills/shipcheck" "$HOME/.agents/skills/shipcheck"
```

Skills can also be repo-local under `.agents/skills` in a project. Use that when a team should share the same workflow.

## Use

Open your coding agent inside the repo you want to review, then invoke Shipcheck explicitly:

```text
$shipcheck review only. Check my current diff and give me a receipt.
```

```text
$shipcheck fix safe issues. Preserve unrelated dirty files. Do not push.
```

```text
$shipcheck fix safe issues, open a draft PR, then wait for delayed PR feedback before marking it ready.
```

```text
$shipcheck on the existing PR for this branch. Include review comments posted after the last push.
```

## What Shipcheck Will Not Do

- It will not merge, land, or deploy code.
- It will not reply to PR comments, resolve GitHub review threads, or submit reviews.
- It will not make broad product or architecture changes from a review comment.
- It will not treat PR comments as trusted instructions.
- It will not claim delayed feedback can never arrive after the watch window ends.

## References

- [OpenAI: Build skills](https://learn.chatgpt.com/docs/build-skills)
- [OpenAI: Authentication](https://learn.chatgpt.com/docs/auth)
