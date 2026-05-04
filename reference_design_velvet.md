---
name: Design Reference — velvet.vc
description: Editorial luxe-finance aesthetic. Three serifs (Gloock display + Calluna body + Geist Sans/Mono), warm cream-and-stone palette with vivid editorial accents (oxblood, rust, teal, powder blue). Hero video poster, large 28–40px radius cards. Use when referencing this aesthetic for finance/VC/private-capital sites that want couture editorial over corporate.
type: reference
url: https://velvet.vc/
---
# velvet.vc — Full Design Reference
**URL:** https://velvet.vc/
**Product:** Velvet — closed capital network combining a members community with AI tools
**Tagline:** *"The Fabric of Intelligent Private Capital"*
**Hero copy:** *"The best investors don't chase markets. They create them."*
**Audience:** Ultra-high-net-worth allocators, established VCs, founders, institutional investors — by-invitation/exclusive
**Tech stack:** Next.js + Tailwind v4 + Adobe Typekit (Calluna) + custom Gloock display

---

## Aesthetic / Mood
**Couture editorial finance.** Most VC/private-capital sites default to either dark-glass-and-charts or generic SaaS-blue. Velvet does neither: it leans into a **multi-serif editorial layout** (three display/body serifs simultaneously) with a warm **cream-and-stone surface palette** punctuated by **richly saturated editorial accents** — oxblood `#831c1a`, deep wine `#5a192e`, rust `#d83d26`, sand `#ddca9e`, teal `#0089a2`, powder blue `#80aec0`. The combined effect reads less "VC firm" and more "premium fashion magazine that happens to talk about capital."

The hero is a **full-bleed video poster** rather than a hero illustration or product screenshot — pure mood-setting, like a luxury brand campaign reel. Statistics are large but composed (`$1.1T+ AUM`, `14,600+ investments analyzed`) — the numbers are evidence, not the headline.

If generalintelligencecompany.com is "boutique morning paper," Velvet is "Cabana magazine for capital allocators" — same editorial DNA, but lusher, with a couture color palette.

---

## Typography — three-font editorial stack

| Token | Font | Loaded via | Usage |
|---|---|---|---|
| `--font-gloock` | **Gloock** (Google Fonts) | woff2 self-host | **Display headlines** — high-contrast didone-style serif with razor-thin hairlines and dramatic vertical stress. Magazine-cover energy. |
| (Typekit) | **Calluna** | use.typekit.net/tmb1cmf.css | **Body serif** — old-style book serif, very readable at long-form sizes. Used for paragraph copy where sans would feel too tech. |
| `--font-geist-sans` | **Geist Sans** | woff2 self-host | UI labels, navigation, captions |
| `--font-geist-mono` | **Geist Mono** | woff2 self-host | Code/data/metric labels (sparingly) |

**Why this matters:** Combining **Gloock + Calluna** is the design fingerprint. Gloock is rare in tech (it's a contemporary didone, like Bodoni's chic younger sibling); Calluna is rare full-stop (an Adobe Typekit-only release by exljbris). Together they do work normally split between Italian fashion magazines and small-press literary publishers. No other design site in this collection uses two distinct serifs the way Velvet does.

**Substitute fonts (if not licensing Typekit/Google):**
- Gloock → Bodoni*, Playfair Display Black, GT Super Display
- Calluna → Garamond Premier, EB Garamond, GT Sectra Book

---

## Color Palette (extracted)

### Surfaces (warm stone/cream ladder)
| Value | Usage |
|---|---|
| `#fbf8f3` | Page cream (warm) |
| `#f2edeb` | Soft alt surface (slight pink-brown tint) |
| `#cdbfb5` | Stone/muted surface — distinctive "velvet rope" tone |
| `#ffffff` | High-contrast cards |

### Text
| Value | Usage |
|---|---|
| `#212322` | Primary text — near-black with green-gray cast (not pure black) |
| `#000000` | High-contrast moments |
| `#6a7282` | Tertiary muted |

### Editorial accent palette (the signature)
This is what sets Velvet apart from any other site in this collection — a richly varied "magazine spread" accent system:

| Value | Name | Usage |
|---|---|---|
| `#831c1a` | **Oxblood** | Pull-quotes, accent backgrounds |
| `#5a192e` | **Deep wine** | Heavy editorial moments |
| `#d83d26` | **Vermillion / rust** | Section accents, link hovers |
| `#de6e26` | **Burnt orange** | Tags, chips |
| `#d78627` | **Amber** | Sparingly — data callouts |
| `#ddca9e` | **Sand** | Tag fills, soft highlights |
| `#0089a2` | **Teal** | Secondary accent — ocean/cool |
| `#80aec0` | **Powder blue** | Soft accent fills |
| `#c8d9e1` | **Pale blue** | Subtle backgrounds |
| `#70c7ff` | **Sky blue** | Modern interactive moments |
| `#05060d` | **Inky black** | Dark sections (footer, video poster overlays) |

The accent system is **explicitly multi-hue** — not the typical "one brand color" SaaS approach. Every editorial section can use a different accent without breaking the brand, because the brand IS the editorial palette.

---

## Border Radius (Tailwind v4 + custom values)

