# BountyOps Showcase

This page is the fastest way to evaluate BountyOps Claim Guardian as a practical agent workflow reference.

## What It Shows

BountyOps demonstrates an operations agent that watches changing external state, ranks risk, acts only when evidence justifies action, and leaves a checkpoint another human or agent can resume from.

The public demo focuses on open-source bounty work, but the same pattern applies to:

- GitHub issue and PR triage;
- CI and release-readiness monitoring;
- inbox-style follow-up queues;
- payment, support, recruiting, and escalation workflows;
- long-running agent jobs that need durable state instead of memory guesses.

## Review Path

1. Open the live dashboard: https://taherdhanera.github.io/bountyops-claim-guardian-demo/
2. Scan the lane table and action queue.
3. Read the action policy in [ARCHITECTURE.md](ARCHITECTURE.md).
4. Copy the reusable lane/action shape from [WORKFLOW_TEMPLATE.md](WORKFLOW_TEMPLATE.md).
5. Check the public/private data boundary in [PUBLIC_DEMO_MANIFEST.md](PUBLIC_DEMO_MANIFEST.md).

## Why It Is Different

Most agent demos stop at a chat interface. BountyOps is built around the operational loop:

```text
live signals -> normalized evidence -> risk ranking -> action policy -> scoped action or checkpoint
```

The important part is not automation for its own sake. The important part is that the agent can explain why it acted, why it waited, and what another reviewer should check next.

## Safety Boundary

The demo is public-safe:

- no private Gmail content;
- no cookies, tokens, or credentials;
- no bank or payout-account data;
- no private claim pages or authenticated dashboards;
- no fake activity, fake stars, or engagement manipulation.

Public comments are treated as expensive actions. The policy prefers checkpoints unless there is a real blocker, failed check, maintainer request, payment signal, or claim-visibility gap.

## Reuse Examples

| Workflow | How to adapt the pattern |
| --- | --- |
| Release ops | Watch PRs, checks, deployments, owners, and release notes; checkpoint go/no-go evidence. |
| Recruiting | Watch interview threads, calendar state, portfolio proof, and follow-up windows; draft concise replies. |
| Support | Watch priority customers, incidents, account blockers, and handoffs; escalate only with evidence. |
| Bounty ops | Watch issue comments, PR state, CI, claim labels, payout signals, and competitor activity. |
| Founder ops | Watch leads, demos, contracts, invoices, and implementation blockers; rank next-money actions. |

## What To Star It For

Star or save the repo if you want a compact public reference for:

- conservative agent action policies;
- GitHub, CI, inbox, and payout-signal workflows;
- public-safe demo packaging;
- checkpoint formats for long-running agents;
- practical agent UX beyond chat.

For a ready-to-use sharing note, see [SHARE_KIT.md](SHARE_KIT.md).
