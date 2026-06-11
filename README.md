# Lokose Services Group — Federal Contracting Website

Static single-page website for **Lokose Services Group LLC**, a minority-owned small business providing grounds maintenance, painting, janitorial, and waste disposal services to federal agencies nationwide. Registered in SAM.gov (UEI: W1V5K5LCWFW7) and self-certified as a Small Disadvantaged Business (SDB) under FAR 52.212-3.

## Preview Locally

No build step required. Open `index.html` directly in a browser, or serve with any static server:

```bash
python3 -m http.server 8080
# then open http://localhost:8080
```

## Deployment

The site is live at [lokoseservicesgroup.com](https://www.lokoseservicesgroup.com), deployed via **GitHub Pages** from this repo (`Jadashi97/lokose-services-website`, `main` branch). The domain is registered at Porkbun with DNS pointing to GitHub Pages; the root domain redirects to `www`.

Every push to `main` deploys automatically — no build step, no manual action needed.

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
