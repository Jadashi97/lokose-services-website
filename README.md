# Lokose Services Group — Federal Contracting Website

Static single-page website for **Lokose Services Group LLC**, a minority-owned small business providing grounds maintenance, painting, and waste disposal services to federal agencies nationwide. Registered in SAM.gov (UEI: W1V5K5LCWFW7) and self-certified as a Small Disadvantaged Business (SDB) under FAR 52.212-3.

## Preview Locally

No build step required. Open `index.html` directly in a browser, or serve with any static server:

```bash
python3 -m http.server 8080
# then open http://localhost:8080
```

## Deploy to Cloudflare Pages

1. Push this repo to GitHub (already done — `Jadashi97/lokose-services-website`).
2. Log in to [Cloudflare Dashboard](https://dash.cloudflare.com/) and go to **Workers & Pages**.
3. Click **Create application** → **Pages** → **Connect to Git**.
4. Select the `lokose-services-website` repository and the `main` branch.
5. Leave the build settings empty — no framework, no build command, output directory is `/` (the repo root).
6. Click **Save and Deploy**. Cloudflare will assign a `*.pages.dev` URL.

## Connect Your Domain (lokoseservicesgroup.com — registered at Porkbun)

1. In the Cloudflare Pages project, go to **Custom domains** → **Set up a custom domain**.
2. Enter `lokoseservicesgroup.com` and click **Continue**.
3. In the Porkbun dashboard, open the domain's **DNS Records** and add:
   - **CNAME** `@` (root) → `lokose-services-website.pages.dev`
   - **CNAME** `www` → `lokose-services-website.pages.dev`
4. Wait for SSL certificate provisioning (usually under 5 minutes).
5. The canonical URL in `index.html` and `sitemap.xml` already points to `https://lokoseservicesgroup.com/`.

## Contact Form

The contact form posts to a live [Formspree](https://formspree.io) endpoint (`https://formspree.io/f/xlgvapvr`). Submissions are delivered to the email address configured in the Formspree dashboard. No further setup needed.

## File Structure

```
├── index.html        Main page — all sections
├── styles.css        Design system + responsive styles
├── script.js         Mobile nav toggle (vanilla JS)
├── robots.txt        Crawler permissions
├── sitemap.xml       Sitemap for search engines
├── assets/
│   ├── logo.svg      Circular badge logo (header)
│   └── favicon.svg   Favicon version of the badge
└── README.md         This file
```

## Tech Stack

- Plain HTML, CSS, vanilla JavaScript — no frameworks, no build step
- Google Fonts (Merriweather + Source Sans 3)
- Inline SVG icons — no external icon library
- SVG logo and favicon (`assets/`)
- Contact form via [Formspree](https://formspree.io)
- Fully responsive (mobile, tablet, desktop)
- Accessible: semantic HTML, ARIA attributes, focus-visible states, skip link
