# Automated Bagging ROI Calculator

A single-page, self-contained ROI calculator for packaging sales reps: shows the payback of
switching from hand packing to an automated bagging machine. UK English, GBP formatting,
no build step, no data storage — everything runs in the browser.

## Run locally

Just open `index.html` in a browser, or serve the folder:

```
npx serve .
```

## Deploy to Cloudflare Pages

1. Push this repo to GitHub (or GitLab):
   ```
   git remote add origin <your-repo-url>
   git push -u origin main
   ```
2. In the Cloudflare dashboard: **Workers & Pages → Create → Pages → Connect to Git**
   and select this repository.
3. Build settings:
   - **Framework preset:** None
   - **Build command:** *(leave empty)*
   - **Build output directory:** `/`
4. Deploy. Every future `git push` to `main` redeploys automatically.

## Custom domain — air.wildylabs.com

1. In the Pages project: **Custom domains → Set up a custom domain** and enter
   `air.wildylabs.com`.
2. Since `wildylabs.com` is on Cloudflare, the dashboard will offer to add the DNS
   record for you. If adding it manually instead, create in the `wildylabs.com` zone:
   - **Type:** CNAME
   - **Name:** `air`
   - **Target:** `<project-name>.pages.dev`
   - **Proxy status:** Proxied
3. Wait for the certificate to issue (usually a minute or two), then the site is live
   at https://air.wildylabs.com.