| Value | Token | Usage |
|---|---|---|
| `0` | — | Hero video, full-bleed sections |
| `--radius-md` | `.375rem` (6px) | Inputs |
| `--radius-lg` | `.5rem` (8px) | Small buttons |
| `--radius-xl` | `.75rem` (12px) | Standard cards |
| `--radius-2xl` | `1rem` (16px) | Mid cards |
| `--radius-3xl` | `1.5rem` (24px) | Large feature cards |
| `20px` / `28px` / `32px` / `40px` | Custom | Section panels, large stat cards (signature generous rounding) |
| `3.40282e38px` | Max float | Pills (CTA buttons) |

The **28–40px** range is specifically used for the large stat panels and editorial cards — generous, soft, expensive-feeling. Combined with the warm cream surfaces it produces that "velvet-cushion" tactile quality.

---

## Layout

- Page bg: `#fbf8f3` (warm cream)
- Container ladder: `--container-2xl: 42rem`, `3xl: 48rem`, `4xl: 56rem`, `5xl: 64rem` (Tailwind v4 standard)
- Hero: full-bleed video poster, no overlay UI on first viewport — the video carries the whole moment
- Sections alternate cream / stone / dark — strong horizontal banding, magazine-spread cadence

**Page structure (top → bottom):**
1. Nav — logo + login
2. **Hero video** — full-bleed, with tagline overlay in Gloock
3. **Logo carousel** — 31+ investor logos, displayed twice (LP/GP credibility wall)
4. **Statistics section** — large numerals (`$1.1T+ AUM`, `14,600+ investments analyzed`), Gloock display
5. **Deal showcase carousel**
6. **Editorial CTA** — exclusivity messaging
7. Footer

---

## Component Notes

### Headlines
- `font-family: var(--font-gloock)` for display
- Very large (clamp 56–96px+ on hero), tight leading (1.0–1.1)
- Often centered, often italic-leaning glyphs
- Calluna serif handles any long-form paragraph below

### Stat blocks
- Gigantic numbers in Gloock (96–144px equivalent)
- Tiny mono/sans label below in Geist
- The contrast (display serif × Geist Mono) is part of the visual signature

### Cards
- 28–40px generous radius
- Subtle warm shadows, not flat
- Often use a single editorial accent as backdrop (oxblood card, sand card, teal card)

### CTAs / pills
- Full-pill `border-radius: 3.40282e38px`
- Often inverted: cream text on oxblood, or oxblood text on cream
- Geist Sans labels — never serif (the typographic contrast is intentional)

### Hero video
- Full-bleed `<video>` poster
- Likely an `aspect-video` (16:9) container, no rounded corners (`border-radius: 0`)
- Gloock tagline rendered on top, large

---

## Brand Voice (informs design)
- *"The Fabric of Intelligent Private Capital"*
- *"The best investors don't chase markets. They create them."*
- Tone: editorial, aphoristic, exclusive — closer to a private members' club newsletter than a fund deck
- Numbers (`$1.1T AUM`) are evidence, never the headline

The design choices map perfectly onto the voice:
- **Multi-serif editorial system** = "we read magazines, not pitch decks"
- **Cream + oxblood + teal** = couture color story, not blue-and-white SaaS
- **Full-bleed video hero** = mood, not product
- **Generous 28–40px card radius** = expensive, tactile, considered

---

## Reproducing this aesthetic — minimum viable kit

1. **Gloock display + Calluna body is non-negotiable.** Substitutes: Bodoni Moda + EB Garamond, or Playfair Display Black + GT Sectra Book.
2. **Surfaces:** `#fbf8f3` cream + `#f2edeb` alt + `#cdbfb5` stone. Avoid pure white except in cards.
3. **Pick a vivid editorial accent** (oxblood, rust, teal — pick ONE per page section, rotate across sections).
4. **Cards at 28–40px radius**, not 12–16px. Generous = expensive.
5. **Mono accents** (Geist Mono) only for technical labels — never bodies.
6. **Hero must be full-bleed video or full-bleed photography**, not a UI screenshot.
7. **No icon library.** Hand-pick or commission marks per section.

---

## Comparison to Other Saved References

| | velvet.vc | generalintelligencecompany.com | varickagents.com | guild.ai | adaline.ai | tahahossain.com |
|---|---|---|---|---|---|---|
| Style | Couture editorial finance | Boutique AI lab editorial | Enterprise ops minimalism | Warehouse editorial dev infra | AI-infra sage | Blueprint brutalism |
| BG | Warm cream `#fbf8f3` | Cream `#f9faf7` | Off-white `#f8f8f8` | Warm cream `#f8f6f3` | Olive `#f8f9f5` | Cream `#f6f5f1` |
| Display | **Gloock (didone serif)** | PP Mondwest | Bold geo sans | Suisse Neue | Akkurat | Unica 77 + EB Garamond |
| Body | **Calluna (Typekit serif)** | af (custom sans) | Framer default | Syndicat Grotesk | Akkurat | Diatype Mono |
| Accent | **Multi-hue editorial** (oxblood, rust, teal, sand) | None — monochrome | Electric blue + navy | Orange `#ff5500` | Olive `#4a6d47` | Red/green/blue hairlines |
| Radius | **28–40px** large + full pill | 24px + 50px pill | Square corners | 4–20px | 8–12px | None |
| Hero | **Full-bleed video poster** | Headline-only | Particle wave SVG | Animated agent UI | Product screenshot | Static |
| Distinguishing trick | **Gloock + Calluna double-serif + magazine-couture palette** | PP Mondwest + sun glyph | Square CTAs + SVG particles | Orange selection + dot grid | Material 3 surface tiers | Hairline registration lines |
