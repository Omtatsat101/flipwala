---
type: code-review
priority: high
from: claude
created: 2026-04-07
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
