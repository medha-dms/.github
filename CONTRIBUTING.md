# Contributing to Medha

This guide applies to **every repository** in the `medha-dms` organization.

## Before you start

1. Turn on **two-factor authentication (2FA)** on your GitHub account. The organization requires it.
2. Set up **commit signing** so your commits show "Verified". See [developer setup](https://github.com/medha-dms/medha-docs/blob/main/guides/developer-setup.md).
3. Make sure you have a Jira story for your work. Every change starts from a Jira story (for example `MDH-12`).

## Branches

- `main` is protected. Nobody pushes to `main` directly.
- Create one branch per Jira story:

| Type | Branch name |
| --- | --- |
| New feature / story | `feature/MDH-12-short-name` |
| Bug fix | `fix/MDH-40-short-name` |
| Docs only | `docs/MDH-55-short-name` |
| Small chores (deps, config) | `chore/MDH-60-short-name` |

Use lowercase and dashes in the short name.

## Commit messages

Start every commit message with the Jira key. This links the commit to the story in Jira automatically.

```
MDH-12 add login API
MDH-12 add tests for wrong password
MDH-40 fix rounding in best-N quiz marks
```

Rules:

- Write in the present tense: "add", "fix", "update" (not "added").
- Keep the first line under 72 characters.
- One commit = one small, clear change.
- All commits must be **signed** (shows "Verified" on GitHub).

## Pull requests (PR)

1. Keep a PR small: one story per PR.
2. Put the Jira key in the PR title: `MDH-12 Add login API`.
3. Fill in the PR template (it opens by itself).
4. CI (lint + tests) must pass.
5. At least **1 approval** is needed. The service owner (from `CODEOWNERS`) must approve.
6. Use **Squash and merge**, so `main` keeps one clean commit per story.
7. Delete the branch after merge.

## Code review

- Review within 1 working day if you can.
- Be kind and clear. Comment on the code, not the person.
- Say what to change and why. Mark small style points as "nit:".

## Services and data

- Each service owns its own database. **Never read or write another service's database.**
- Services talk to each other only through their API (written in `openapi.yaml`).
- Change an API contract only after the owners of the services that use it agree.

## Secrets

- Never commit passwords, API keys, tokens or database URLs.
- Keep them in a `.env` file (already in `.gitignore`) and share a `.env.example` with empty values.
- In CI, use GitHub **Secrets**.
- If you commit a secret by mistake, tell the team at once and change (rotate) that secret. Deleting the commit is not enough.

## Requirements

Requirements live in the [SRS](https://github.com/medha-dms/medha-docs/blob/main/srs.md). If your work changes a requirement, update the SRS in `medha-docs` with a PR, and mention the requirement ID (for example `FR-T-10`).
