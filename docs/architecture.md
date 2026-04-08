# Architecture — Dao De Jing

## Project Overview

A static HTML + CSS website hosting all 81 chapters of the Dao De Jing.
No frameworks. No build step. GitHub Pages serves the files directly.

---

# Folder Structure

```
DaoDeJing/
  index.html            ← home page, grid of 81 chapter cards
  chapter1.html         ← chapter detail pages
  ...
  chapter81.html
  css/
    style.css           ← all styles (design tokens, layout, components)
  images/               ← future assets (illustrations, icons)
  docs/                 ← project documentation
  Backup/               ← dated backups (YYYY-MM-DD/) before changes
```

---

# Page Types

## 1. Home Page — index.html

Displays a grid of 81 chapter cards. Each card links to its chapter page.

Key sections:
```
portal-bar      ← "← The Way Within" back link (top of every page)
site-header     ← site title + Chinese subtitle
intro           ← short description of the Dao De Jing
main.card-grid  ← 81 chapter cards
footer          ← copyright + portal link
```

## 2. Chapter Pages — chapter1.html … chapter81.html

One page per chapter. Consistent structure across all 81 pages.

Key sections:
```
portal-bar              ← "← The Way Within" back link
chapter-header          ← chapter number + prev/next/home nav
main.chapter-container  ← all chapter content
  section.full-text     ← original Chinese text + audio button
  section.line-explanation  ← 逐句解釋 (line-by-line breakdown)
  section.summary       ← 章節精髓 (chapter essence/summary)
footer                  ← copyright + portal link
```

---

# Navigation

Every chapter page includes a `chapter-nav` with three links:
- ← Chapter N-1 (hidden on chapter 1)
- Home (always present)
- Chapter N+1 → (hidden on chapter 81)

---

# CSS Architecture

Single stylesheet: `css/style.css`

Organised in sections:
```
TOKENS / VARIABLES     ← CSS custom properties (:root)
SKIP LINK              ← accessibility
PORTAL BAR             ← top strip linking back to portal
RESET & BASE
HEADER
INTRO
CARD GRID              ← 81 chapter cards on home page
CHAPTER HEADER         ← chapter page header
CHAPTER NAV            ← prev/next navigation
CHAPTER CONTAINER      ← main content area
EXPLANATION CARDS      ← line-by-line breakdown cards
SUMMARY                ← chapter summary section
AUDIO BUTTON           ← 誦讀全文 button
FOOTER
RESPONSIVE             ← @media breakpoints
```

---

# Design Tokens

Shared with The Way Within portal. Defined in `:root`:

| Token | Value | Usage |
|-------|-------|-------|
| `--bg` | `#f5f0e8` | Page background |
| `--surface` | `#ffffff` | Card background |
| `--ink` | `#1c1a14` | Header/footer background |
| `--ink-light` | `#3a3528` | Secondary dark surfaces |
| `--gold` | `#a07830` | Accents, buttons, links |
| `--gold-light` | `#c9a75a` | Hover states |
| `--text` | `#2d2a22` | Body text |
| `--muted` | `#6b6455` | Secondary text |
| `--border` | `#ddd5c0` | Card borders |
| `--radius` | `8px` | Border radius |

---

# Audio Feature

Each chapter page includes a 誦讀全文 (Read Aloud) button.
Uses the browser's Web Speech API (`window.speechSynthesis`) — no server required.
Targets Mandarin TTS voice (`zh-CN`), speech rate 0.9.

---

# Responsive Design

| Breakpoint | Chapter grid | Cards |
|-----------|-------------|-------|
| > 600px | Multi-column auto-fit | Normal padding |
| ≤ 600px | Single column | Compact padding |

---

# Hosting

GitHub Pages. `index.html` at repository root.
All paths are relative — no configuration needed.

Live URL: https://lugh3456.github.io/DaoDeJing/
