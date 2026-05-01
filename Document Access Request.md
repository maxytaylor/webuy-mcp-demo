# weBuy Checkout — Engineering Constraints & Sprint Context

**Last updated:** 2025-04-28  
**Owner:** @max-taylor (Platform Engineering)

---

## Current Sprint Capacity

- **Available eng days for checkout experiments:** 2 days
- **Sprint end:** 2025-05-09
- **Active work that may conflict:** Payment gateway migration (do not touch `checkout/payment/` during sprint)

---

## Coupon & Discount Component

### What's available
- Coupon drawer component was refactored in **v2.3.1** (shipped 2025-04-01)
- Now supports **animated reveal** on coupon apply — previously static
- Discount logic supports: flat %, item-specific %, and rhyme-based promotional codes (yes, really)
- Coupon codes are validated server-side; client gets success/fail response within ~200ms

### Known issues
- `coupon_drawer_close` event **not reliably firing on mobile Safari 16.x** — affects ~8% of sessions
- Auto-apply on page load causes flicker on slow connections (3G) — flagged but not prioritised
- Rage clicks recorded on coupon field when code is invalid — users retry without clearing field first

### Recommendation for experiment scope
> Scope any coupon UX experiment to **desktop only** for this sprint to avoid the Safari edge case contaminating results. Mobile can follow in the next cycle once the event firing bug is resolved.

---

## Checkout Flow — Recent Changes

| Version | Date | Change |
|---|---|---|
| v2.3.1 | 2025-04-01 | Coupon drawer animated reveal |
| v2.3.0 | 2025-03-18 | Checkout colour scheme experiment scaffolding added |
| v2.2.9 | 2025-03-04 | Cart quantity update optimistic UI |
| v2.2.7 | 2025-02-14 | Remove from cart confirmation modal removed (A/B test concluded) |

---

## Experiment Infrastructure

- Experiments are configured via Mixpanel Experiments — no feature flag system currently in place
- Variant assignment happens client-side on `View Checkout` event fire
- **Do not run more than 2 simultaneous checkout experiments** — variant assignment conflicts observed in v2.2.x
- Minimum detectable effect for Purchase Completed: ~3.5% given current traffic volumes

---

## Contacts

| Area | Owner |
|---|---|
| Coupon component | @sarah-chen |
| Checkout flow | @james-park |
| Experiment infra | @max-taylor |
