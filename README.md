# SpanWatch — Landing Page

Static landing page for an **AI maintenance copilot for public infrastructure** (bridges, water systems, roads) startup. No build step, no dependencies — plain HTML/CSS/JS.

## Rebranding (company name / domain)

Edit the three values at the top of **`config.js`**:

```js
const BRAND = {
  companyName: "SpanWatch",
  domain: "spanwatch.example.com",
  contactEmail: "hello@spanwatch.example.com"
};
```

Every occurrence of the company name, domain, and email in the page is injected from this file at load time. Nothing else needs to change.

## Deploy to GitHub Pages

1. Create a new GitHub repo and push this folder's contents to it:
   ```sh
   git init
   git add .
   git commit -m "Landing page"
   git remote add origin https://github.com/<user>/<repo>.git
   git push -u origin main
   ```
2. In the repo: **Settings → Pages → Source: Deploy from a branch → `main` / `(root)`** → Save.
3. The site goes live at `https://<user>.github.io/<repo>/`.

For a custom domain, add it under **Settings → Pages → Custom domain** (GitHub creates a `CNAME` file) and point your DNS at GitHub Pages.

## Files

| File | Purpose |
|---|---|
| `index.html` | Page structure & copy |
| `style.css` | All styling (theme variables at top of file) |
| `config.js` | Brand config + injection script |

## Notes

- Theme: steel blue + safety orange, faint hazard-stripe hero with an orange bottom rule, tight corners, uppercase buttons, Barlow font (`--ink`, `--accent`, `--safety` in `style.css`).
- Hero visual is a pure HTML/CSS **asset map + live alert feed**: gridded district map with road paths and pulsing status pins, beside a triage feed (act-now / watch / resolved).
- The email form shows a confirmation message client-side; wire it to Formspree, Buttondown, or your own endpoint to actually collect emails.
- Logo is an inline SVG bridge-arch mark in `index.html` (nav + footer) — swap both `<svg class="logo-mark">` blocks to change it.
