# CLAUDE.md

Context for Claude Code sessions working on this repository.

## What this is

Website + business build-out for **Brownell Energy Law** — Stephen Brownell's
planned solo practice serving small power-sector companies (developers, IPPs,
C&I solar operators) that find big-firm rates prohibitive and a full-time GC
premature. Stephen is a 40-year energy GC (currently GC at Trail Ridge Power);
he also runs settingstonelegal.com (separate repo, `settingstone-legal`), a
free tool chest for energy attorneys that serves as top-of-funnel for this
practice.

Live site: <https://attorneybrownell.github.io/brownell-energy-law/>
(GitHub Pages, deployed from `main` by `.github/workflows/deploy.yml`;
static, no build step; push to `main` = deploy).

## The business model — decisions locked with Stephen

- **No hourly billing, ever.** Value pricing only. Core premise: clients pay
  for judgment; an AI toolchain (Claude) manufactures the deliverables.
- **Two tiers per service** (this naming is settled — do not revert to the
  earlier "Counsel Kits" brand):
  - **First Cut** — the complete deliverable at a published fixed price,
    shipped in **≤2 business days** (Stephen insisted on 2, not 5) or full
    refund ("the delivery guarantee").
  - **To Signature** — negotiation through an executed agreement as a fixed
    add-on (~75–100% of First Cut price), **3 negotiation rounds included,
    $950/round after**. Electable at order or after seeing the First Cut.
- **The Full Stack** — every deliverable ships in five formats: instrument
  (memo/redline), board deck, one-page visualization, audio brief, runbook.
  This is the signature differentiator.
- **Payment at order** (Stripe planned, not yet built): pay when the SOW is
  accepted, work starts when payment clears. No auth/capture (considered and
  rejected). Large/custom matters: ACH invoice, 50/50 for multi-week work.
  Flat fees earned-on-receipt language must be verified against Stephen's
  licensing state's rules; keep an IOLTA dormant.
- **Custom matters**: budget-band intake ($1.5–3k / 3–7k / 7–15k / talk),
  fixed quote within 1 business day. Never negotiate price — scope to budget.
- **Free trial**: NO standing free offer. Five hand-picked design partners get
  a free deliverable in exchange for testimonials + redacted samples. Public
  sees the fictional demo (below).
- **Scope**: full power sector *capability*, C&I solar/DG *marketing lead*
  (proof-follows-capability; add verticals as case studies accrue).
- **Phase 2 (not built)**: "Counsel Line" membership — kit-credits per month,
  priority queue, rollover capped — added only once catalog demand is proven.

## Site inventory

- `index.html` — homepage (hero, why-this-exists, Full Stack anatomy, two
  tiers, 5-step how-it-works, guarantee band, capabilities grid, bio, contact)
- `catalog.html` — Services & Pricing; 12 services with First Cut prices and
  To Signature add-ons. **Prices are Claude-drafted and await Stephen's
  redline** ($1,500–$6,500 range).
- `solar-dg.html` (primary), `storage.html`, `interconnection.html`,
  `tax-equity.html`, `construction.html`, `markets.html` — capability pages (SEO)
- `kits/index.html` — Sample Work gallery
- `kits/meridian-ridge/` — the demonstration deliverable: fictional seller-side
  PPA review (Meridian Ridge Solar, 4.2 MW, vs. "Granite Peak Beverage" draft).
  memo / deck / heatmap / audio (transcript) / runbook, all cross-linked.
  All parties fictional; every page carries demo banners + attorney-advertising
  disclaimers. Keep those disclaimers on anything new.
- `styles.css` — carbon #14181d · amber #e8a33d · paper #faf8f4; Fraunces /
  Inter / IBM Plex Mono. Bump the `?v=` query on CSS changes.

## Known open items (the roadmap)

1. Stephen's redline of prices, copy, bio; contact email is a placeholder
   (stephen@brownellpowerplus.com) pending a practice domain/address.
2. Real audio file for the demo (NotebookLM over the transcript at
   `kits/meridian-ridge/audio.html`), then add a player to that page.
3. Intake/request form → conflicts-check gate → auto-generated one-page SOW
   under a master engagement letter (e-sign, signed once per client).
4. Stripe: checkout for catalog services (payment at order), ACH invoicing.
5. Airtable ops base: Clients, Matters/SOWs, Parties (conflicts spine —
   including Stephen's TRP matter history), Deliverables, Pipeline.
6. Custom domain + CNAME.
7. Ethics/foundations checklist (Stephen's side): state flat-fee rules,
   malpractice carrier's AI posture, entity formation, "AI Practice Standard"
   transparency page, TRP transition/conflicts.

## Operational notes

- Repo is public. No secrets, tokens, or client-identifying data in commits.
- The GitHub Pages *site* must exist before `deploy-pages` succeeds — it's
  already enabled; don't touch Settings → Pages.
- This sandbox's proxy cannot reach `*.github.io` — verify deploys via the
  Actions workflow conclusion, not curl.
- Session containers are ephemeral: push work to `main` before going idle.
