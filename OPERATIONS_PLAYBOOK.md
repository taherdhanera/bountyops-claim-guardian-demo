# BountyOps Operations Playbook

This playbook turns the BountyOps demo into a reusable pattern for teams building conservative agents around GitHub, CI, email, and payout-style workflows.

## Who It Is For

- open-source contributors protecting bounty or grant claims
- maintainers who need fewer noisy status comments
- agent builders designing external-state monitoring loops
- founders building internal tools for recruiting, support, payments, or vendor follow-up
- engineering teams that need audit-ready decisions instead of chat-only automation

## Core Operating Rule

The agent should not act because it can act. It should act only when fresh evidence shows a real state change that creates risk or unlocks progress.

Good actions:

- fix a contributor-side blocker
- respond to a maintainer's explicit request
- preserve claim visibility after a newer same-issue submission appears
- document payment, approval, merge, or rejection evidence
- checkpoint a clean pass so the next run starts from live state

Bad actions:

- posting generic status bumps
- duplicating a prior claim comment without new evidence
- pretending payment is confirmed before it is received
- mixing private mailbox content into a public artifact
- automating account, captcha, Terms, or final-submit steps

## Evidence Model

Each monitored lane should normalize into the same small record:

| Field | Purpose |
| --- | --- |
| `source` | GitHub issue, PR, CI check, mailbox thread, claim page, or local checkpoint |
| `current_state` | Open, clean, blocked, waiting, paid, rejected, stale, or unknown |
| `owner` | Contributor-side, maintainer-side, platform-side, or external |
| `risk` | Payout risk, merge risk, visibility risk, account risk, or no risk |
| `proof` | Public URL, sanitized message summary, command output, or report path |
| `next_action` | Comment, fix, draft, wait, submit manually, or checkpoint |

The important part is not the exact schema. The important part is that every external action can be traced back to current evidence.

## Decision Loop

1. Read live aggregate state first.
2. Check the high-value lanes directly.
3. Compare latest external activity against the active claim or task.
4. Decide whether the right move is to fix, comment, draft, wait, or checkpoint.
5. Act only when the evidence justifies it.
6. Save a compact checkpoint with totals, links, blockers, and next watch points.

## Comment Policy

Public comments should be sparse and evidence-backed. A good comment includes:

- the active PR or artifact link
- the claim or task identifier
- the current merge/readiness state
- the exact newer event that created the visibility need
- no pressure language

If there is no new risk, do not comment. A clean checkpoint is better than a noisy thread.

## Private Data Boundary

Keep public demos sanitized.

Do not publish:

- mailbox bodies
- live claim URLs when they expose private account context
- cookies, tokens, API keys, wallet details, payout credentials, or bank data
- private client or employer information
- screenshots that reveal personal labels, tabs, or unrelated accounts

Use public GitHub URLs, redacted counters, synthetic fixtures, and short summaries instead.

## Adaptation Patterns

The same loop works beyond bounty claims:

- customer escalations: watch support threads, SLAs, and open engineering fixes
- recruiting: watch applications, interview replies, follow-up windows, and blockers
- vendor payments: watch invoices, approvals, bank status, and reminder thresholds
- CI/release ops: watch failing checks, stale approvals, release notes, and deploy gates
- community programs: watch submissions, review comments, winner selection, and payout evidence

## Review Checklist

Before an agent posts, sends, submits, or labels anything, verify:

- Is the state fresh?
- Is the action tied to a concrete blocker or opportunity?
- Is the owner clear?
- Is there a safer fix than a public comment?
- Is the wording professional and evidence-backed?
- Is private data excluded?
- Will this action still look reasonable to a maintainer or recruiter later?

If any answer is weak, checkpoint and wait instead of acting.
