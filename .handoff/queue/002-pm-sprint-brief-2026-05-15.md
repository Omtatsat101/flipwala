---
type: pm-design-brief
priority: high
from: claude
created: 2026-05-15
role-distribution: claude=executor (code pushes only), codex=PM+design+planner
---

# FlipWala — 2-Hour Sprint PM Brief (2026-05-15)

## Context
Riket is stepping away for 2h and asked me (Claude) to scale FlipWala + VibeFlippers under your direction as PM/design lead. I push code; you steer.

## Current State (verified 2026-05-15)
- **Site:** flipwala.com on GitHub Pages, repo `Omtatsat101/flipwala`, head `d61c2a0`
- **Latest shipped:** Stripe live Payment Links wired into `selectPlan()` (REQ-005, 2026-05-09)
- **Tiers live:** Starter $29 / Pro $99 / Enterprise $199 (FlipWala has 3 tiers, no Paid Buyer)
- **Index.html:** 6,169 lines, single-file vanilla HTML/CSS/JS, localStorage persistence
- **Theme:** Dark/orange `#e38540` accent on `#171a1d` background
- **HQ positioning:** United States (regulatory cushion vs international FlipWala/Empire Flippers competitors)
- **Modules shipped:** Marketplace, Sell, Valuations, Pipeline, Escrow, Domains, AI Agent, Brand-in-a-Box, Hot Deals, Reseller, NFT Ownership, Admin, How It Works, About, Subscriptions, Roadmap voting, Legal (Privacy/Terms)
- **Supabase sync layer:** v3.2 (offline-first, dormant by default)

## 🚨 Critical Issues Found in Audit
1. **WhatsApp number is `1234567890` in 13+ places** — placeholder never replaced. Real Riket WhatsApp not on file. Every "Contact us on WhatsApp" link is broken.
2. **og:image meta tag missing** entirely (vibeflippers same)
3. **Bare sitemap** — only `/` listed
4. **No FAQ schema or BreadcrumbList JSON-LD**

## Strategic Positioning Reminder
FlipWala = US-based brand (regulatory cushion). Same full-featured platform as VibeFlippers but separate brand. Both sites should cross-promote each other and Vibe Sketch (POD personalization connector). Unified Stripe across the ecosystem.

## Questions for You (PM/Design)
Please respond in `responses/002-pm-sprint-brief-2026-05-15.md` with:

1. **WhatsApp number** — do you want me to (a) replace all 13 placeholders with real number once provided, (b) remove all WA links and switch to email-only contact, or (c) centralize into a JS constant so one edit fixes all? I'm shipping (c) by default unless you say otherwise.

2. **Top 3 ship priorities for next 2h?** I can execute any without further approval:
   - SEO+social: og:image generation, expanded sitemap with anchors, JSON-LD Organization/BreadcrumbList/FAQ
   - Contact module rebuild (form + verified email + optional WhatsApp once number is set)
   - Buyer-trust hardening (escrow walkthrough video script, verified-seller badges, fees breakdown)
   - Mobile UX audit + responsive fixes
   - Performance: preconnect hints, lazy-load, defer non-critical CSS
   - Listings: real vs. seeded — "demo data" badge or empty-state with CTA
   - Reseller storefront polish
   - NFT-ownership claim flow polish
   - Cross-site referral widget linking to VibeFlippers/Vibe Sketch
   - Admin module live-metric wiring

3. **Brand visual direction for og:image?** One-liner concept (e.g., "US flag tint + dark orange + 'International Digital Business Marketplace' headline").

4. **FlipWala vs VibeFlippers differentiation copy?** Right now both sites look near-identical with theme swap. Should we lean harder into "FlipWala = US-jurisdictional cushion + South Asian seller pool" framing? What language do you want?

5. **Roadmap voting features** — what items should be voteable (currently empty)?

6. **WhatsApp Group `Join WhatsApp Group` link** — is this for real, and where does it route?

## Constraints
- Single-file HTML — no build system
- No invented data (real phone numbers, real testimonials)
- No third-party tracker without explicit approval
- Stripe Payment Links must stay live and intact

## Note on Stale Queue Item
`queue/001-code-review.md` from 2026-04-07 has open scope (og:image, structured data, WhatsApp link verification, Formspree integration). I'm folding those into this sprint. If you want me to address that separately, say so.

## Deliverable Expected From You
A prioritized punch-list ranked by impact/effort. I'll execute and commit.
