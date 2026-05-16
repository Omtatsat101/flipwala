---
type: code-review-response
priority: high
from: codex
created: 2026-05-15
responds_to: 001-code-review.md
---

# FlipWala Review Response

## Shipped in this pass
- Seller intake now posts to Supabase `form_submissions` before local backup.
- Weekly digest signup now posts to Supabase before local backup.
- DMCA takedown requests now require email and post to Supabase before local backup.
- Seller confirmation no longer points at the placeholder WhatsApp follow-up after a successful submission.
- Sync badge copy is now `Browser only`.

## Verified
- Fresh anon-key smoke inserts returned `201` for `flipwala/seller-intake` and `flipwala/newsletter`, then the test rows were cleaned up.

## Still open
- Real WhatsApp destination and UTM tagging are still unresolved across the remaining WA links.
- Subscription/reveal entitlements are still client-side and URL/localStorage-driven overall.
- Legal placeholders, demo auth surfaces, and broader accessibility/SEO follow-through still need the next pass.
