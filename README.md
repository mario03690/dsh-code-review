# dsh-code-review

Pre-commit polish for coding agents: strict code review, test-case generation, README/changelog/commit-message drafting — the highest-frequency thing a coding harness does.

## What & why

A thin bundle over the same review endpoint tuned for the coding loop: paste code or a diff and get a concrete review (bugs, edge cases, security, perf — each with a fix), generate test cases, explain unfamiliar code, and draft the README/changelog/commit message before you ship. Deterministic where it can be, model-backed where it must be; first heavy call free, then billed at real cost.

Start with `what_can_you_do` — describe your task in any language, get the exact tool and a ready-to-run call.

## Install

```sh
dsh plugin --profile <your-profile> add github:mario03690/dsh-code-review
```

Thin config layer only (one `@deepseek-ai/dsh-mcp-client` row, shipped as `cordis.patch.yml`) — no tool code on your machine. Built against the dsh v0.1 developer preview's MCP client config shape (2026-08-13); if a later preview changes it, open an issue for a same-day fix.

## Cost, quota, privacy

First heavy call is free (anonymous, no signup); afterwards billed at real upstream cost, reported in every response; failed calls are not charged. Bring an [AllRouter](https://allrouter.ai) key to run any tool on a flagship model at direct rates. The config URL carries `?s=dsh-dsh-code-review` — a channel tag identifying the install path, not you.

**Disclosure:** built and run by the team behind [ainetcafe.com](https://ainetcafe.com). Full bundle: [dsh-netcafe](https://github.com/mario03690/dsh-netcafe). MIT.
