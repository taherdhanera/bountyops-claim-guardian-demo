# Microsoft Agents League Submission Package: BountyOps Reasoning Agent

## Target

- Event: Microsoft Agents League Hackathon
- Track: Reasoning Agents
- Prize pool: USD 55,000
- Registration deadline: 2026-06-12 12:00 PM PT
- Submission deadline: 2026-06-14 11:59 PM PT
- Source: https://info.microsoft.com/Agents-League-Hackathon-Registration.html
- Live verification: official page still lists the June 12 registration deadline, June 14 project deadline, and USD 55,000 prize pool as of 2026-06-11.

## Submission Name

BountyOps Claim Guardian

## One-Line Pitch

An autonomous reasoning agent that protects open bounty payouts by monitoring Gmail, GitHub, and claim pages, ranking merge risk, and producing evidence-backed maintainer updates only when a real payout blocker appears.

## Problem

Open bounty work gets lost when maintainers, competitors, claim bots, CI systems, and payout dashboards move faster than a single contributor can track. The expensive failure mode is not missing code; it is missing the moment a clean, rewardable PR becomes hidden behind a newer competitor, bad claim marker, failing check, or unanswered maintainer request.

## Agent Behavior

1. Watch active bounty claims and payout pages.
2. Read GitHub issue/PR tails for maintainer, competitor, CI, and claim marker changes.
3. Search Gmail for notification and payout alerts.
4. Rank items by payout amount, merge urgency, and claim visibility risk.
5. Decide whether to act, watch, or skip.
6. Generate a compact evidence packet with PR state, claim marker, latest external activity, blocker, and next action.
7. Post a public status refresh only when the evidence shows a real visibility gap or contributor-side blocker.
8. Update a local audit trail and dashboard.

## Why It Fits Reasoning Agents

- Multi-step reasoning: combines payout value, PR state, issue-tail chronology, claim markers, CI, and Gmail signals.
- Tool use: uses CLI, GitHub, Gmail, and local evidence logs.
- Risk-aware action: avoids spam by acting only when latest external activity creates a visibility or blocker gap.
- Auditable decisions: every action is linked to commands, URLs, timestamps, and generated checkpoints.

## Demo Flow

### Scene 1: Protected Pipeline

Show `agent-prize-radar/reports/dashboard.html` with:

- Confirmed pending total.
- Including-upside total.
- Action-needed count.
- Open PR sweep status.
- Ranked expansion lanes.

### Scene 2: Hot Signal Arrives

Use a recorded or replayed example from SecureBanana #80:

- Gmail/GitHub detects a newer competitor `/attempt #80` from @YfengJ on 2026-06-11.
- Agent verifies our PR #1666 is open, non-draft, and claim-marked.
- Agent checks issue tail and competitor PR.
- Agent decides a concise tail refresh is warranted.

### Scene 3: Evidence-Backed Action

Show the generated public comment:

- https://github.com/SecureBananaLabs/bug-bounty/issues/80#issuecomment-4677720719

Then show the checkpoint:

- `bounty-checkpoint-2026-06-11-1152-securebanana80-yfengj-cleared.md`

### Scene 4: No-Action Reasoning

Show a clean pass:

- Watcher action-needed count is 0.
- Gmail has no current actionable alert.
- Hot issue tails are latest from us.
- Agent skips public comments and moves to expansion planning.

### Scene 5: Expansion Ranking

Show `agent-prize-radar/reports/current.md` ranking:

1. Microsoft Agents League
2. Google Cloud Rapid Agent
3. UiPath AgentHack

Explain that protected payouts stay first, then new work is selected by payout, deadline, fit, effort, and risk.

## Current Evidence Artifacts

- Dashboard: `agent-prize-radar/reports/dashboard.html`
- Ranked report: `agent-prize-radar/reports/current.md`
- Machine action log: `agent-prize-radar/reports/action-log.json`
- Watcher snapshot: `watch-logs/bounty-watch-current.json`
- Latest expansion verification checkpoint: `bounty-checkpoint-2026-06-11-1201-clean-watch-upwork-feed-corrected.md`
- Latest #80 counter checkpoint: `bounty-checkpoint-2026-06-11-1152-securebanana80-yfengj-cleared.md`

## Submission Assets Needed

- Public repo or branch containing:
  - `agent-prize-radar/`
  - watcher scripts
  - generated report/dashboard/action-log examples
  - selected anonymized or public GitHub evidence links
- Hosted project URL:
  - https://microsoft-public-demo-bundle.vercel.app
  - Public Vercel access verified on 2026-06-11 with unauthenticated `200` and page title `BountyOps Claim Guardian`.
- Demo video:
  - Target length: 2-3 minutes.
  - Show the five demo scenes above.
  - Script: `submissions/microsoft-demo-video-script.md`
- Registration/action kit:
  - `submissions/microsoft-agents-league-registration-action-kit-2026-06-11.md`
- README:
  - Draft: `submissions/microsoft-public-demo-readme.md`
  - Covers problem, agent loop, tools, evidence policy, and local run commands.

## Build Checklist

- [ ] Create a clean public demo repo or branch.
- [x] Add a README focused on the Reasoning Agents track.
- [x] Add sample sanitized watcher input/output fixtures.
- [x] Add `npm run demo` command that regenerates report and dashboard from fixtures.
- [x] Add `npm run public-demo` command that refreshes and validates the hostable bundle.
- [x] Add `npm run public-demo:zip` command that creates a static upload archive.
- [x] Assemble local public-safe demo bundle at `submissions/microsoft-public-demo-bundle/`.
- [x] Add a hostable static demo entry page at `submissions/microsoft-public-demo-bundle/index.html`.
- [x] Host public static demo on Vercel.
- [x] Draft a 2-3 minute demo script.
- [x] Draft a public demo README.
- [ ] Record a 2-3 minute demo.
- [ ] Register for Microsoft Agents League before 2026-06-12 12:00 PM PT.
- [ ] Submit before 2026-06-14 11:59 PM PT.

## Local Commands

```powershell
cd agent-prize-radar
npm run rank:json
npm run report
npm run dashboard
npm run action-log
```

## Risk Notes

- Do not include private Gmail content, tokens, bank data, cookies, or payout credentials.
- Use public GitHub issue and PR URLs for evidence.
- Keep public comments professional and sparse.
- Make the demo replayable from fixtures if live credentials cannot be shown.
