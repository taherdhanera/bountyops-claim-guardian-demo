# BountyOps Claim Guardian

Reasoning-agent workflow for protecting open-source bounty payouts without noisy public comments.

[![Live demo](https://img.shields.io/badge/live-demo-1168d8)](https://taherdhanera.github.io/bountyops-claim-guardian-demo/)
[![Agent workflow](https://img.shields.io/badge/agent-workflow-177245)](ARCHITECTURE.md)
[![No spam policy](https://img.shields.io/badge/policy-no--spam-5f6f82)](#safety-rules)
[![Static public demo](https://img.shields.io/badge/static-public--safe-7a3db8)](PUBLIC_DEMO_MANIFEST.md)
[![Public release](https://img.shields.io/badge/release-v0.1.0-0f766e)](https://github.com/taherdhanera/bountyops-claim-guardian-demo/releases/tag/v0.1.0-public-demo)
[![License MIT](https://img.shields.io/badge/license-MIT-111827)](LICENSE)

Live demo: https://taherdhanera.github.io/bountyops-claim-guardian-demo/

Stable release: https://github.com/taherdhanera/bountyops-claim-guardian-demo/releases/tag/v0.1.0-public-demo

Repository:
https://github.com/taherdhanera/bountyops-claim-guardian-demo

## Use This If You Are Building

- an AI agent that watches GitHub, Gmail, CI, payments, support, recruiting, or release signals;
- a dashboard that turns messy external state into a ranked next-action queue;
- a no-spam action policy for agents that may comment, email, or escalate;
- a reusable checkpoint format for long-running work that cannot depend on memory alone.

## Why This Repo Is Worth Saving

Most agent demos stop at chat. BountyOps shows a practical operations loop: read live external state, rank risk, decide whether action is justified, and leave evidence another human or agent can resume from.

It is designed for workflows where a noisy or wrong action can hurt the user:

- open-source bounty and payout monitoring;
- GitHub issue, PR, CI, and review-state triage;
- inbox and notification queues;
- recruiting, support, release-readiness, and payment follow-up pipelines;
- long-running agent tasks that need checkpointed memory instead of guesswork.

If this pattern helps your own agent work, star or save the repo so it is easier for other builders to find.

The fastest way to evaluate it is the live dashboard plus the architecture note:

- [Live demo](https://taherdhanera.github.io/bountyops-claim-guardian-demo/)
- [Agent decision model](ARCHITECTURE.md)
- [Workflow template](WORKFLOW_TEMPLATE.md)

## 30-Second Review

| Need | Start here |
| --- | --- |
| See the product-style demo | [Live demo](https://taherdhanera.github.io/bountyops-claim-guardian-demo/) |
| Understand the agent decision model | [ARCHITECTURE.md](ARCHITECTURE.md) |
| Reuse the operating pattern | [OPERATIONS_PLAYBOOK.md](OPERATIONS_PLAYBOOK.md) |
| Copy the workflow template | [WORKFLOW_TEMPLATE.md](WORKFLOW_TEMPLATE.md) |
| See where the pattern fits | [USE_CASES.md](USE_CASES.md) |
| Share it without spam | [SHARE_KIT.md](SHARE_KIT.md) |
| Launch it responsibly | [LAUNCH_CHECKLIST.md](LAUNCH_CHECKLIST.md) |
| See the public roadmap | [ROADMAP.md](ROADMAP.md) |
| Inspect the generated dashboard | [demo-dashboard.html](demo-dashboard.html) |
| Read a sample checkpoint/report | [demo-current.md](demo-current.md) |
| Verify the public data boundary | [PUBLIC_DEMO_MANIFEST.md](PUBLIC_DEMO_MANIFEST.md) |
| Check project maintenance notes | [CHANGELOG.md](CHANGELOG.md) |

## Who Should Star / Save This

BountyOps is a public-safe reference for practical agentic operations. Star or save it if you are building agents that must watch changing external state, decide when action is justified, and leave a clear audit trail.

- monitors GitHub issues, PRs, CI, claim markers, and inbox-style notifications;
- ranks payout risk and contributor-side blockers;
- preserves an audit trail for long-running work;
- avoids spam by acting only when evidence shows a real gap;
- packages the result as a readable dashboard and replayable decision report.

It is most useful for AI-agent builders, open-source bounty contributors, maintainers, indie hackers, and teams designing GitHub, Gmail, CI, payment, support, recruiting, or release-readiness workflows.

## What This Proves

| Capability | Public proof |
| --- | --- |
| Long-running agent state | [demo-current.md](demo-current.md) shows the compact checkpoint/report format. |
| Review-ready UI | [demo-dashboard.html](demo-dashboard.html) turns watcher output into a scan-friendly operations dashboard. |
| Conservative action policy | [ARCHITECTURE.md](ARCHITECTURE.md) documents when the agent may comment, fix, draft, watch, or checkpoint. |
| Reusable playbook | [OPERATIONS_PLAYBOOK.md](OPERATIONS_PLAYBOOK.md) explains how to adapt the loop to recruiting, support, payments, and release ops. |
| Copy-paste starter | [WORKFLOW_TEMPLATE.md](WORKFLOW_TEMPLATE.md) gives a lane schema, action matrix, comment shape, and checkpoint format. |
| Public-safe packaging | [PUBLIC_DEMO_MANIFEST.md](PUBLIC_DEMO_MANIFEST.md) defines the data boundary for sharing the demo. |
| Real GitHub evidence | The demo links to public issue and PR evidence without exposing private account data. |

## Reuse The Pattern

The workflow is intentionally small enough to copy:

```text
inputs -> evidence lanes -> risk ranking -> action policy -> comment/fix/wait/checkpoint -> report
```

Useful starting points:

- [WORKFLOW_TEMPLATE.md](WORKFLOW_TEMPLATE.md) for lane schema and action matrix.
- [OPERATIONS_PLAYBOOK.md](OPERATIONS_PLAYBOOK.md) for adaptation steps.
- [ARCHITECTURE.md](ARCHITECTURE.md) for the conservative decision policy.
- [PUBLIC_DEMO_MANIFEST.md](PUBLIC_DEMO_MANIFEST.md) for the public/private data boundary.

## Fast Demo Path

1. Open the [live dashboard](https://taherdhanera.github.io/bountyops-claim-guardian-demo/).
2. Scan the active-lane table and action queue.
3. Read [demo-current.md](demo-current.md) for the generated checkpoint/report.
4. Review [ARCHITECTURE.md](ARCHITECTURE.md) for the decision policy and safety boundary.

The demo is intentionally static, public-safe, and easy to review in under five minutes.

If the workflow is useful, star or save the repo so other agent builders can find the public-safe reference.

## Built For

- open-source bounty contributors protecting claim visibility
- maintainers who want fewer noisy status comments
- AI-agent builders designing conservative action policies
- teams building GitHub, Gmail, CI, and API operations dashboards
- founders who want agent workflows that do useful work outside chat

## Search Keywords

AI agents, agentic workflow, GitHub automation, Gmail automation, bounty monitoring, payout operations, CI monitoring, claim protection, no-spam automation, evidence logs, workflow dashboard, open-source bounty operations.

## What It Does

BountyOps Claim Guardian monitors active bounty claims across GitHub, Gmail notifications, claim pages, CI checks, and local evidence logs. It ranks payout risk, detects competitor or maintainer activity, and decides whether to act, watch, or skip.

The core policy is conservative: public comments are generated only when there is a real claim visibility gap, contributor-side blocker, failed check, or maintainer request. Clean passes become audit checkpoints instead of noisy comments.

## Demo

Open the static demo:

- Live site: https://taherdhanera.github.io/bountyops-claim-guardian-demo/
- Dashboard: [demo-dashboard.html](demo-dashboard.html)
- Generated report: [demo-current.md](demo-current.md)
- Use cases: [USE_CASES.md](USE_CASES.md)
- Operations playbook: [OPERATIONS_PLAYBOOK.md](OPERATIONS_PLAYBOOK.md)
- Workflow template: [WORKFLOW_TEMPLATE.md](WORKFLOW_TEMPLATE.md)
- Public manifest: [PUBLIC_DEMO_MANIFEST.md](PUBLIC_DEMO_MANIFEST.md)
- Share kit: [SHARE_KIT.md](SHARE_KIT.md)
- Submission package: [submission-package.md](submission-package.md)

This repository is intentionally static and public-safe. It shows the output and operating model without publishing private mailbox content, authenticated claim URLs, cookies, tokens, payout credentials, or banking data.

## Why It Matters

Open-source bounty work can lose payout visibility when issue tails, PRs, claim bots, and CI status change quickly. The agent keeps the contributor's active claims review-ready by preserving evidence:

- active PR link
- claim marker such as `/claim #80`
- merge and draft status
- bounty label state
- CI/check state
- latest issue/PR activity
- maintainer blockers or no-action reasoning

## Agent Loop

1. Read watcher, claim, PR, issue, CI, and inbox state.
2. Normalize each lane into structured evidence.
3. Rank by payout value, merge readiness, visibility risk, and blocker status.
4. Decide whether the correct action is comment, fix, draft, wait, or checkpoint.
5. Write a compact checkpoint so the next run resumes from current evidence.

## Quick Local Review

This is a static public-safe demo. You can inspect it without credentials:

```powershell
start index.html
start demo-dashboard.html
```

No private Gmail, cookies, tokens, payout credentials, or bank data are required.

## Architecture

See [ARCHITECTURE.md](ARCHITECTURE.md) for the decision model, no-spam guardrails, and public-safe data boundary.

## Demo Evidence

Public-safe live example:

- SecureBanana #80 evidence comment: https://github.com/SecureBananaLabs/bug-bounty/issues/80#issuecomment-4677720719
- Active PR: https://github.com/SecureBananaLabs/bug-bounty/pull/1666
- Local checkpoint: `bounty-checkpoint-2026-06-11-1152-securebanana80-yfengj-cleared.md`

The demo uses sanitized local fixtures for repeatability and does not include private Gmail, live claim URLs, cookies, bank data, payout credentials, or tokens.

## Microsoft Agents League Fit

Track: Reasoning Agents

BountyOps demonstrates multi-step tool reasoning, risk-aware action, and auditable decision making. It uses real-world GitHub/Gmail/claim signals, turns them into structured evidence, and decides when external action is warranted.

## Useful For

- open-source bounty contributors protecting claim visibility;
- maintainers who want less noisy status comments;
- AI-agent builders designing conservative action policies;
- teams building GitHub/Gmail/API operations dashboards;
- founders evaluating practical agent workflows beyond chat demos.

## Adapt This Pattern

Use the same loop for any workflow where external state changes faster than humans can track manually:

- PR/issue triage across many repositories;
- CI failure and release-readiness monitoring;
- customer-support escalation queues;
- recruiting or client-follow-up pipelines;
- compliance-style evidence capture for operational decisions.

The important constraint is the action policy: the agent should act only when the current evidence justifies the action, then record what it did.

For concrete scenarios, see [USE_CASES.md](USE_CASES.md).

## Safety Rules

- Never publish private mailbox content.
- Never include secrets, cookies, tokens, bank data, or payout credentials.
- Use public GitHub links and sanitized fixtures for demos.
- Keep public comments sparse, professional, and evidence-backed.

## License

MIT. See [LICENSE](LICENSE).
