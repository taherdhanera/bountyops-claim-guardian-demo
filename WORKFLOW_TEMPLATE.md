# Agent Operations Workflow Template

Use this template when adapting BountyOps Claim Guardian to another long-running workflow such as bounty claims, recruiting follow-ups, vendor payments, support escalations, or release readiness.

## Mission

Track changing external state, identify real blockers or opportunities, act only when current evidence justifies it, and leave an audit trail that a human can review later.

## Lane Record

```json
{
  "lane": "github-pr-123",
  "source": "GitHub PR",
  "current_state": "open-clean-waiting-review",
  "owner": "maintainer-side",
  "risk": "payout-review-delay",
  "proof": "https://github.com/org/repo/pull/123",
  "last_checked": "2026-06-21T08:30:00+05:30",
  "next_action": "watch",
  "reason": "No failed checks, no requested changes, no newer same-issue visibility gap."
}
```

## Ranking Formula

Rank lanes by:

1. Cash or business value.
2. Whether the next action is contributor-owned.
3. Whether a maintainer, recruiter, customer, or payment processor is waiting.
4. Whether a newer competitor or same-issue event creates visibility risk.
5. Whether the action can be completed without noisy repetition.

## Action Matrix

| Evidence | Correct action |
| --- | --- |
| Failing CI owned by you | Fix, test, push, then document the fix. |
| Maintainer requested a specific change | Implement the narrow change and reply with proof. |
| Newer same-issue competitor activity appears | Post one concise visibility comment with active PR, claim, and current state. |
| Payment or approval email arrives | Save evidence privately, update totals, and follow the payment instructions. |
| Clean PR with no new event | Do not comment. Save a checkpoint. |
| Application follow-up window opens | Draft a short professional follow-up for manual review or send if explicitly authorized. |
| Terms, captcha, account creation, or final submit is required | Stop for manual human action. |

## Public Comment Shape

```text
/claim #123

Visibility refresh after newer same-issue activity:
- Newer event: <public link>
- My active submission remains: <PR or artifact link>
- Current state: open, non-draft, clean/mergeable, claim marker present, no failing checks

No contributor-side change is pending from my side unless maintainers request a targeted revision.
```

Use this only when a fresh event creates a real visibility need.

## Checkpoint Shape

```markdown
# Operations Checkpoint - YYYY-MM-DD HHMM

## Totals
- Confirmed pending: USD X
- Unconfirmed upside: USD Y
- Paid received today: USD Z

## Live Sweep
- Gmail/payment: clear or details
- GitHub hot lanes: clear or details
- Claim pages: clear or details
- Competitor visibility gaps: count and links

## Actions Taken
- Link or file path
- Why it was justified

## Do Not Act
- Noisy comment targets
- Manual-submit or Terms/captcha boundaries

## Next Watch Points
- Highest value lane
- Nearest follow-up window
- Any known blind spot
```

## Safety Rules

- Do not invent stars, approvals, payments, interviews, or usage.
- Do not publish private mailbox content or payout data.
- Do not automate Terms acceptance, captcha, account creation, or final submits.
- Do not post generic bumps.
- Prefer a useful fix or a clean checkpoint over a public comment.
