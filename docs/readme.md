# Dao De Jing — Learning Site

**Dao De Jing (道德經)** is a static educational website presenting all 81 chapters of the Tao Te Ching, the classical Chinese text attributed to Laozi (老子), written over 2,500 years ago.

Each chapter includes the full original Chinese text, a line-by-line explanation in Traditional Chinese, and a chapter summary. The site is part of **The Way Within (修身之道)** collection.

---

# Site Goals

- Present all 81 chapters in a clean, readable format
- Provide line-by-line explanations in Traditional Chinese
- Support audio reading via the Web Speech API
- Link seamlessly back to the The Way Within portal
- Maintain a calm, scholarly reading environment

---

# Technology

The project intentionally uses a minimal technology stack.

HTML
CSS
Vanilla JavaScript (Web Speech API only, for audio reading)

No frameworks. No build tools. No dependencies.

This keeps the site easy to maintain and deploy on GitHub Pages.

---

# Hosting

GitHub Pages via the `lugh3456` account.

Live URL: https://lugh3456.github.io/DaoDeJing/

---

# Folder Structure

```
DaoDeJing/
  index.html            ← chapter grid (81 cards)
  chapter1.html         ← individual chapter pages
  chapter2.html
  ...
  chapter81.html
  css/
    style.css           ← all site styles
  images/               ← placeholder for future assets
  docs/
    readme.md           ← this file
    architecture.md     ← technical structure
    plan.md             ← vision and objectives
    roadmap.md          ← phased delivery plan
    ai-context.md       ← instructions for AI assistants
  Backup/               ← dated backups before major changes
```

---

# Design

The site shares the design system of The Way Within portal:

- Warm parchment background (`#f5f0e8`)
- Deep ink header and footer (`#1c1a14`)
- Gold accents (`#a07830`)
- Noto Serif SC for headings and Chinese text
- Noto Sans SC for body text

---

# License

Personal educational project.
