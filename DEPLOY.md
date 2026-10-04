# Deploying onticllc.com via GitHub Pages

The site is a single static `index.html` served by GitHub Pages from the
`ryan5hanahan/onticllc-website` repository. There is no build step.

## Updating the site
- Push to the `master` branch
- GitHub Pages republishes automatically, usually within a minute or two

## Pages settings
Repository → Settings → Pages:
- Source: Deploy from a branch, `master`, `/ (root)`
- Custom domain: `onticllc.com` (also stored in the `CNAME` file; keep them in sync)
- Enforce HTTPS: on

## DNS (GoDaddy)
| Type  | Name  | Value                     |
|-------|-------|---------------------------|
| A     | @     | 185.199.108.153           |
| A     | @     | 185.199.109.153           |
| A     | @     | 185.199.110.153           |
| A     | @     | 185.199.111.153           |
| CNAME | www   | ryan5hanahan.github.io    |

`www.onticllc.com` redirects to `https://onticllc.com/`.

## HTTPS certificate
GitHub provisions and renews the certificate automatically. It covers
`onticllc.com` and `www.onticllc.com`.

If a domain is missing from the certificate (for example after a DNS change),
remove the custom domain in Pages settings, save, add `onticllc.com` back, then
re-enable Enforce HTTPS once the new certificate is issued.

The `www` record must point to `ryan5hanahan.github.io`, not to `onticllc.com`,
or GitHub will not include `www` in the certificate.
