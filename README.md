# 📦 JustDiveCol – Static Assets

This repository hosts **brand-wide static files** served from  
👉 [https://static.justdivecol.com](https://static.justdivecol.com)

These assets are shared across all JustDiveCol apps and subdomains (`www`, `shop`, `club`, `learn`, `events`, `my`, `pay`, …).

---

## 📂 Folder Structure

**/css/**

- `tokens.css` → Global design tokens (colors, spacing, radii, typography vars)
- `fonts.css` → @font-face rules loading fonts from /fonts
- `base.css` → (optional) global base styles
- `type.css` → (optional) heading scale classes

**/fonts/**

- `Montserrat-Variable.woff2`
- `Lora-Regular.woff2`
- `Lora-Bold.woff2`
- `fonts.css`
- `LICENSE.txt` → SIL Open Font License (OFL)

**/logos/**

- `logo-main.svg` → Primary logo
- `logo-white.svg` → White variant
- `favicon.ico` → Multi-size ICO for legacy browsers
- `favicon.svg` → Modern scalable favicon
- `favicon-96x96.png` → PNG fallback (96×96)
- `apple-touch-icon.png` → iOS home screen icon (180×180)
- `web-app-manifest-192x192.png` → Android/Chrome icon
- `web-app-manifest-512x512.png` → Android/Chrome icon
- `site.webmanifest` → PWA manifest referencing 192px + 512px icons

**/media/**

- `/heroes/` → Shared hero backgrounds
- `/banners/` → Campaign banners
- `/icons/` → Shared non-React icons
- `/illustrations/` → Generic SVG illustrations

**/pdf/**

- `press-kit.pdf`
- `brand-guidelines.pdf`

**/json/**

- `destinations.json` → (optional) shared content configs

---

## 🚀 How to Use in Apps

### 1. Import Fonts & Tokens

In each app’s `index.html`:

```html
<link
  rel="preconnect"
  href="https://static.justdivecol.com"
  crossorigin />
<link
  rel="stylesheet"
  href="https://static.justdivecol.com/css/fonts.css" />
<link
  rel="stylesheet"
  href="https://static.justdivecol.com/css/tokens.css?v=2025-08-25" />
```

### 2. Reference in Tailwind

In `tailwind.config.js`:

```js
extend: {
  colors: {
    brand: {
      primary: "var(--brand-primary)",
      "primary-dark": "var(--brand-primary-dark)",
      neutral: "var(--brand-neutral)",
      "cta-orange": "var(--brand-cta-orange)",
    },
  },
  spacing: {
    "section-sm": "var(--section-sm)",
    "section-md": "var(--section-md)",
    "section-lg": "var(--section-lg)",
  },
  fontFamily: {
    sans: ["var(--font-sans)"],
    serif: ["var(--font-serif)"],
  },
}
```

### 3. Favicons / Logos

In each app’s `index.html`:

```html
<!-- Modern browsers -->
<link
  rel="icon"
  type="image/svg+xml"
  href="https://static.justdivecol.com/logos/favicon.svg" />

<!-- Legacy fallback -->
<link
  rel="icon"
  href="https://static.justdivecol.com/logos/favicon.ico"
  sizes="any" />

<!-- Apple iOS -->
<link
  rel="apple-touch-icon"
  href="https://static.justdivecol.com/logos/apple-touch-icon.png" />

<!-- PNG fallback (optional) -->
<link
  rel="icon"
  type="image/png"
  sizes="96x96"
  href="https://static.justdivecol.com/logos/favicon-96x96.png" />

<!-- Web App Manifest -->
<link
  rel="manifest"
  href="https://static.justdivecol.com/logos/site.webmanifest" />
```

---

## 🔒 What NOT to put here

- ❌ Page-specific images (keep inside each app’s `/public/images`).
- ❌ Videos or large RAW images (>5MB).
- ❌ Secrets, keys, or private documents.

---

## 📜 License

- Fonts (`/fonts`) are distributed under the **SIL Open Font License (OFL)**. See [`/fonts/LICENSE.txt`](./fonts/LICENSE.txt).
- Logos, media, and other assets are © JustDiveCol. Do not reuse without permission.

---

## 🛠️ Maintenance

- Use **query string versioning** (`?v=2025-08-25`) to bust cache when updating CSS/fonts.
- Document changes in `CHANGELOG.md`.
- Optimize images with [Squoosh](https://squoosh.app/) or SVGO for SVGs.
- Test that assets load correctly over HTTPS:
  - [ ] `https://static.justdivecol.com/css/tokens.css`
  - [ ] `https://static.justdivecol.com/css/fonts.css`
  - [ ] `https://static.justdivecol.com/logos/favicon.svg`
