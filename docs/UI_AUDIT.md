# UI/UX quality gate

Guided by [UI UX Pro Max's priorities](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill/blob/main/.claude/skills/ui-ux-pro-max/references/quick-reference.md).

## Automated/static inspections performed for this revision

- HTML: one `h1`, matching HTML tag open/close counts, semantic header/nav/main/footer landmarks.
- Links: internal anchors and relative CSS/favicon paths resolve in the repository tree; project case study links target present paths.
- Runtime: no JavaScript or third-party tracking; CSS only, with no external font requests.
- Responsive CSS: dedicated tablet/phone/narrow-phone adjustments.
- Interaction: visible focus states, skip link, minimum height for linked controls, reduced-motion override.
- Design tokens: representative high-contrast text pairs measured independently. This does not replace comprehensive accessibility auditing.

## Manual browser checklist

- [ ] At widths 320 / 375 / 768 / 1024 / 1440, verify no horizontal overflow or unwanted clipped text.
- [ ] Zoom to 200% and make sure headlines, labels and actions reflow.
- [ ] Tab from the skip link through all controls; focus remains visible below sticky header.
- [ ] Simulate `prefers-reduced-motion: reduce`.
- [ ] Open each outbound link (Italeen, Google Play, case studies, GitHub).
- [ ] Check Google Pages deployment after merge, including CSS cache refresh.
- [ ] If running Lighthouse/axe, save the report before claiming an audit score.

**Scope:** static validation is not the same as visual browser QA or production deployment certification.
