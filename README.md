# Lokose Services Group — Federal Contracting Website

Static single-page website for **Lokose Services Group**, an SBA-certified 8(a) and HUBZone small business providing grounds maintenance, painting, and waste disposal services to federal agencies nationwide.

## Purpose

This site serves as the company's public-facing web presence for federal contracting officers, small business specialists, and potential teaming partners. It highlights certifications, core service capabilities, NAICS codes, and past performance to support contract pursuit and capability statement requests.

## Tech Stack

- Plain HTML, CSS, and vanilla JavaScript — no frameworks, no build step
- Google Fonts (Merriweather + Source Sans 3)
- Contact form powered by [Formspree](https://formspree.io)
- Fully responsive (mobile, tablet, desktop)

## Setup

Open `index.html` in a browser, or serve locally:

```bash
python3 -m http.server 8080
```

## Placeholders to Replace

Before deploying, update these placeholders with real values:

| Placeholder | Location | Description |
|---|---|---|
| `PLACEHOLDER_UEI` | Hero, Contact, Footer | Unique Entity Identifier |
| `PLACEHOLDER_CAGE` | Hero, Contact, Footer | CAGE Code |
| `[YOUR NAME], [TITLE]` | Contact section | Point of contact |
| `[PHONE]` | Contact section | Business phone number |
| `[ADDRESS]` | Contact section | Mailing address |
| `PLACEHOLDER_FORM_ID` | Contact form `action` | Formspree endpoint ID |
| Past performance cards | Past Performance section | Real client engagements |
