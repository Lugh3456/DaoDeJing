# AI Development Context — Dao De Jing

Always read this file before modifying the site.

---

# Current State
Last updated: 2026-04-26
Phase: Phase 3 — Content Improvement (Phase 4 complete)
Last completed: Full content audit — 2026-04-26. All 81 chapters verified for correct Chinese source text and complete explanation cards. All structure checks pass.
In progress: —
Next up: —

---

# Project Purpose

A static educational site presenting all 81 chapters of the Dao De Jing (道德經).
Part of the **The Way Within (修身之道)** collection of classical Chinese wisdom sites.

The site feels calm, scholarly, and minimal. Avoid flashy UI or heavy animation.

---

# Technology Constraints

Uses only:

HTML
CSS
Vanilla JavaScript (Web Speech API for audio — do not remove)

Do NOT introduce:

React, Vue, Next.js, Tailwind
Build tools or Node dependencies
Any server-side code

The site must remain static and deployable directly to GitHub Pages.

---

# Folder Structure

```
DaoDeJing/
  index.html            ← home page
  chapter1.html … chapter81.html  ← chapter pages
  css/style.css         ← all styles
  images/               ← future assets
  docs/
    readme.md           ← project overview
    architecture.md     ← technical structure
    plan.md             ← vision and objectives
    roadmap.md          ← phased delivery plan
    ai-context.md       ← this file
    audit-config.json   ← site structure config for content audit
    reference.py        ← authoritative Wang Bi text for all 81 chapters
  Backup/               ← dated backups (YYYY-MM-DD/) before changes
```

Never put CSS outside `css/`. Never put HTML in subfolders.
All pages must be at the repository root to work with GitHub Pages.

---

# Content Audit

**Always run the content audit before pushing to GitHub.**

This site has a dedicated audit skill (`ddj-content-audit`) that checks:
1. The Chinese source text in every chapter matches the authoritative Wang Bi reference
2. Every line of source text has a corresponding explanation card
3. All HTML structure elements are present and correct (nav links, titles, sections, scripts, accessibility)

## Audit files (in docs/)

`audit-config.json` — describes this site's HTML structure so the audit scripts know where to look. Contains the element selectors, section class names, and reference file location.

`reference.py` — the authoritative Wang Bi text for all 81 chapters. This is the "correct answer" file. The audit compares every chapter's `<p id="chineseText">` against this reference and flags any wrong, truncated, or mismatched text.

## How to run the audit

Ask Claude to audit the DaoDeJing site. The `ddj-content-audit` skill handles the rest — it reads the config, runs both checks, and reports any issues before you push.

## History

A 2026-04-26 audit found 69 of 81 chapters had content problems (wrong text, truncated text, missing explanation cards). All were fixed that day. See `Backup/2026-04-26/` for the pre-fix snapshots.

---

# Design Tokens

Defined in `:root` in `css/style.css`. Always use tokens — never hardcode colours.

| Token | Value | Usage |
|-------|-------|-------|
| `--bg` | `#f5f0e8` | Page background |
| `--surface` | `#ffffff` | Card background |
| `--ink` | `#1c1a14` | Header/footer background |
| `--ink-light` | `#3a3528` | Secondary dark surfaces |
| `--gold` | `#a07830` | Accents, interactive elements |
| `--gold-light` | `#c9a75a` | Hover states |
| `--text` | `#2d2a22` | Body text |
| `--muted` | `#6b6455` | Secondary text |
| `--border` | `#ddd5c0` | Card borders |
| `--radius` | `8px` | Border radius |

---

# Typography

Noto Serif SC — headings, Chinese text, chapter cards
Noto Sans SC — body text, navigation, explanations

Both are loaded from Google Fonts. Do not switch fonts.

---

# Key CSS Classes

| Class | Purpose |
|-------|---------|
| `.portal-bar` | Top strip linking back to The Way Within |
| `.skip-link` | Accessibility skip link (before portal-bar) |
| `.site-header` | Home page header |
| `.chapter-header` | Chapter page header |
| `.header-zh` | Chinese subtitle (道德經) in header |
| `.chapter-nav` | Prev/Home/Next navigation |
| `.card-grid` | 81 chapter cards grid |
| `.chapter-card` | Individual chapter card on home page |
| `.chapter-container` | Main content wrapper on chapter pages |
| `.line-explanation` | 逐句解釋 section |
| `.explanation-card` | Individual line breakdown card |
| `.summary` | 章節精髓 section |
| `.read-btn` | 誦讀全文 audio button |
| `.footer-portal-link` | Portal link in footer |

Do not rename these classes unless necessary.

---

# Page Structure — Chapter Pages

Every chapter page must follow this structure:

```html
<a class="skip-link" href="#main-content">Skip to content</a>
<div class="portal-bar"> … </div>
<header class="chapter-header">
  <h1>Chapter N</h1>
  <nav class="chapter-nav"> … prev / home / next … </nav>
</header>
<main class="chapter-container" id="main-content">
  <section class="full-text"> … Chinese text + audio button … </section>
  <section class="line-explanation">
    <h2>逐句解釋</h2>
    … explanation cards …
  </section>
  <section class="summary">
    <h2>章節精髓</h2>
    … summary text …
  </section>
</main>
<footer class="site-footer">
  <a href="…" class="footer-portal-link">The Way Within · 修身之道</a>
  <p>© 2026 Dao De Jing Learning Platform</p>
</footer>
```

---

# Chapter Navigation Rules

- Chapter 1: no previous link
- Chapter 81: no next link
- All other chapters: show both previous and next
- Home link always present

---

# What Not to Change

- CSS custom properties in `:root`
- Google Fonts import (both Noto Serif SC and Noto Sans SC)
- The skip link before the portal bar
- The `id="main-content"` on `<main>`
- The audio/speak() function in chapter pages

---

# Development Philosophy

Prefer simple HTML and clean structure.
Use a Python script for any change touching 5 or more files; edit directly for fewer than 5.
Always create a dated Backup/ folder before modifying files.
Run the content audit before pushing to GitHub.
Verify locally before pushing to GitHub.
