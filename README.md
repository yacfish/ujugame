# ujugame.com

Static landing page for **UJU**, served free on [GitHub Pages](https://pages.github.com/).

- Live (project Pages): https://yacfish.github.io/ujugame/
- Custom domain (after DNS): https://ujugame.com
- Game source: https://github.com/yacfish/uju
- X: https://x.com/UjuGame

## itch.io demo

The landing page shows plain text: **Demo on itch.io — coming soon** (no link). Add a real itch URL in `index.html` when the demo is ready.

## GitHub Pages

This repo is configured for Pages from the `main` branch root. A `CNAME` file contains `ujugame.com`.

After DNS works, in the repo: **Settings → Pages → Custom domain** should show `ujugame.com`. Check **Enforce HTTPS** once the certificate is ready (can take a few minutes after DNS propagates).

## GoDaddy DNS (do this yourself)

You already own `ujugame.com` at GoDaddy. **Do not buy GoDaddy hosting.** DNS only.

In GoDaddy → **My Products** → **Domains** → `ujugame.com` → **DNS** / **Manage DNS**:

### 1. Apex / root (`ujugame.com`) — A records

Remove any conflicting A / ALIAS / forwarding records for `@`, then add these **A** records (GitHub Pages):

| Type | Name | Value | TTL |
|------|------|-------|-----|
| A | `@` | `185.199.108.153` | 600 / 1 Hour |
| A | `@` | `185.199.109.153` | 600 / 1 Hour |
| A | `@` | `185.199.110.153` | 600 / 1 Hour |
| A | `@` | `185.199.111.153` | 600 / 1 Hour |

### 2. `www` — CNAME

| Type | Name | Value | TTL |
|------|------|-------|-----|
| CNAME | `www` | `yacfish.github.io` | 600 / 1 Hour |

Notes:

- Value for www must be `yacfish.github.io` (no `https://`, usually no trailing slash).
- Propagation can take from a few minutes up to 24–48 hours.
- After DNS resolves, enable **HTTPS** in the GitHub Pages settings for this repo.

Official reference: [Configuring a custom domain for GitHub Pages](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site).

## Local preview

Open `index.html` in a browser, or from this folder:

```bash
python3 -m http.server 8000
```

Then visit http://localhost:8000
