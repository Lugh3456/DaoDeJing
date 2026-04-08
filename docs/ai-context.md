# AI Development Context — Dao De Jing

Always read this file before modifying the site.

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
  docs/                 ← this folder
  Backup/               ← dated backups
```

Never put CSS outside `css/`. Never put HTML in subfolders.
All pages must be at the repository root to work with GitHub Pages.

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
Batch changes across many files using Python scripts.
Always create a dated Backup/ folder before modifying files.
Verify locally before pushing to GitHub.
