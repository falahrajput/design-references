---
name: Design Reference — tahahossain.com
description: Detailed design system from Taha Hossain's portfolio site — colors, type, layout, grid lines, and component specs. Use when referencing this aesthetic for design work.
type: reference
originSessionId: 84d6c5e7-91ed-47c1-86de-c5ecf3545e02
---
# tahahossain.com — Full Design Reference
**URL:** https://tahahossain.com/
**Built with:** Webflow
**Owner:** Taha Hossain, Founder & Creative Director at Daybreak Studio

---

## Aesthetic / Mood
Blueprint-meets-editorial. Feels like a printed layout spec or architectural drawing rendered in the browser. Extremely precise, minimal color, heavy use of hairline registration lines and monospace metadata labels. Typography contrast between serif body copy and micro-uppercase mono labels is the defining characteristic.

---

## Color Palette

| Token | Value | Usage |
|---|---|---|
| Background | `#f6f5f1` | Main page background (warm cream) |
| `--text-main` | `black` | All body/label text |
| `--line-red` | `#bb5e5e` | All 4 outer border lines + top grid rule |
| `--line-green` | `#1d8341` | Vertical column divider pseudo-elements |
| `--line-blue` | `#3d60dc` | Horizontal row divider lines + technical detail text |
| `--creamwhite` | `#fffdf9` | Alternate off-white |

---

## Typography

| Role | Font | Size | Line Height | Other |
|---|---|---|---|---|
| Callout / Labels | `"Unica 77"` | 11px | 125% | letter-spacing: 0.1px |
| Mono metadata | `"Diatype Mono"` | 8px | 125% | uppercase |
| Body large | `EB Garamond` | 24px | 31px | — |
| Body small | `EB Garamond` | 13px | 17px | — |
| Item numbers | `"Unica 77"` | 8px | 100% | — |

Other fonts loaded (unused in main layout): Montserrat, Rubik, Anton, Raleway, Playfair Display, Lora, Vidaloka, Work Sans, Inter.

---

## Layout

- **Outer container:** `width: 100%`, `height: 100%`, `position: absolute`
- **Main grid:** `display: flex`, `flex-flow: wrap`, `padding: 24px`, `grid-row-gap: 24px`, `grid-column-gap: 0px`
- **Grid template:** 2 columns (`1fr 1fr`) — left bio panel + right resume grid
- **Left panel (`.grid-text`):** `flex-flow: column`, `min-width: 372px`, `padding: 44px 24px 24px`, `gap: 48px`
- **Right resume (`.grid-resume`):** `display: flex`, `flex-flow: wrap`, two columns inside each with `min-width: 350px`
- **Resume items (`.grid-resume--item`):** `padding: 44px 24px 40px`, `gap: 16px`
- **Overflow:** `overflow: scroll` on main grid (no visible scrollbar — hidden via CSS)

---

## The Registration Line System (most distinctive feature)

Four hairline border lines are rendered as `position: absolute` divs inside `.features`, each 0.5px thick, inset 24px from each edge, colored `#bb5e5e`:
- `.border-l` — left line, top: 0, left: 24px, height: 100vh
- `.border-t` — top line, top: 24px, left: 0, width: 100vw
- `.border-r` — right line, top: 0, right: 24px, height: 100vh
- `.border-b` — bottom line, bottom: 24px, left: 0, width: 100vw

Internal grid dividers use `::before` pseudo-elements:
- Column separators: `background: var(--line-green)` — 0.5px vertical
- Row separators: `background: var(--line-blue)` — 0.5px horizontal (bottom of each grid item)
- Top grid rule: `background: var(--line-red)` — 0.5px horizontal (top of grid)

---

## Technical Metadata Labels (`.grid-technical-details`)

Each section has an absolutely-positioned label strip at the top showing:
- `Content 0X` (section number)
- `" The Section Name "` (quoted, descriptive)
- `Width:1728px` / `Height:1200px` (live-updating via JS on resize)
- `PADDING:24PX`

Styled: `display: flex`, `justify-content: space-between`, `padding: 10px`, `top: 0`, `left: 0`
Color: `var(--line-red)` for main labels, `var(--line-blue)` for secondary column labels

---

## Component Details

### Item Number Badges
- 12×12px circle, `border: 0.5px solid var(--text-main)`, `border-radius: 10px`
- Contains the number in Unica 77, 8px

### Social Links
- `display: flex`, `align-items: center`, `gap: 8px`, `text-decoration: none`
- Icon: custom SVG — 4 tiny 2×2px squares in a 2×2 grid pattern, using `fill: var(--text-main)`
- Link text: EB Garamond body-s (13px)

### Item Details
- Each item: `display: flex`, `gap: 10px`, `align-items: flex-start`
- Wide variant: `gap: 24px`
- Info column: `flex-flow: column`, `gap: 8px`
- Info title: `flex-flow: column`, `gap: 4px`

---

## Content Structure (5 sections)

1. **The Biography** — Full-height left panel. Name, bio text (EB Garamond 24px), socials, contact.
2. **The Practice** — Current work: Daybreak Studio (Est. 2021), TBD (Est. 2025)
3. **The Fieldwork** — Community advisory: Toronto Tech Week, Sheridan Product Advisory Council
4. **The History** — Past places: Freelance/Ueno, Meta, Palantir, Konrad
5. **The Lectures** — Speaking: York University, TTW, Convocation toasts
