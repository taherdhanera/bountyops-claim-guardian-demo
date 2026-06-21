# BountyOps Quickstart

Use this when you want to adapt the BountyOps pattern to your own agent workflow without reading every file first.

## 1. Pick One Operational Lane

Start with a workflow where wrong or noisy action has real cost:

- GitHub PR and CI triage
- support escalation
- recruiting follow-up
- release readiness
- payment or invoice follow-up
- bounty claim protection

Write the lane as one sentence:

```text
Watch <sources>, detect <risk>, then choose <act | draft | wait | checkpoint>.
```

Example:

```text
Watch GitHub PRs, CI, and issue comments; detect merge blockers or competitor visibility gaps; then choose fix, comment, wait, or checkpoint.
```

## 2. Define Evidence Fields

Keep the state small enough to inspect.

```json
{
  "lane": "github-pr-watch",
  "value": 700,
  "sourceUrl": "https://github.com/org/repo/pull/123",
  "state": "open",
  "mergeState": "clean",
  "latestExternalAt": null,
  "latestOursAt": "2026-06-21T15:03:19Z",
  "actionNeeded": false,
  "reason": "open, non-draft, claim visible, no newer external blocker"
}
```

Good lanes usually include:

- current state
- last checked time
- highest-risk external activity
- owner-side blocker status
- action-needed boolean
- short reason

## 3. Add A Conservative Action Policy

Agents should not act just because they can.

```text
Act only when:
- a maintainer asks for a change;
- CI or checks fail;
- a newer external event creates a real visibility or delivery gap;
- a payment, approval, or follow-up signal needs evidence.

Otherwise:
- write a checkpoint;
- keep watching;
- avoid public noise.
```

## 4. Produce A Report

Generate one scan-friendly report after each pass:

```markdown
# Current Watch

- Checked at: 2026-06-22T00:14:20+05:30
- Action needed: 0
- Highest value lane: SecureBanana #80 / PR #1666 / USD 780
- Decision: no comment; current evidence is clean

## Next Watch Points

1. Recheck high-value PRs.
2. Recheck inbox/payment signals.
3. Refresh checkpoint if nothing changed.
```

## 5. Keep A Resume Checkpoint

Checkpoint enough context for another human or agent to resume without guessing:

- what was checked
- current totals or queue counts
- links inspected
- actions taken
- actions explicitly skipped
- next watch points

## Files To Read Next

- [WORKFLOW_TEMPLATE.md](WORKFLOW_TEMPLATE.md) for a reusable schema and action matrix.
- [ARCHITECTURE.md](ARCHITECTURE.md) for the decision policy.
- [OPERATIONS_PLAYBOOK.md](OPERATIONS_PLAYBOOK.md) for adapting this to another team.
- [demo-current.md](demo-current.md) for a public-safe example report.
- [demo-dashboard.html](demo-dashboard.html) for the dashboard output.

