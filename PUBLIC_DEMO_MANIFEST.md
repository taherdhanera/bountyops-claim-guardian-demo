# Public Demo Bundle Manifest

Prepared: 2026-06-11

## Purpose

This folder is the public-safe package for the BountyOps Claim Guardian Microsoft Agents League submission. It is designed for a public repo, hosted static demo, or review handoff without exposing private account material.

## Included Files

- `README.md` - public-facing project overview and local demo commands.
- `QUICKSTART.md` - shortest path to adapt the workflow to another agent or operations lane.
- `DEPLOYMENT.md` - deployment instructions and verified public Vercel URL.
- `index.html` - hostable static entry page for the public demo.
- `assets/bountyops-dashboard.png` - public-safe screenshot of the static demo with private totals redacted.
- `vercel.json` - static-hosting config for a Vercel deployment from this folder.
- `submission-package.md` - Microsoft Agents League submission draft for the Reasoning Agents track.
- `demo-video-script.md` - 2-3 minute demo narration and scene checklist.
- `demo-current.md` - generated sanitized report from the demo fixture.
- `demo-dashboard.html` - generated static dashboard from the demo fixture.
- `demo-watcher.json` - sanitized watcher input fixture.

## Safety Boundary

This bundle intentionally excludes:

- private Gmail message bodies and mailbox exports
- cookies, auth tokens, session data, and API keys
- bank, payout, tax, or payment-account details
- live claim URLs or authenticated payout pages
- raw Algora account pages that require login
- private local logs or screenshots containing account identity data
- non-public maintainer or contributor data

Public GitHub issue, PR, and comment URLs may be included as evidence because they are already public and relevant to the agent behavior being demonstrated.

## Verification

Current public demo:

- https://microsoft-public-demo-bundle.vercel.app
- Verified on 2026-06-11 with unauthenticated `200` and page title `BountyOps Claim Guardian`.

Regenerate the demo artifacts from the sanitized fixture:

```powershell
cd agent-prize-radar
npm run public-demo
```

Expected outputs:

- `reports/demo-current.md`
- `reports/demo-dashboard.html`
- refreshed copies in `submissions/microsoft-public-demo-bundle/`

Before publishing, confirm `npm run public-demo` passes. It refreshes the bundle, checks required files, and scans for obvious private token/key patterns.

To create a static upload archive:

```powershell
npm run public-demo:zip
```

This writes `submissions/microsoft-public-demo-bundle.zip`.
