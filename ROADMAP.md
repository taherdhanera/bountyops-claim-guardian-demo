# Roadmap

BountyOps is a public-safe reference for reasoning-agent operations. The roadmap is intentionally practical: each item should make the workflow easier to inspect, reuse, or adapt without exposing private account data.

## Current Release

`v0.1.0-public-demo`

- Static public dashboard.
- Public-safe watcher fixture and generated report.
- Architecture notes for the agent decision model.
- Workflow template for adapting the loop.
- No-spam sharing kit and launch checklist.
- Public release with stable review links.

## Next Improvements

### 1. CLI Starter

Package the workflow template as a small local CLI that can validate a lane file and generate a checkpoint report from sanitized inputs.

Target outcome:

- `bountyops validate`
- `bountyops report`
- clear errors for missing claim links, stale timestamps, or unsafe private fields

### 2. Better Demo Evidence

Add a small set of sanitized scenarios that show how the action policy changes across states.

Useful cases:

- clean watch pass
- failed CI
- maintainer-requested change
- competitor visibility gap
- payment or claim confirmation signal

### 3. Reusable Integrations Guide

Document how the same operating loop maps to other workflows without copying private implementation details.

Priority examples:

- GitHub PR review queues
- release-readiness checks
- recruiting follow-up
- support escalation
- payment-status monitoring

### 4. Dashboard Polish

Improve scanning and trust cues in the static dashboard.

Candidate additions:

- lane age
- latest external actor
- recommended next action
- evidence freshness
- public/private data boundary marker

### 5. Safety Validators

Add checks that block common public-sharing mistakes.

Examples:

- private email bodies
- cookies or tokens
- bank or payout credentials
- local-only claim URLs
- absolute private workspace paths

## Contribution Fit

Good feedback is specific and workflow-oriented:

- what state signal is missing;
- where the action policy is too noisy or too quiet;
- which adaptation would be useful in a real team workflow;
- which demo step is unclear in the first five minutes.

Use [Demo feedback](https://github.com/taherdhanera/bountyops-claim-guardian-demo/issues/new?template=demo-feedback.yml) or [Workflow adaptation request](https://github.com/taherdhanera/bountyops-claim-guardian-demo/issues/new?template=workflow-adaptation.yml) to keep public discussion focused.
