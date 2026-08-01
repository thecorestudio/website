# DESIGN.md — TheCore Studio

> Portable design system in the Google Stitch `DESIGN.md` format, for use with
> Impeccable and any DESIGN.md-aware AI harness. Register: **brand + product**.
> Version 0.1 · 2026.

---

## Brand

- **Name:** TheCore Studio
- **Category:** Pilates studio — small classes, seriously trained instructors, complete equipment (beyond the Reformer).
- **Positioning:** The center movement starts from. A place where you're followed body by body, not processed as a number.
- **Registers:** `brand` (site, marketing, identity) and `product` (booking app, member area). Every command should know which it's in.

---

## Voice & Tone

Speak like a good instructor who looks you in the eye.

- **Address:** informal second person — Italian *tu*. Warm, never distant.
- **Personality:** warm not cold · competent not condescending · clear not loud · encouraging not judgmental.
- **Principles:**
  - Person first, exercise second. Make people feel awaited, not handled.
  - Explain the *why* of a movement in plain words — no jargon.
  - No caps-lock, no urgency, no inflated promises. Few words, the right ones.
  - Every level is welcome. Celebrate progress, never compare bodies.

**Say this**
- "Vieni a provare, poi ne parliamo con calma."
- "Sei in gruppo piccolo: ti seguiamo davvero."
- "Oggi hai tenuto la posizione più a lungo. Si vede."

**Never this (anti-references)**
- "RIMETTITI IN FORMA PER L'ESTATE!"
- "Il workout definitivo per bruciare grassi."
- "Posti limitatissimi, affrettati ora!!!"
- Generic hype, fat-shaming, scarcity pressure, exclamation stacks.

---

## Color

Warm neutrals base, one terracotta heart, sage as the natural second. Two background colors max per surface. **Terracotta is an accent, not a carpet** — reserve it for the single action you want the person to take.

### Semantic tokens

| Token | Value | Use |
|---|---|---|
| `--bg-surface` | `#EFE7DA` | Page / app background (cream) |
| `--bg-raised` | `#F6F1E8` | Cards, raised surfaces |
| `--border` | `#E4D6C1` | Hairline borders, dividers |
| `--text-primary` | `#2E2822` | Titles and body (espresso) |
| `--text-muted` | `#7A6C5E` | Secondary text, captions |
| `--accent` | `#C06B47` | CTA, links, emphasis (terracotta) |
| `--accent-hover` | `#A85638` | Hover / active accent |
| `--accent-calm` | `#8A9079` | Calm states, tags, badges (sage) |

### Scales

**Clay / neutrals** — `#F6F1E8` 50 · `#EFE7DA` 100 · `#E4D6C1` 200 · `#D0BCA0` 300 · `#B09A7E` 400 · `#7A6C5E` 500 · `#4A4038` 700 · `#2E2822` 900 · `#211C17` 950

**Terracotta** — `#FBEEE6` 50 · `#F0D8C9` 100 · `#E3B49B` 200 · `#D6997A` 300 · `#C06B47` 500 · `#A85638` 600 · `#7D3D26` 700

**Sage** — `#EEF0E8` 50 · `#DDE0D2` 100 · `#C4CAB4` 200 · `#A7AF93` 300 · `#8A9079` 500 · `#6B715C` 600 · `#4F5544` 700

---

## Typography

- **Display / titles:** `"Cormorant Garamond", serif` — weights 400 / 500, italic available. Editorial, warm, elegant.
- **Text / UI:** `"Hanken Grotesk", sans-serif` — weights 400 / 500 / 600 / 700.
- **Mono / labels:** `"Spline Sans Mono", monospace` — small caps-style labels, letter-spacing `0.1–0.14em`, uppercase.

### Type scale

| Role | Family | Size / line |
|---|---|---|
| display | Cormorant Garamond 500 | 56–64 / 0.95 |
| h2 | Cormorant Garamond 500 | 40 / 1.1 |
| h3 | Hanken Grotesk 600 | 22 / 1.2 |
| body | Hanken Grotesk 400 | 17 / 1.6 |
| caption | Spline Sans Mono 400 | 13, uppercase, `0.08em` |

---

## Space, Shape & Elevation

- **Spacing (base 4):** `xs 8` · `sm 12` · `md 16` · `lg 24` · `xl 40` · `2xl 64` · `3xl 96`
- **Radius (soft, never sharp):** `sm 8` · `md 14` · `lg 22` · `full 999`
- **Shadow:** `soft 0 2px 8px rgba(46,40,34,.06)` · `raised 0 8px 24px rgba(46,40,34,.10)`

---

## Logo

- **Mark:** concentric circles — the "core", a center from which movement radiates. Works standalone (app icon, stamp, social).
- **Preferred lockup:** the mark **on solid terracotta** `#C06B47` with cream `#FBEEE6` rings and cream wordmark. This is the hero expression.
- **Wordmark:** "TheCore" in Cormorant Garamond 500; "Studio" in Spline Sans Mono, uppercase, letter-spacing `0.42em`, flanked by two short terracotta rules.
- **Variants:** mono espresso `#2E2822`, negative (cream on espresso), on-sage, on-terracotta (preferred).
- **Clear space:** margin around the mark equal to the inner circle's radius.
- **Minimum size:** 24 px digital · 10 mm print.
- **App icon:** mark alone, centered, no wordmark — solid terracotta tile, radius 22.

---

## Design rules

1. Terracotta is for action and emphasis only; if it's everywhere, nothing stands out.
2. Max one or two background colors per surface — cream and one raised tone.
3. Radii stay soft; no sharp corners.
4. Titles are serif (Cormorant), everything functional is Hanken Grotesk, labels are mono uppercase.
5. Copy is *tu*, warm, plain, unhurried — see Voice.
6. Community & territory warmth (local synergies) informs tone, not public claims.

---

## Tokens (CSS)

```css
:root {
  /* surfaces */
  --bg-surface: #EFE7DA;
  --bg-raised:  #F6F1E8;
  --border:     #E4D6C1;
  /* text */
  --text-primary: #2E2822;
  --text-muted:   #7A6C5E;
  /* accents */
  --accent:       #C06B47;
  --accent-hover: #A85638;
  --accent-calm:  #8A9079;
  /* type */
  --font-display: "Cormorant Garamond", serif;
  --font-sans:    "Hanken Grotesk", sans-serif;
  --font-mono:    "Spline Sans Mono", monospace;
  /* space (base 4) */
  --space-xs: 8px;  --space-sm: 12px; --space-md: 16px;
  --space-lg: 24px; --space-xl: 40px; --space-2xl: 64px;
  /* shape */
  --radius-sm: 8px; --radius-md: 14px; --radius-lg: 22px;
  --shadow-soft:   0 2px 8px rgba(46,40,34,.06);
  --shadow-raised: 0 8px 24px rgba(46,40,34,.10);
}
```

