# groundtruth-landing

Marketing site for [GroundTruth](https://mygroundtruth.app) — a
peer-attestation land-tenure platform for Ghana. The main product
lives at [koblavi/groundtruth](https://github.com/koblavi/groundtruth).

## What's here

Three static HTML pages plus a shared stylesheet:

| File | URL | Purpose |
|---|---|---|
| `index.html` | `/` | Landing — brand mark, tagline, "coming soon" |
| `privacy.html` | `/privacy` | Privacy Policy — Ghana Data Protection Act 2012 aligned |
| `terms.html` | `/terms` | Terms of Service — peer-attestation framing, NOT legal title |
| `style.css` | n/a | Shared stylesheet matching the mobile app's brand palette |

The pages share styling and the hex+ochre-dot logo (mirrors the
app icon in the main repo at `apps/mobile/icons/app-icon.svg`).

## Deploy — Cloudflare Pages

This repo is built for [Cloudflare Pages](https://pages.cloudflare.com/):

1. Connect this repo to a Cloudflare Pages project
2. Build settings:
   - **Framework preset:** `None`
   - **Build command:** *(leave blank)*
   - **Build output directory:** `/`
3. Custom domain: point `mygroundtruth.app` at the Pages project
4. Cloudflare auto-issues a Let's Encrypt certificate

Pages strips `.html` from URLs automatically, so `privacy.html` is
served at both `/privacy` and `/privacy.html`. The Google OAuth
consent screen URLs use the clean variants.

## Legal disclaimers

Both `privacy.html` and `terms.html` carry a **"Draft pending legal
review"** banner. They are accurate technical descriptions of what
the platform does, written by the engineering team. They need a pass
from Ghanaian counsel before public launch — particularly:

- §6 of the Terms ("Trust signals are community signals, not legal
  proof") — this is the load-bearing legal framing for the whole
  product and should be reviewed by a property-law specialist.
- Privacy §6 (your rights) — make sure the response timelines and
  the Ghana Data Protection Commission complaint route are accurate
  to current practice.
- Terms §14 (governing law / Accra jurisdiction) — confirm with
  counsel this is the right venue clause for our entity structure.

## Brand colours (from the mobile app's `Theme.axaml`)

| Name | Hex | Use |
|---|---|---|
| GtCream-50 | `#FAF7F2` | Page background |
| GtGreen-900 | `#0F2E22` | Body text |
| GtGreen-700 | `#1F4D3A` | Logo hexagon, headings |
| GtOchre-500 | `#D4823A` | Accent dot, links |
| GtLine | `#E5DFD5` | Dividers |
| GtMuted-700 | `#6B6256` | Footer, secondary text |

Keep new pages consistent with this palette — the goal is for users
arriving from a WhatsApp share-card link to feel they've landed in
the same product they saw on someone's phone.

## Updating the brand mark

The hex+dot is inlined as SVG in every page (no external request).
Source vector lives in the main repo:
`apps/mobile/icons/app-icon.svg`. If the brand mark changes there,
update the inline `<svg>` in `index.html`, `privacy.html`,
`terms.html` to match.

## Contact

`hello@mygroundtruth.app` — general
`privacy@mygroundtruth.app` — privacy questions
`legal@mygroundtruth.app` — terms / legal questions
`security@mygroundtruth.app` — vulnerability reports
