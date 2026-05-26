# Lokose Services Group — Federal Contracting Website

Static single-page website for **Lokose Services Group**, an SBA-certified 8(a) and HUBZone small business providing grounds maintenance, painting, and waste disposal services to federal agencies nationwide.

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

## Connect Your Domain (lokoseservicesgroup.com)

1. In the Cloudflare Pages project, go to **Custom domains** → **Set up a custom domain**.
2. Enter `lokoseservicesgroup.com` and click **Continue**.
3. If your domain is already on Cloudflare DNS, it will add the CNAME automatically.
4. If your domain is with another registrar, point your DNS:
   - **CNAME** `@` → `lokose-services-website.pages.dev`
   - **CNAME** `www` → `lokose-services-website.pages.dev`
5. Wait for SSL certificate provisioning (usually under 5 minutes).
6. Update the canonical URL in `index.html` and `sitemap.xml` if your final domain differs.

## Set Up the Contact Form (Formspree)

1. Go to [formspree.io](https://formspree.io) and create a free account.
2. Click **New Form**, give it a name (e.g., "Lokose Contact"), and copy the endpoint URL.
3. In `index.html`, find this line:
   ```html
   <form class="contact-form" action="https://formspree.io/f/PLACEHOLDER_FORM_ID" ...>
   ```
4. Replace `PLACEHOLDER_FORM_ID` with your real form ID (e.g., `xpzvqkdl`).
5. Commit, push, and Cloudflare Pages will auto-deploy.

## Pre-Launch Checklist

Search for these placeholders in `index.html` and replace them before going live:

| Placeholder | Where | What to replace with |
|---|---|---|
| `PLACEHOLDER_UEI` | Hero, Contact, Footer | Your Unique Entity Identifier from SAM.gov |
| `PLACEHOLDER_CAGE` | Hero, Contact, Footer | Your CAGE Code |
| `[YOUR NAME], [TITLE]` | Contact section | Your name and title (e.g., "John Doe, President") |
| `[PHONE]` | Contact section | Business phone number |
| `+1XXXXXXXXXX` | Contact section `tel:` href | Phone number in E.164 format |
| `[ADDRESS]` | Contact section | Mailing address |
| `PLACEHOLDER_FORM_ID` | Contact form `action` attribute | Formspree endpoint ID |
| `[Commercial Property Management Firm]` | Past Performance cards (x3) | Real client names or descriptions |
| `[Service provided — ...]` | Past Performance cards (x3) | Actual service descriptions |
| `[Period of performance and outcome]` | Past Performance cards (x3) | Real dates and outcomes |

**Tip:** Run a global search for `PLACEHOLDER` and `[` (opening bracket) to catch them all.

## File Structure

```
├── index.html        Main page — all sections
├── styles.css        Design system + responsive styles
├── script.js         Mobile nav toggle (vanilla JS)
├── robots.txt        Crawler permissions
├── sitemap.xml       Sitemap for search engines
├── assets/           Images (empty — add logo, photos)
└── README.md         This file
```

## Tech Stack

- Plain HTML, CSS, vanilla JavaScript — no frameworks, no build step
- Google Fonts (Merriweather + Source Sans 3)
- Inline SVG icons — no external icon library
- Inline SVG favicon
- Contact form via [Formspree](https://formspree.io)
- Fully responsive (mobile, tablet, desktop)
- Accessible: semantic HTML, ARIA attributes, focus-visible states, skip link
