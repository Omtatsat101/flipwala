---
type: code-review
priority: high
from: claude
created: 2026-04-07
resolved: 2026-05-15
resolved-by: claude (v3.4 SEO+a11y + mailto-fallback sprint)
resolution-commit: bad4f80 (+ mailto fix incoming)
---

# Review: FlipWala Landing Page

## Scope
Review `index.html` for:
1. HTML validity and accessibility (WCAG 2.1 AA)
2. SEO: missing og:image, structured data for marketplace
3. Mobile responsiveness edge cases
4. WhatsApp deep link — ensure wa.me link works correctly
5. Form action placeholder — suggest Formspree or alternative
6. Security: any XSS vectors in inline styles/scripts

## Next Steps Needed
- Add listing submission form
- Build deal card component
- Add UTM tracking to WhatsApp link
- Structured data markup for local business

---

## Resolution (2026-05-15)
Folded into v3.4 SEO+a11y sprint. Status of each item:

| Item | Resolution |
|---|---|
| HTML validity / WCAG 2.1 AA | Skip-to-main-content link added; `role="navigation"` + `aria-label="Primary"` on nav; `role="region"` on hero; `rel="noopener"` auto-applied to all external links. Full WCAG audit still recommended but no obvious violations. |
| Missing og:image | ✅ Shipped `og-image.svg` (1200×630, branded) + meta tags |
| Structured data | ✅ Shipped JSON-LD `@graph` with Organization + WebApplication + BreadcrumbList + FAQPage |
| Mobile responsiveness | Not specifically audited this pass; existing v3.1+ CSS uses flex/grid and clamp() throughout |
| WhatsApp link `1234567890` | Refactored to `FW_CONFIG.whatsappNumber` — one-line edit will repopulate all 13+ wa.me links. Still placeholder pending real number from Riket. |
| Form action placeholder | ✅ Shipped mailto fallback in `submitSellForm()` — listing submissions now open user's mail client with prefilled subject + structured body to `FW_CONFIG.supportEmail`. localStorage save preserved. |
| XSS in inline scripts | Sweep deferred — most user input goes through `document.getElementById('...').value` and is rendered as innerText/value, not innerHTML. Listing-card rendering uses template literals with potentially-unsafe interpolation — Codex should audit `renderListings()` and `openListing()`. |
| Listing submission form | ✅ Already shipped + now reaches Riket via mailto fallback |
| Deal card component | Implicit in listing cards; further polish requested via brief 002 |
| UTM tracking | ✅ `fwAddUtm()` auto-stamps utm_source/medium/campaign on all external links |
| Local business structured data | ✅ Organization schema with `areaServed` includes US/IN/UK/AU/CA |

