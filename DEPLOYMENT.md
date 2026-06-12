# Deployment Notes

This folder can be deployed as a static site.

## Refresh Before Deploy

From `agent-prize-radar`:

```powershell
npm run public-demo
```

This regenerates the sanitized demo report and dashboard, refreshes the bundle copies, checks required files, and scans for obvious token/key patterns.

## Vercel

Production deployment is live and public:

- Stable project URL: https://microsoft-public-demo-bundle.vercel.app
- Deployment URL: https://microsoft-public-demo-bundle-nz7adcmd9-taherdhaneras-projects.vercel.app
- Verified public access: 2026-06-11, unauthenticated `200`, title `BountyOps Claim Guardian`

The folder includes `vercel.json`, so deploy from this directory:

```powershell
cd submissions/microsoft-public-demo-bundle
vercel --prod
```

Use the stable Vercel project URL as the Microsoft Agents League project URL.

## Zip Upload

If direct CLI deployment is unavailable, create a static upload archive:

```powershell
cd agent-prize-radar
npm run public-demo:zip
```

Archive output:

- `submissions/microsoft-public-demo-bundle.zip`

Upload the zip contents to any static host. The entry point is `index.html`.

## Alternative Static Hosts

This bundle can also be uploaded to GitHub Pages, Netlify, Cloudflare Pages, or any static file host. The entry point is `index.html`; no server or build step is required after `npm run public-demo` has refreshed the bundle.
