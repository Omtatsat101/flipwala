---
type: status-update
priority: medium
from: claude
created: 2026-05-15
related-to: 002-pm-sprint-brief-2026-05-15.md
---

# FlipWala — Sprint Status Update (Round 1, ~25 min in)

## Shipped (live on flipwala.com)
Two commits pushed: `d61c2a0 → 31a953c → bad4f80`

### v3.4: SEO + a11y pass (`31a953c`)
- og:image / twitter:image / og:image:alt / image dimensions — referencing `/og-image.svg`
- New `og-image.svg` (1200×630) — dark+orange branded card with US-HQ badge — verified live at https://flipwala.com/og-image.svg
- JSON-LD `@graph`: Organization + WebApplication + BreadcrumbList + FAQPage (4-Q FAQ schema for rich-results snippets)
- Expanded `sitemap.xml` from 1 URL → 13 URLs with section anchors + image sitemap
- `<link rel="preconnect">` to `cdn.jsdelivr.net` and `buy.stripe.com`
- `<link rel="dns-prefetch">` to `wa.me`
- `<meta name="theme-color" content="#171a1d">`
- **Accessibility:** skip-to-main-content link (focus-visible), `role="navigation"` + `aria-label="Primary"` on nav, `role="region"` on hero
- **FW_CONFIG centralized config object** (whatsappNumber, supportEmail, dmcaEmail, utm params)
- `fwWaUrl()` helper + `DOMContentLoaded` rewriter scans all `a[href*="wa.me/1234567890"]` and rebuilds href from config — **single-line edit to FW_CONFIG.whatsappNumber will fix all 13+ placeholder links site-wide**
- `fwAddUtm()` helper auto-stamps `utm_source/medium/campaign` on external links
- `rel="noopener"` auto-applied to all `target="_blank"` links (security + perf)
- `console.warn` flags if WA number is still placeholder (visible to dev tools, invisible to public)

### Sister Brands footer column (`bad4f80`)
- New "Sister Brands" column linking VibeFlippers, Vibe Sketch, KiddieSketch (with one-liner descriptors)
- Establishes ecosystem positioning from memory directly in footer
- Links auto-tagged with UTM by fwAddUtm rewriter

## Still awaiting your input (from brief 002)
1. Real WhatsApp number to plug into `FW_CONFIG.whatsappNumber`
2. Top 3 next sprint priorities
3. og:image design direction — current is a quick-pass SVG, want a revision pass?
4. Differentiation copy FlipWala vs VibeFlippers
5. Roadmap voting features
6. WhatsApp Group link real-or-placeholder

## What I'm doing while you respond
Continuing with safe objective improvements: validating JSON-LD against Google's tester, watching for live-deploy verification, planning the "demo data" badge UX for listings (waiting on Q4 answer before implementing).
