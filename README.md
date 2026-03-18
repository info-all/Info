# GearLab — Tech Affiliate Site

A clean, minimal affiliate marketing site built with pure HTML & CSS. No frameworks, no build tools — just drop it on GitHub Pages and go live in minutes.

---

## Live Demo

> `https://your-username.github.io/gearlab`

---

## Deploy to GitHub Pages

### 1. Create a repository

Go to [github.com/new](https://github.com/new) and create a new **public** repository. Name it `gearlab` (or anything you like).

### 2. Upload the file

Add `index.html` (rename `tech-picks.html` → `index.html`) to the root of your repo. You can do this via the GitHub web UI or by cloning locally:

```bash
git clone https://github.com/your-username/gearlab.git
cd gearlab
cp /path/to/tech-picks.html index.html
git add index.html
git commit -m "Initial commit"
git push origin main
```

### 3. Enable GitHub Pages

1. Go to your repo → **Settings** → **Pages**
2. Under **Source**, select `Deploy from a branch`
3. Choose branch: `main` | folder: `/ (root)`
4. Click **Save**

Your site will be live at `https://your-username.github.io/gearlab` within ~60 seconds.

---

## Project Structure

```
gearlab/
├── index.html        ← Main page (all HTML, CSS, JS in one file)
└── README.md         ← This file
```

Everything is self-contained in `index.html` — no external dependencies beyond Google Fonts.

---

## Customisation

### Add your affiliate links

Open `index.html` and find each "View on Amazon" button. Replace `href="#"` with your actual affiliate link:

```html
<!-- Before -->
<a class="btn-buy" href="#">View on Amazon</a>

<!-- After -->
<a class="btn-buy" href="https://amzn.to/YOUR-AFFILIATE-ID" target="_blank" rel="noopener sponsored">
  View on Amazon
</a>
```

> Always use `rel="noopener sponsored"` on affiliate links — it's both a security best practice and signals to search engines that the link is commercial.

### Change branding & colours

All design tokens live in the `:root` block at the top of the `<style>` section:

```css
:root {
  --accent: #c84b2f;       /* Change to your brand colour */
  --ink:    #111110;       /* Primary text */
  --paper:  #f8f7f4;       /* Page background */
}
```

### Add or remove products

Each product card follows this pattern — copy, paste, and edit:

```html
<div class="product">
  <div class="rank">06</div>
  <div class="product-body">
    <div class="product-meta">
      <span class="tag">Your tag</span>
      <span class="stars">★★★★★</span>
      <span class="rating-count">4.9 · 1,000 reviews</span>
    </div>
    <h2>Product Name</h2>
    <p class="product-desc">Your description here.</p>
    <div class="pros">
      <span class="pro">Feature one</span>
      <span class="pro">Feature two</span>
    </div>
    <div class="product-footer">
      <div class="price-block">
        <span class="price">$99</span>
      </div>
      <a class="btn-buy" href="YOUR_AFFILIATE_URL" target="_blank" rel="noopener sponsored">
        View on Amazon
      </a>
    </div>
  </div>
</div>
```

---

## Legal & Compliance

### FTC Disclosure (required)
The affiliate disclosure block is already included in the page footer area. Do **not** remove it — US law (FTC guidelines) requires clear disclosure whenever you earn commissions from links.

### Amazon Associates
If using Amazon affiliate links, ensure your disclosure mentions Amazon specifically. The included text already covers this. Review the [Amazon Associates Operating Agreement](https://affiliate-program.amazon.com/help/operating/agreement) for full requirements.

### GDPR / Privacy
If you add analytics (e.g. Google Analytics), you'll need a cookie consent banner and a Privacy Policy page. GitHub Pages doesn't set cookies itself.

---

## Optional Enhancements

| Enhancement | How |
|---|---|
| Custom domain | Repo → Settings → Pages → Custom domain |
| Analytics | Add Google Analytics `<script>` before `</head>` |
| More pages | Add `reviews.html`, `deals.html` and link them in `<nav>` |
| SEO meta tags | Add `<meta name="description">` and Open Graph tags inside `<head>` |
| Sitemap | Create `sitemap.xml` and submit to Google Search Console |

---

## License

This project is released for personal and commercial use. Swap out all placeholder product data and affiliate links before going live.
