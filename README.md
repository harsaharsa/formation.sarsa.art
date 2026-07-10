# formation.sarsa.art

Static site for **Sarsa Formation OÜ**, leading with **Chora**. Built to serve
two goals: pass a **Stripe** business review and support an **Anthropic Startup
Program** application. Warm "Sana" visual language (cream paper, warm ink, sage /
terracotta / brass; Cormorant Garamond · Newsreader · Work Sans) reusing the Sana
glasses sigil.

## Files

| File | Purpose |
|------|---------|
| `index.html` | Chora landing — what it is, the Sana lesson, built on Claude, access & pricing (prepaid credits **or** subscription), company imprint |
| `terms.html` | Terms of Service — **DRAFT** |
| `privacy.html` | Privacy Policy (GDPR) — **DRAFT** |
| `refunds.html` | Refund Policy — **DRAFT** |
| `contact.html` | Company details / contact — **DRAFT** |
| `styles.css` | Shared styles |
| `CNAME` | `formation.sarsa.art` (GitHub Pages custom domain) |
| `.nojekyll` | Serve files as-is |

## Deploy (GitHub Pages, same setup as sarsa.art)

1. ✅ Repo `harsaharsa/formation.sarsa.art` created and pushed to `main`.
2. ✅ Pages enabled: source `main` / root, custom domain `formation.sarsa.art`
   (read from the `CNAME` file).
3. ⬜ **DNS** — at **Porkbun** (where `sarsa.art` is hosted): add a `CNAME`
   record `formation` → `harsaharsa.github.io`. Once it resolves, GitHub
   verifies the domain and *Enforce HTTPS* becomes tickable.

## Fill these before going live

One real unknown remains — the rest now carry concrete values.

- **VAT number** — `contact.html` still flags "confirm VAT status." A newly
  formed OÜ under the Estonian threshold need not be VAT-registered; confirm,
  and if it is registered, add the number in `contact.html`.

Written in from the e-Business Register: **registry code 17290516**, registered
**28 July 2025**, office **Lõõtsa tn 1a, 11415 Tallinn** — across the imprint
(`index.html`, `contact.html`) and the legal pages (`terms.html`,
`privacy.html`), plus the `index.html` structured data. Chora's service hosting
(**Fly.io** compute, **Neon** Postgres) is named in `privacy.html` §3.

Decided and written in: liability cap **12 months** (`terms.html` §8);
withdrawal **14 days** and response SLA **5 business days** (`refunds.html`);
retention **12 months / 12 months / 7 years** (`privacy.html` §4). Billing
covers **prepaid credits and subscriptions** across `index`, `terms` §3, and
`refunds`.

Then **remove the DRAFT banners** — after Estonian/EU counsel reviews the four
legal pages, not before. Do not submit to Stripe while the banners are up: a
reviewer reading "not yet legally reviewed" on your Terms is a decline.

## Stripe activation checklist

- [ ] Create/complete the Stripe account for **Sarsa Formation OÜ** (business
      type: company; Estonia). *(Your account + banking details — not something
      I can do for you.)*
- [ ] Public business URL: `https://formation.sarsa.art`.
- [ ] Reachable **Terms**, **Privacy**, **Refunds**, **Contact** — done (finalise drafts).
- [ ] Clear description of what's sold and the **pricing model** (prepaid
      credits and subscriptions) — done on the landing page. If you enable
      Stripe Billing, subscription cancellation and renewal terms are already
      written into `terms.html` §3 and `refunds.html` §3.
- [ ] Registered business name + address matching the imprint.
- [ ] Statement descriptor + support email (`harri@regenesis.one`).

## Anthropic Startup Program checklist

- [ ] **Claude Console** account (API console, not the chat app) + company email.
- [ ] Company website: `https://formation.sarsa.art` — done.
- [ ] Short "what you're building" description — the landing copy works as a base.
- [ ] Apply: <https://claude.com/programs/startups>.
- [ ] Note: credits are weighted toward **institutionally-funded** startups
      (founded < 4 years, no prior Anthropic startup credits). Your Claude usage
      via Sana/Chora is real integration evidence. Apply regardless — it's a
      ~2-minute form — but don't count on the credits until confirmed.

_Built 2026-07-10._
