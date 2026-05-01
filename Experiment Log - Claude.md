# weBuy Experiment Results Log

A running log of completed experiments on the weBuy checkout and purchase funnel.  
Maintained by the Growth team. Update within 48hrs of concluding an experiment.

---

## 2025 Q1

### EXP-014 — Remove from Cart Confirmation Modal
**Status:** Concluded ✅ Shipped  
**Hypothesis:** Removing the confirmation modal on cart item removal reduces friction and increases checkout rate  
**Primary metric:** Checkout Started  
**Result:** +6.2% lift, statistically significant (p < 0.01). Shipped in v2.2.7.  
**Notes:** No meaningful impact on accidental removal rate — concern was unfounded.

---

### EXP-013 — Auto-Apply Highest Available Discount
**Status:** Concluded ⚠️ Not shipped  
**Hypothesis:** Automatically applying the best available discount code on checkout load increases purchase conversion  
**Primary metric:** Purchase Completed  
**Result:** +4.1% lift, statistically significant. **Not shipped** — Finance flagged margin impact at scale. Estimated -£180k/month revenue at current volumes.  
**Notes:** Lift was real. Business decision not to ship. Revisit if margin profile changes. Do not re-run without Finance sign-off.

---

### EXP-012 — Inline Coupon Field (replacing drawer)
**Status:** Concluded ❌ No lift  
**Hypothesis:** Moving the coupon input inline (below order summary) vs. behind the drawer would increase coupon usage and conversion  
**Primary metric:** Coupon Applied Successfully → Purchase Completed  
**Result:** No significant lift. Coupon usage actually dropped 12% — users didn't notice the inline field. Drawer pattern has stronger visual affordance.  
**Notes:** Session replays showed users scanning for the drawer and not registering the inline field. Stick with drawer pattern.

---

## 2024 Q4

### EXP-011 — Urgency Timer on Checkout ("Items in your cart are reserved for 10 mins")
**Status:** Concluded ❌ Negative result — rolled back  
**Hypothesis:** Urgency timer would reduce checkout abandonment  
**Primary metric:** Purchase Completed  
**Result:** -2.3% on Purchase Completed, +18% on Support Chat Message (users asking if items were actually removed). Rolled back after 4 days.  
**Notes:** Caused more anxiety than urgency. Avoid artificial scarcity mechanics on this user base.

---

### EXP-010 — Checkout Colour Scheme (Control vs. 4 variants)
**Status:** Concluded ✅ Variant D shipped  
**Hypothesis:** Colour scheme affects trust signals and completion rate at checkout  
**Primary metric:** Purchase Completed  
**Result:** Variant D (high contrast, muted tones) +3.1% vs Control. Shipped in v2.3.0.  
**Notes:** Variants A and C showed no lift. Variant B negative on mobile. Colour matters more than expected.

---

## Current Hypotheses (not yet in experiment)

- **Coupon reveal animation** — animated reveal of savings amount before confirming purchase may increase emotional engagement and reduce abandonment. Builds on v2.3.1 capability. Leading candidate for next sprint.
- **Progress indicator at checkout** — showing step 1 of 2 may reduce drop-off at payment details step
- **Social proof on cart page** — "X others bought this today" — low eng effort, worth a quick test
