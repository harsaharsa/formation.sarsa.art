# formation.sarsa.art

Static site for **Sarsa Formation OÜ**, leading with **Chora**. Built to serve
two goals: pass a **Stripe** business review and support an **Anthropic Startup
Program** application. Warm "Sana" visual language (cream paper, warm ink, sage /
terracotta / brass; Cormorant Garamond · Newsreader · Work Sans) reusing the Sana
glasses sigil.

## Files

| File | Purpose |
|------|---------|
| `index.html` | Chora landing — what it is, the Sana lesson, built on Claude, access & pay-as-you-go pricing, company imprint |
| `terms.html` | Terms of Service — **DRAFT** |
| `privacy.html` | Privacy Policy (GDPR) — **DRAFT** |
| `refunds.html` | Refund Policy — **DRAFT** |
| `contact.html` | Company details / contact — **DRAFT** |
| `styles.css` | Shared styles |
| `CNAME` | `formation.sarsa.art` (GitHub Pages custom domain) |
| `.nojekyll` | Serve files as-is |

## Deploy (GitHub Pages, same setup as sarsa.art)

1. Create the repo `harsaharsa/formation.sarsa.art` and push this folder to `main`.
2. Repo **Settings → Pages** → Source: `main` / root. Custom domain: `formation.sarsa.art` (the `CNAME` file already sets this).
3. **DNS** (at whoever hosts sarsa.art's DNS): add a `CNAME` record
   `formation` → `harsaharsa.github.io`. Wait for it to resolve, then tick
   *Enforce HTTPS* in Pages.

## Fill these before going live

- **Registry code** (registrikood) — in the imprint, `terms.html`, `privacy.html`, `contact.html`.
- **Registered office address** — same places.
- **VAT number** — `contact.html`, if registered.
- **Liability cap window** — `terms.html` §8 (`[3 / 6 / 12]` months).
- **Retention periods / sub-processors / cookie notice** — `privacy.html`.
- **Withdrawal-right days & response SLA** — `refunds.html`.
- Then **remove the DRAFT banners** and get the legal pages reviewed by
  Estonian/EU counsel.

## Stripe activation checklist

- [ ] Create/complete the Stripe account for **Sarsa Formation OÜ** (business
      type: company; Estonia). *(Your account + banking details — not something
      I can do for you.)*
- [ ] Public business URL: `https://formation.sarsa.art`.
- [ ] Reachable **Terms**, **Privacy**, **Refunds**, **Contact** — done (finalise drafts).
- [ ] Clear description of what's sold and the **pricing model** (usage-based
      prepaid credits) — done on the landing page.
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
