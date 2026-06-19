# Architecture

BountyOps Claim Guardian is an agentic workflow pattern for long-running bounty and payout operations.

The project is intentionally conservative. It treats public comments, claim updates, and recruiter/payment follow-ups as actions that need evidence, not as engagement opportunities.

## Inputs

- Public GitHub issue activity.
- Public GitHub pull request state.
- CI/check status.
- Claim marker presence, such as `/claim #80`.
- Sanitized inbox-style notification summaries.
- Local checkpoints from prior runs.

Private mailbox bodies, live authenticated claim URLs, cookies, tokens, bank details, payout credentials, and private local paths are outside the public data boundary.

## Evidence Model

Each active lane is normalized into a compact record:

- bounty or opportunity id;
- active PR URL;
- current PR state;
- merge readiness;
- claim marker state;
- bounty label state;
- latest relevant issue activity;
- latest relevant PR activity;
- contributor-side blocker;
- maintainer-side blocker;
- recommended action.

## Decision Policy

The agent can recommend five actions:

- `fix`: contributor-side code, CI, merge, or documentation blocker exists;
- `comment`: claim visibility or maintainer-request evidence requires a public update;
- `draft`: an email or private follow-up needs user review;
- `watch`: state is clean but should be checked later;
- `checkpoint`: no action is needed and the clean state should be recorded.

The default is `watch` or `checkpoint`. Public comments require a real reason.

## No-Spam Guardrails

Do not post just because time passed. A public comment is allowed only when at least one condition is true:

- a maintainer asked for proof or changes;
- a PR status changed and the change affects payout/merge readiness;
- a competitor created a newer same-issue visibility gap;
- a claim/payment signal needs evidence;
- CI failed and the contributor can fix it;
- the previous public state is stale and the issue is high-value enough to justify a concise status refresh.

## Output

The workflow emits:

- a human-readable dashboard;
- a generated report;
- a compact checkpoint;
- an action log;
- optional public-safe submission package.

## Public Demo Boundary

This repository contains static public demo artifacts. It does not contain the live private workspace, mailbox content, authentication, payout credentials, or claim dashboard sessions.
