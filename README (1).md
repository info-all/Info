# GearLab — Affiliate Marketing Website

> A clean, editorial-style affiliate marketing framework for the tech & gadgets niche. Single-file HTML, no build tools, no dependencies.

**Version:** 1.0 · **Last updated:** March 2026 · **Niche:** Tech & Gadgets

---

## Table of Contents

1. [Overview](#overview)
2. [Project Structure](#project-structure)
3. [Technology Stack](#technology-stack)
4. [Design System](#design-system)
5. [Page Structure](#page-structure)
6. [Setting Up Affiliate Links](#setting-up-affiliate-links)
7. [Customisation Guide](#customisation-guide)
8. [Legal & Compliance](#legal--compliance)
9. [Deployment](#deployment)
10. [SEO Recommendations](#seo-recommendations)
11. [Potential Enhancements](#potential-enhancements)

---

## Overview

GearLab is a clean, editorial-style affiliate marketing website focused on the tech and gadgets niche. It is built as a **single-file HTML framework** — no build tools, no dependencies, no frameworks. The entire site runs directly in any modern browser.

The site is designed around a **top picks listicle format**: curated product roundups with affiliate links, star ratings, pricing, and calls to action. Revenue is generated when visitors click product links and make purchases on partner platforms such as Amazon Associates.

---

## Project Structure

The project is intentionally minimal. The core deliverable is a single HTML file containing all markup, styles, and scripts inline.

```
gearlab/
├── tech-picks.html     # Main site file — all HTML, CSS, and JS in one place
├── README.md           # This documentation file
└── assets/             # (Optional) folder for future images or icons
```

Because the framework uses no external assets or build steps, deployment is as simple as uploading `tech-picks.html` to any static hosting provider.

---

## Technology Stack

| Layer | Technology |
|---|---|
| Structure | Semantic HTML5 — `header`, `main`, `footer`, `section` |
| Styling | Vanilla CSS with custom properties (CSS variables) |
| Fonts | Google Fonts — DM Serif Display + DM Sans (via CDN) |
| Interactivity | Vanilla JavaScript — no libraries or frameworks |
| Animations | CSS keyframe animations (`@keyframes fadeUp`) |
| Hosting | Any static host — GitHub Pages, Netlify, Vercel, shared hosting |

---

## Design System

The visual design follows a clean editorial aesthetic inspired by print magazines. All design tokens are defined as CSS custom properties in the `:root` block, making global changes easy.

### Colour Palette

| Variable | Value | Usage |
|---|---|---|
| `--ink` | `#111110` | Primary text, headings |
| `--ink-2` | `#555550` | Body copy, secondary text |
| `--ink-3` | `#999990` | Captions, labels, muted text |
| `--paper` | `#f8f7f4` | Page background |
| `--paper-2` | `#eeecea` | Card backgrounds, chips |
| `--accent` | `#c84b2f` | Button hover, badges, links |
| `--accent-light` | `#f5ece9` | Accent background tints |

### Typography

| Role | Font | Usage |
|---|---|---|
| Display / Headings | DM Serif Display | Logo, hero H1, all product names |
| Body / UI | DM Sans | Body copy, labels, buttons, navigation |

---

## Page Structure

The page is divided into four semantic sections, each with a clearly defined role.

### 1. Header (sticky)
Contains the site logo and top navigation. Uses `backdrop-filter: blur` to remain readable when scrolled over content. Sticks to the top of the viewport at `z-index: 100`.

### 2. Hero
A centred editorial block with a dateline badge, large serif headline, and a single descriptive sentence. Sets the tone and context for the listicle below.

### 3. Product List (`<main>`)
The core content area. Each product is rendered as a two-column grid row: a large rank number and a product body block. The product body contains, in order:

- Category tags and editorial badges (e.g. "Best Overall")
- Star rating display and review count
- Product name in DM Serif Display
- Short editorial description (2–3 sentences)
- Feature pills row ("pros" chips)
- Price block with original price, sale price, and savings badge
- "View on Amazon" CTA button with affiliate link

### 4. Footer
Minimal single-line footer with copyright, privacy link, and affiliate disclosure link.

---

## Setting Up Affiliate Links

Each product card contains a CTA button. To activate affiliate tracking, replace the placeholder `href="#"` values with your real affiliate URLs.

### Amazon Associates

1. Sign up at [affiliate-program.amazon.com](https://affiliate-program.amazon.com) and create a tracking ID (e.g. `gearlab-20`).
2. Find the product on Amazon and use the **SiteStripe** bar to generate your affiliate link.
3. Replace `href="#"` on the relevant `<a class="btn-buy">` element with your generated link.
4. Remove the `onclick="return false;"` attribute so clicks navigate to Amazon.

**Example affiliate link format:**
```
https://www.amazon.com/dp/B0XXXXXXXX?tag=gearlab-20
```

### Other Networks

The same pattern applies to any affiliate network (Impact, ShareASale, CJ Affiliate, etc.). Replace the `href` with the network-provided deep link for each product.

---

## Customisation Guide

### Changing the colour scheme
All colours are defined as CSS custom properties in the `:root` block at the top of the `<style>` section. Edit those values to retheme the entire site instantly.

### Adding a new product card
Copy any existing `<div class="product">` block and update the rank number, tags, product name, description, pros, price, and `href`. Extend the animation delay sequence by adding:

```css
.product:nth-child(7) { animation-delay: 0.30s; }
```

### Changing the site name
The logo "GearLab" appears in two places — update both:
- The `<title>` tag in `<head>`
- The `<a class="logo">` element in the `<header>`

### Adding Google Analytics
Paste your GA4 measurement script immediately before the closing `</head>` tag. No other changes required.

### Switching fonts
Replace the Google Fonts `<link>` in `<head>` and update the `--serif` and `--sans` CSS variables in `:root`.

---

## Legal & Compliance

Affiliate marketing websites have specific legal obligations. The following are non-negotiable requirements in most jurisdictions.

### FTC Disclosure (USA)
The US Federal Trade Commission requires clear disclosure that you earn commissions from links. The included disclosure block at the bottom of the product list satisfies this requirement. **Do not remove or obscure it.**

### Amazon Associates Operating Agreement
Amazon requires the following statement to appear on any page with Amazon affiliate links:

> *"[Site name] is a participant in the Amazon Services LLC Associates Program, an affiliate advertising program designed to provide a means for sites to earn advertising fees by advertising and linking to Amazon.com."*

### Privacy Policy
If you use analytics tools (Google Analytics, etc.) or ad networks, you are required to have a privacy policy disclosing cookie usage and data collection. Link to it in the footer.

---

## Deployment

Because the site is a single static HTML file, it can be deployed anywhere that serves static files.

### Recommended Hosting Options

| Provider | Cost | Notes |
|---|---|---|
| GitHub Pages | Free | Version-controlled, custom domain support |
| Netlify | Free tier | Drag-and-drop deploy, instant HTTPS |
| Vercel | Free tier | Fast global CDN, CLI deploy |
| Shared hosting | Varies | Upload via FTP, works on any cPanel host |

### Custom Domain
Point your domain's `A` or `CNAME` record to your hosting provider. HTTPS is strongly recommended — browsers mark HTTP-only sites as "Not Secure", which hurts trust and SEO.

---

## SEO Recommendations

The HTML framework includes a basic `<title>` tag. The following improvements are recommended before launch:

- Add a `<meta name="description">` tag with a 150–160 character page summary
- Add Open Graph tags (`<meta property="og:...">`) for social sharing previews
- Use descriptive, keyword-rich product headings (already done in the template)
- Add JSON-LD structured data for `Product` schema to enable rich results in Google Search
- Submit the page URL to Google Search Console after launch

---

## Potential Enhancements

The current framework is a starting point. Future iterations could include:

- A category filter bar (e.g. Under $50 / Under $100 / Premium) powered by vanilla JS
- A price comparison table for similar products
- An email capture form linked to a newsletter service (Mailchimp, ConvertKit)
- A dark mode toggle using a CSS class swap on `<body>`
- Individual product review pages with in-depth specs and test results
- Server-side price fetching via the Amazon Product Advertising API for real-time pricing

---

## Contributing

To suggest changes or improvements, open an issue or submit a pull request. Please follow the existing code style — plain HTML, no frameworks, comments only where genuinely needed.

---

*GearLab README · v1.0 · March 2026*
