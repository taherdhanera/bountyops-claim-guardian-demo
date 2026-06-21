# Scenarios

These public-safe scenarios show how BountyOps decides whether to watch, comment, fix, escalate, or checkpoint. They are sanitized examples for evaluating the action policy without exposing private mailbox, claim, payout, or credential data.

## Decision Matrix

| Scenario | Signal | Correct action | Why |
| --- | --- | --- | --- |
| Clean watch pass | PR is open, non-draft, mergeable, claim marker exists, no newer competitor signal | Checkpoint only | A public comment would add noise without improving payout protection. |
| Failed CI | PR is open but a required check failed | Fix first | Contributor-side blockers are higher priority than visibility comments. |
| Maintainer asks for changes | Issue or PR has a maintainer request that is still unanswered | Implement or answer directly | The payout path depends on clearing the maintainer gate. |
| New competitor visibility gap | A newer same-issue claim or PR appears after our last issue-side proof | Post one concise refresh | A focused evidence comment protects claim visibility without spam. |
| Payment or claim signal | Gmail, Algora, or claim page shows paid, approved, merged, rejected, or action-needed | Record evidence and act on the specific blocker | Payment conversion beats generic monitoring. |
| Manual account gate | A job or platform requires login, terms, captcha, or profile submission | Prepare the packet, leave final submit manual | The agent should not cross account/consent boundaries. |

## Example Lane States

### Watch Only

```json
{
  "lane": "Example bounty #12",
  "prState": "OPEN",
  "draft": false,
  "mergeState": "CLEAN",
  "claimPresent": true,
  "latestExternalSignal": null,
  "nextAction": "checkpoint"
}
```

### Fix First

```json
{
  "lane": "Example bounty #18",
  "prState": "OPEN",
  "draft": false,
  "mergeState": "DIRTY",
  "failedCheck": "api-regression",
  "nextAction": "fix-ci-before-commenting"
}
```

### Visibility Refresh

```json
{
  "lane": "Example bounty #3",
  "ourPr": "open-clean-non-draft",
  "newCompetitorSignal": "same-issue-pr-after-our-last-comment",
  "nextAction": "post-one-evidence-backed-claim-refresh"
}
```

## Comment Shape

When a visibility refresh is justified, the comment should be short and evidence-backed:

```text
/claim #123

Claim/status refresh after newer same-issue activity:
- Newer external signal: <public link>
- My active implementation PR remains open, non-draft, and mergeable/CLEAN: <public PR link>
- No maintainer-requested changes are pending from my side.
```

## What The Agent Must Not Do

- Do not post duplicate comments just because time passed.
- Do not comment before fixing a contributor-side blocker.
- Do not publish private Gmail bodies, cookies, tokens, bank data, or payout credentials.
- Do not automate account login, terms acceptance, captcha, or final application submit.
- Do not treat pending pipeline value as received cash.

## Reuse Notes

The same policy works outside bounty claims:

- recruiting follow-up: reply only when there is a stale unanswered thread or requested action;
- release readiness: fix failing checks before posting status updates;
- support escalation: escalate only when SLA, severity, or customer signal justifies it;
- payment monitoring: preserve evidence and act on the exact payout blocker.
