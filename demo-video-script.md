# Microsoft Agents League Demo Video Script

Target length: 2 minutes 30 seconds.

Project: BountyOps Claim Guardian
Track: Reasoning Agents

## 0:00-0:15 - Opening

Show `agent-prize-radar/reports/demo-dashboard.html`.

Voiceover:

"BountyOps Claim Guardian is a reasoning agent for open-source bounty operators. It monitors active payout claims, Gmail notifications, GitHub issues and PRs, and local evidence logs, then decides when to act and when to stay quiet."

## 0:15-0:40 - The Money Pipeline

Zoom on the protected pipeline metrics.

Voiceover:

"The first job is protecting money already earned or pending. The live workflow tracks confirmed pending payout, upside, claim attention, action-needed count, merge state, and whether any open bounty PR is missing from the watchlist."

On screen:

```powershell
cd agent-prize-radar
npm run demo
```

## 0:40-1:15 - Reasoning Over A Hot Signal

Show a public GitHub issue tail example and the action log.

Voiceover:

"When a competitor or maintainer comment arrives, the agent does not blindly post. It checks the issue chronology, our PR state, claim marker, mergeability, bounty label, and whether the new activity creates a visibility or blocker gap."

Show `reports/action-log.json`.

Voiceover:

"Every action has a timestamp, trigger, evidence links, and a next watch point. That makes the agent auditable instead of noisy."

## 1:15-1:50 - Evidence-Backed Action

Show a checkpoint file and public-safe example comment.

Voiceover:

"If the latest external activity hides an active clean claim, BountyOps generates a concise, evidence-backed refresh. It links the active PR, states the claim, and avoids broad claims or spam. If there is no payout risk, it records a no-action decision instead."

On screen:

- Open `reports/demo-current.md`
- Open `reports/demo-dashboard.html`
- Open a checkpoint from the live workspace

## 1:50-2:20 - Expansion Toward The Revenue Goal

Show the ranked expansion lanes.

Voiceover:

"After protecting pending payouts, the agent ranks new legitimate work by prize size, deadline, strategic fit, effort, and risk. The current best lanes are Microsoft Agents League, Google Rapid Agent, and UiPath AgentHack."

## 2:20-2:30 - Close

Return to dashboard.

Voiceover:

"BountyOps turns bounty work into a disciplined revenue operations loop: monitor, reason, act only when needed, and preserve evidence from claim to payout."

## Recording Checklist

- Use demo fixtures, not private Gmail, cookies, bank data, or payout credentials.
- Show only public GitHub URLs and local redacted/demo artifacts.
- Keep the browser zoom high enough for judges to read metrics.
- Keep terminal output focused on `npm run demo`, `npm run submission`, and generated artifacts.
- End with the dashboard and ranked expansion lanes visible.
