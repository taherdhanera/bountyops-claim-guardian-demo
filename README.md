# BountyOps Claim Guardian

Reasoning agent for protecting open-source bounty payouts.

## What It Does

BountyOps Claim Guardian monitors active bounty claims across GitHub, Gmail notifications, claim pages, CI checks, and local evidence logs. It ranks payout risk, detects competitor or maintainer activity, and decides whether to act, watch, or skip.

The core policy is conservative: public comments are generated only when there is a real claim visibility gap, contributor-side blocker, failed check, or maintainer request. Clean passes become audit checkpoints instead of noisy comments.

## Why It Matters

Open-source bounty work can lose payout visibility when issue tails, PRs, claim bots, and CI status change quickly. The agent keeps the contributor's active claims review-ready by preserving evidence:

- active PR link
- claim marker such as `/claim #80`
- merge and draft status
- bounty label state
- CI/check state
- latest issue/PR activity
- maintainer blockers or no-action reasoning

## Demo Evidence

Public-safe live example:

- SecureBanana #80 evidence comment: https://github.com/SecureBananaLabs/bug-bounty/issues/80#issuecomment-4677720719
- Active PR: https://github.com/SecureBananaLabs/bug-bounty/pull/1666
- Local checkpoint: `bounty-checkpoint-2026-06-11-1152-securebanana80-yfengj-cleared.md`

The demo uses sanitized local fixtures for repeatability and does not include private Gmail, live claim URLs, cookies, bank data, payout credentials, or tokens.

## Local Demo

```powershell
cd agent-prize-radar
npm run demo
```

This generates:

- `reports/demo-current.md`
- `reports/demo-dashboard.html`

For the live local state:

```powershell
npm run report
npm run dashboard
npm run action-log
npm run submission
```

Key live artifacts:

- `reports/current.md`
- `reports/dashboard.html`
- `reports/action-log.json`
- `submissions/microsoft-agents-league-bountyops.md`
- `submissions/microsoft-demo-video-script.md`

## Agent Loop

1. Read current watcher and claim state.
2. Search Gmail for actionable bounty and payout notifications.
3. Inspect hot GitHub issue and PR lanes.
4. Rank by payout amount, merge readiness, visibility risk, and blocker status.
5. Act only when evidence shows a real gap.
6. Write a compact checkpoint so the next run can resume quickly.

## Microsoft Agents League Fit

Track: Reasoning Agents

BountyOps demonstrates multi-step tool reasoning, risk-aware action, and auditable decision making. It uses real-world GitHub/Gmail/claim signals, turns them into structured evidence, and decides when external action is warranted.

## Safety Rules

- Never publish private mailbox content.
- Never include secrets, cookies, tokens, bank data, or payout credentials.
- Use public GitHub links and sanitized fixtures for demos.
- Keep public comments sparse, professional, and evidence-backed.
