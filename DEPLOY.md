# Deploying onticllc.com via Cloudflare Pages

## 1. Connect GitHub to Cloudflare
- Log in to https://dash.cloudflare.com
- Go to Workers & Pages → Create → Pages → Connect to Git
- Select the `ryan5hanahan/onticllc-website` repository
- Build settings: Framework preset = None, Build command = (leave empty), Build output directory = /
- Click "Save and Deploy"

## 2. Add Custom Domain
- After first deploy, go to the project → Custom domains → Add custom domain
- Enter: onticllc.com
- Cloudflare will auto-configure DNS if the domain is already on Cloudflare
- If the domain is NOT on Cloudflare DNS yet:
  - Transfer DNS to Cloudflare, OR
  - Add a CNAME record: onticllc.com → <your-project>.pages.dev

## 3. SSL/HTTPS
- Cloudflare auto-provisions HTTPS — no cert management needed
- Full (Strict) SSL mode recommended

## 4. Updating the site
- Push to the `master` branch of this repo
- Cloudflare auto-deploys within ~30 seconds
