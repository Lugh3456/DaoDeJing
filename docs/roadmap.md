# Roadmap — Dao De Jing

---

# Phase 1 — Foundation (Completed)

- HTML structure for all 81 chapter pages
- Basic CSS styling
- Chapter grid on home page
- Audio reading feature (Web Speech API)

---

# Phase 2 — Unified Design System (Completed)

Integration with The Way Within portal design system.

- Adopted shared design tokens (colours, fonts) from the portal
- Added portal bar ("← The Way Within") to every page
- Applied Noto Serif SC + Noto Sans SC fonts across all pages
- Gold accent colours for interactive elements
- Chinese subtitle (道德經) in site header
- Skip links for keyboard accessibility
- Prev/Next chapter navigation on all chapter pages
- Footer with portal link on all pages
- Meta description on home page
- Standardised folder structure: css/, docs/, images/

---

# Phase 3 — Content Improvement

Possible improvements:

- Add English translations for each chapter
- Add historical and philosophical context per chapter
- Add illustrations or calligraphy images
- Cross-reference related chapters

---

# Phase 4 — Polish and Launch (Completed)

- SEO optimisation (meta tags, structured data)
- Performance review (font loading, layout shift)
- Full accessibility audit
- Deployed to GitHub Pages — 2026-04-08
  Live URL: https://lugh3456.github.io/DaoDeJing/

---

# Future Considerations

- Search or filter across chapters by theme or keyword
- Favourite / bookmark chapters (client-side)
- Dark mode option

---

# Phase 5 — Content Audit (Completed 2026-04-26)

A full audit of all 81 chapters revealed 69 had content problems after initial generation.

Issues found and fixed:
- 22 chapters had wrong source text (text from a different chapter entirely)
- 43 chapters had truncated source text (cut off before the end)
- 4 chapters had minor character mismatches
- Missing explanation cards across many chapters

All 81 chapters now pass both the content audit and HTML structure check.

Audit infrastructure added to `docs/`:
- `audit-config.json` — site structure config for the audit skill
- `reference.py` — authoritative Wang Bi text for all 81 chapters

