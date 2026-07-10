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
| `terms.html` | Terms of Service (Estonian law; B2C/B2B split) |
| `privacy.html` | Privacy Policy (GDPR) |
| `refunds.html` | Refund & cancellation policy (credits + subscriptions) |
| `contact.html` | Company details / contact / imprint |
| `styles.css` | Shared styles |
| `CNAME` | `formation.sarsa.art` (GitHub Pages custom domain) |
| `.nojekyll` | Serve files as-is |

## Deploy (GitHub Pages, same setup as sarsa.art)

1. ✅ Repo `harsaharsa/formation.sarsa.art` created and pushed to `main`.
2. ✅ Pages enabled: source `main` / root, custom domain `formation.sarsa.art`
   (read from the `CNAME` file).
3. ✅ **DNS** — at **Porkbun**: `CNAME formation` → `harsaharsa.github.io`.
4. ✅ **HTTPS enforced.** Let's Encrypt cert `CN=formation.sarsa.art`, issued
   2026-07-10, expires 2026-10-08. `http://` now `301`s to `https://`.

> **Gotcha, if this ever recurs:** GitHub requests the TLS certificate at the
> moment the custom domain is *set*. The domain was set before the DNS record
> existed, so the check failed and was **never retried** — it sat at
> `cert: none` indefinitely, not for the documented 24h. Fix: remove and re-add
> the custom domain once DNS resolves (`gh api -X PUT .../pages -F cname=null`,
> then re-`PUT` it). The site stays up and the `CNAME` file is untouched.

Still open: the domain shows `protected_domain_state: unverified`. Add a TXT
record named `_github-pages-challenge-harsaharsa` at `sarsa.art` with the token
from <https://github.com/settings/pages> to prevent subdomain takeover. (An
earlier attempt put the *record name* in as the record **value** at the apex —
delete that stray TXT.)

## Email

`harri@sarsa.art` — `sarsa.art` is a **user alias domain** on the existing
`regenesis.one` Google Workspace, so it is the same mailbox and costs no extra
seat. (A *secondary* domain would have needed a new paid user and cannot be an
alternate address for an existing one; that distinction is the whole trick.)

⬜ **Mail auth still incomplete for sending as `@sarsa.art`:**
- SPF is **missing** at `sarsa.art` — add TXT `v=spf1 include:_spf.google.com ~all`
- DMARC is missing on **both** domains — start with TXT at `_dmarc.sarsa.art`:
  `v=DMARC1; p=none; rua=mailto:harri@sarsa.art`
- DKIM is already published at `google._domainkey.sarsa.art` ✅

## Fill these before going live

No unknowns remain in the copy. The company is **not VAT-registered**, stated in
`contact.html` and `terms.html` §3. Estonian registration becomes mandatory once
taxable turnover passes **€40,000** in a calendar year (register within 3 working
days); if that happens, update both places and charge VAT at checkout.

## Legal claims and their sources (verified 2026-07-10)

Checked against primary/official sources rather than drafted from memory:

| Claim on the site | Source |
|---|---|
| Accounting records kept 7 years from end of the financial year | Accounting Act § 12, [Riigi Teataja](https://www.riigiteataja.ee/akt/110072025003) |
| Consumer Disputes Committee, free for both sides, ~90 days | [TTJA](https://ttja.ee/en/about-consumer-disputes-committee) |
| Trader must answer a consumer complaint within 15 days | [TTJA, consumer claims](https://www.ttja.ee/en/private-client/consumer-rights/consumer-rights-and-obligations/consumer-claims) |
| Withdrawal = proportionate payment for a **digital service** (not total loss of the right, which applies to *digital content* on a non-tangible medium) | CRD 2011/83 Arts 14(3), 16(m); transposed in VÕS § 56 / § 48¹ |
| VAT registration threshold €40,000 | [EMTA](https://www.emta.ee/en/business-client/taxes-and-payment/value-added-tax/registration-vat-payer/obligation-register-taxable-person) |

**Deliberately NOT cited:** the EU Online Dispute Resolution platform. It was
discontinued on 20 July 2025 (Regulation (EU) 2024/3228) and traders must remove
references to it. Most boilerplate ToS templates still link it.

Not verified against primary text: Riigi Teataja and EUR-Lex both serve
JavaScript shells to non-browser clients, so the statutory wording above was read
via search indexes of those pages and corroborating Estonian sources, not fetched
directly.

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

**DRAFT banners removed 2026-07-10** at the owner's decision, without external
counsel review. The pages were substantively tightened at the same time (B2C/B2B
split, credit-expiry commitment, EU conformity remedies, indemnity, Estonian
Consumer Disputes Committee ADR route, severability/assignment/force majeure,
GDPR security + automated-decisions statements, concrete withdrawal mechanics).
A counsel pass remains recommended before meaningful revenue — in particular the
checkout must actually implement the express-consent + acknowledgment flow that
`refunds.html` §4 describes.

## Stripe activation checklist

- [ ] Create/complete the Stripe account for **Sarsa Formation OÜ** (business
      type: company; Estonia). *(Your account + banking details — not something
      I can do for you.)*
- [x] Public business URL: `https://formation.sarsa.art` — live, HTTPS enforced.
- [x] Reachable **Terms**, **Privacy**, **Refunds**, **Contact** — live, no draft banners.
- [ ] Clear description of what's sold and the **pricing model** (prepaid
      credits and subscriptions) — done on the landing page. If you enable
      Stripe Billing, subscription cancellation and renewal terms are already
      written into `terms.html` §3 and `refunds.html` §3.
- [x] Registered business name + address matching the imprint (17290516,
      Lõõtsa tn 1a, 11415 Tallinn).
- [ ] Statement descriptor + support email (`harri@sarsa.art`).
- [ ] ⚠️ **Build the checkout consent flow before enabling billing.**
      `refunds.html` §4 promises that Stripe collects an express request for
      immediate performance plus an acknowledgment that full performance ends
      the withdrawal right. Until that exists, the page describes a thing that
      does not.

## Anthropic Startup Program checklist

- [ ] **Claude Console** account (API console, not the chat app) — use the
      company email `harri@sarsa.art`.
- [ ] Company website: `https://formation.sarsa.art` — done.
- [ ] Short "what you're building" description — the landing copy works as a base.
- [ ] Apply: <https://claude.com/programs/startups>.
- [ ] Note: credits are weighted toward **institutionally-funded** startups
      (founded < 4 years, no prior Anthropic startup credits). Your Claude usage
      via Sana/Chora is real integration evidence. Apply regardless — it's a
      ~2-minute form — but don't count on the credits until confirmed.

_Built 2026-07-10._
