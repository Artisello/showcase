# Ihor Hrudnyy Showcase — Master Design System

**Audience:** YC reviewers, investors, technical peers, potential collaborators.  
**Primary job:** Explain in less than 30 seconds what the founder has actually built, and offer direct proof.  
**Implementation:** GitHub Pages, static semantic HTML + CSS. No runtime JavaScript, external fonts, third-party tracking, or build step.

## Reference and selection

Adapted from [UI UX Pro Max](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill) and its searchable data and quick-reference guidance (reviewed 2026-11-03).

- **Product match:** `Portfolio/Personal` in `data/products.csv` — primary `Motion-Driven + Minimalism & Swiss Style`, secondary `Brutalism`; use a **storytelling-driven** landing sequence. Motion is deliberately restrained for an investor-facing static portfolio.
- **Supporting pattern:** `Portfolio Grid` in `data/landing.csv` — hero, selected work, philosophy, direct closing action.
- **Typography reference:** `Tech Startup` in `data/typography.csv` suggests Space Grotesk + DM Sans. We preserve the intended bold geometric hierarchy using **system fonts** to avoid a network font dependency.
- **Color interpretation:** project-specific charcoal, off-white and restrained chartreuse rather than applying an unrelated generic portfolio palette. This is an intentional brand adaptation, not a generated exact-palette match.
- **UX rules:** `references/quick-reference.md` priorities: contrast, visible focus, touch targets, responsive reflow, semantic headings, minimal scripts, reduced motion, no fabricated social proof.

## Direction

**Swiss editorial with an engineering edge.** One dominant headline, asymmetric hero, restrained grid, disciplined whitespace, crisp dividing lines, one accent for focus and primary actions.

The site must feel decisive and technically credible, not like a sales landing page or a template gallery. Real evidence is more persuasive than large numerical claims.

## Color tokens (docs/assets/site.css)

| Role | Token | Value | Purpose |
| --- | --- | --- | --- |
| Dark background | `--bg` | `#0c1110` | Primary canvas |
| Dark surface | `--surface` | `#17201b` | Project cards |
| Light text | `--text` | `#f3f5ed` | Primary on dark |
| Muted text | `--muted` | `#b6c6b9` | Secondary on dark |
| Accent | `--accent` | `#d8f468` | CTA and proof links |
| Light section | `--light` | `#f1f1e8` | Technical chapter |
| Dark text | `--light-ink` | `#16231b` | Primary on light |

Computed representative contrast ratios (WCAG formula; checked independently): primary on dark **17.31:1**; muted on dark **10.67:1**; accent on dark **15.46:1**; light-section body text **7.30:1**. These checks are for specified pairs, **not** a blanket WCAG certification.

## Type and layout

- Font stack: system sans, no third-party font load.
- Body: 16px base, 1.6+ line-height. Hero description: 18px desktop / 17px phone.
- Large compact headings: weight 800; tight display tracking only, not tight body text.
- Metadata labels: 12px minimum; links/CTAs: 15px minimum with clear hierarchy.
- Grid container: up to 1200px. Width: viewport minus consistent fluid gutters.
- Spacing: coarse 8px rhythm for major sections; micro adjustments only at breakpoints.
- Main breakpoints: ~1070px, 800px, 620px, 375px.

## Information architecture

1. Founder positioning + concise explanation + visible CTA
2. Three **real external proofs** (business, published Android listing, engineering case study)
3. Four scoped project stories with transparent status (live, private code, published, MVP/pilot)
4. Architecture philosophy, shown with a diagram that cannot imply production verification
5. Human leadership beyond software
6. Closing CTA to the public portfolio and evidence policy

## Interaction and accessibility

- Semantic nav, exactly one h1, sequential headings, skip link, meaningful external-link text.
- At least 44px practical link/touch hit area for navigation and primary actions.
- Focus outline at least 3px; never hidden by decorative overlays.
- No hover-dependent essential information.
- User's reduced-motion preference disables decorative transitions and smooth scrolling.
- Decorative map/diagram elements are marked or wrapped appropriately for screen readers.
- Icons are simple text directional arrows, not emoji; decorative arrows are `aria-hidden`.
- No speculative metrics, fake reviews or quote cards.

## Proof discipline

- Italeen is the operating business; public live storefront linked directly.
- Original WooCommerce source repositories remain private; case studies summarize architecture, not confirmed deployment of every revision.
- Artisello has a public Google Play listing; the B2B workflow remains separately labeled as MVP/pilot.
- Invitalia funding, Kilometro Rosso workspace and swimming history are founder-provided facts; supporting private records are not disclosed here.
- Read `EVIDENCE.md` before introducing any new claims.

## Pre-publication checks

Review desktop (1440/1024), tablet (768), phone (375 and 320) and narrow landscape. Check keyboard navigation, 200% zoom, page overflow, link destinations, focus, dark/light chapter contrast, reduced motion and text wrapping. Do not claim browser screenshot/visual validation until it has actually been performed.
