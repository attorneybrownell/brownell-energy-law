# Brownell Energy Law

Website for Brownell Energy Law — flat-fee legal counsel for the power sector,
by Stephen Brownell. Services are named by output (PPA Review & Redline,
Project Diligence Report, …) and come in two tiers: **First Cut** — the
complete deliverable in two business days at a published fixed price — and
**To Signature** — negotiation through an executed agreement, three rounds
included. Every deliverable ships as **the Full Stack**: the legal instrument
plus a board deck, a one-page visualization, an audio brief, and an action
runbook.

## Structure

- `index.html` — homepage: positioning, the Full Stack, tiers, how it works, guarantee, about
- `catalog.html` — services & pricing (First Cut / To Signature tiers)
- `kits/` — sample work gallery (demonstration deliverable for a fictional project)
- `solar-dg.html`, `storage.html`, `interconnection.html`, `tax-equity.html`,
  `construction.html`, `markets.html` — capability pages (solar/DG is the
  primary focus; the rest exist for full-sector coverage and SEO)
- `styles.css` — single shared stylesheet (Fraunces / Inter / IBM Plex Mono;
  carbon + amber + paper)
- `.github/workflows/deploy.yml` — GitHub Pages deploy on every push to `main`

## Deployment

Static site, no build step. Pushing to `main` triggers the Pages workflow,
which publishes the repository root to
<https://attorneybrownell.github.io/brownell-energy-law/>.

## Roadmap (not yet built)

- Intake/request form with conflicts-check gate and auto-generated SOWs
- Stripe checkout (payment at order) for catalog kits
- Airtable ops base: clients, matters, parties/conflicts, deliverables
- Real sample kit assets (memo, deck, visualization, audio, runbook) for the
  Meridian Ridge Solar demonstration project
- Custom domain
