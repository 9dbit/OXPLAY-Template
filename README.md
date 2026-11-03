# OXPLAY Template

Version **1.0.0** — reusable responsive frontend template and visual asset archive for Playground.

This repository preserves the approved GOBI88 reference UI, local assets, catalog, responsive fixes, and browser-local demo workflows. OXPLAY Template is the template identity; the captured logo and visible reference branding remain unchanged.

## Repository roles

| Repository | Purpose |
| --- | --- |
| [OXPLAY-Template](https://github.com/9dbit/OXPLAY-Template) | Reusable template and versioned asset archive |
| [Agent-Frontend-Ui](https://github.com/9dbit/Agent-Frontend-Ui) | Active UI development and Playground engine integration |
| [Playground](https://github.com/9dbit/Playground) | Engine and admin application |

Copied with Git history from frontend commit `3513a9181f049815cc04dcc7fbcb001752a1aad0`. Keep the `v1.0.0` release as the baseline. Working frontend changes do not automatically change this independent template repository.

## Included

- 238 source images plus the local logo alias; source URLs and SHA-256 hashes in `docs/reference/asset-copy-manifest.json`.
- 85 demo games, 50 providers, 16 hero banners, 12 exclusive covers, 6 promotion posters, and the remaining hero promotion detail records.
- 131 discovered routes, mobile navigation, search, favorites, account pages, and local wallet/reward/inbox/referral/support/history simulations.
- Portrait Casino, Promotion, and Exclusive covers and account overflow fixes.
- Source, documentation, dependency lockfile, Railway configuration, and validation workflow.

## Run

Node 24 is recommended. No runtime dependencies; jsdom is only used for development tests.

```sh
npm ci
npm run build
npm test
npm start
```

Open `http://localhost:3000`. The server respects `PORT` and exposes `/health`. `/preview/` provides responsive iframe widths of 360, 393, 768, and 1440 px. This archive has no separate Railway deployment.

## Reuse

Use **Use this template** to create a new project, or clone the `v1.0.0` tag for the exact baseline. For the current Playground project, continue in `9dbit/Agent-Frontend-Ui`, which already contains the approved frontend and retains its Railway connection.

1. Set the derived project's package name and branding in `public/config.js` and `public/assets`.
2. Retain a template-origin record with the source version.
3. Keep project-specific UI and backend adapters in the derived repository.
4. Return reusable improvements through a reviewed template change and a new release.

## Demo and integration

The initial signed-in user is `playground_demo`; after logout use the sample password `demo1234`. Registration is a local simulation and discards passwords. Reset demo state from the footer.

`public/state.js` contains the local demo adapter. No authentication backend, payment gateway, provider session, source-site API, or external chat is connected. Playground must own identity, tenant scope, balances, transaction status, rewards, and sessions during integration.

See [the integration guide](docs/OXPLAY_TEMPLATE_GUIDE.md). Repository separation does not implement backend integration.

## Verified baseline

- Build and 24 automated tests passed: route rendering, asset bytes, carousel loading, promotion poster mapping, and demo account workflows.
- Live Chromium inspection on 3 November 2026 confirmed all eight account tabs at four iframe widths (360, 393, 768, 1440 px): 32 navigation checks with no horizontal document overflow.
- Portrait cover geometry was checked in Casino, Promotion, and Exclusive categories at those widths. The original GOBI88 public site was also inspected in the browser.
- Native iPhone Safari remains untested. Responsive iframe checks are not native-device certification.

Historical audit documents are retained; this section records the latest verification before template separation.

Restore source assets using `python3 scripts/restore-assets.py`. Downloads must match the committed SHA-256 manifest. Images are served locally without runtime hotlinks.
