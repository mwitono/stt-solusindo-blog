# STT Solusindo Blog

Blog posts published on behalf of **Solusindo Total Teknikatama** (STT), an authorized Zoho Partner in Indonesia. Each post is a bilingual (EN/ID) single-page HTML article about Zoho, AI, and business automation.

## Structure

```
stt-solusindo-blog/
├── index.html                          ← homepage, lists all posts (newest first)
├── posts/
│   └── YYYY-MM-DD-slug/
│       ├── index.html                  ← the post itself (self-contained: inline CSS/JS)
│       └── cover.jpg                   ← hero/cover image (1600x900, from Canva)
└── README.md
```

Every post lives in its own dated folder under `posts/`, so posts never collide and old URLs never break. Each post's `index.html` is fully self-contained (all CSS and JS inline) so it can be opened, previewed, or shared as a single file.

## House style

- **Bilingual toggle**: EN/ID switch in the top nav. Implementation note: don't rely on a `lang-en`/`lang-id` class alone with `display` — CSS specificity from component classes (`.hero .tag`, `.cta-btn`, etc.) can override it and show both languages, or neither. Instead toggle a dedicated `.lang-hidden { display: none !important; }` class via JS (`el.classList.toggle('lang-hidden', ...)`), which is specificity-proof. Copy this pattern from the most recent post rather than reinventing it.
- **Brand colors**: `#E8272E` (STT red), `#1A1A2E` (navy), `#F59E0B` (amber accent).
- **Sections used across posts**: sticky nav with lang toggle, hero with cover image, stats grid (sourced), feature/capability grid, an inline SVG diagram where a concept needs illustrating, a comparison or deep-dive block, an illustrative scenario (clearly labeled as illustrative — do not fabricate specifics about named real companies unless you have verified, citable facts), a getting-started/steps section, an ROI callout, an author box, and a closing CTA.
- **Cover images**: generated via Canva (`youtube_banner` format, 1600px wide export) using a warm, candid, people-in-office photography style — see the `blog-cover-image-generator` skill for the prompt template and weekly scene rotation. Pick a different scene than the immediately preceding post if publishing more than one post in the same week.
- **Logo**: `assets/logo.png` (STT Solusindo logo, transparent PNG) goes in the nav on every page — homepage and every post. Reference it with a relative path (`assets/logo.png` from the homepage, `../../assets/logo.png` from a post). On a dark nav background, wrap it in a small white rounded chip (`background:#fff;border-radius:8px;padding:4px 10px`) so it stays legible — see any existing post's nav for the pattern to copy.

## Publishing a new post

1. Create `posts/YYYY-MM-DD-slug/` with `index.html` and `cover.jpg`.
2. Add one `.post-card` entry to the top of the list in the root `index.html` (newest first).
3. Commit and push.

## Deploying

This repo is served via **GitHub Pages** (Settings → Pages → Deploy from branch → `main` / root). The homepage is available at `https://mwitono.github.io/stt-solusindo-blog/` and each post at `.../posts/<slug>/`.

## History

Posts before 2026-09-20 lived as flat dated files in the repo root (`blog-<slug>.html` + `cover-image-<slug>.jpg`). That first post (the ERP + AI trends piece) has been relocated into `posts/2026-09-20-zoho-ai-erp-trends/` to match the structure above; its content is unchanged.
