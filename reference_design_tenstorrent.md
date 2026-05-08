---
name: Design Reference — tenstorrent.com
description: Premium AI silicon vendor / sovereign compute. Pale teal-tinted off-white `#f1f8f8` + near-black-teal text `#071614`, custom **TT Wormhole** display + Degular Display + Neue Haas Unica Pro + Berkeley Mono. Full multi-hue token ladder system (blue/green/pink/purple/yellow × 0–900). Tailwind v4. Use when referencing this aesthetic for hardware/silicon, sovereign-compute, or research-lab product design.
type: reference
url: https://tenstorrent.com/
---
# tenstorrent.com — Full Design Reference
**URL:** https://tenstorrent.com/
**Product:** Tenstorrent — AI accelerator silicon (Wormhole, Blackhole) + sovereign compute stack
**Tagline:** "Where AI Runs"
**Audience:** Enterprise AI practitioners, sovereign-compute buyers, research labs, anti-vendor-lock-in builders
**Founded by:** Jim Keller (legendary chip architect — DEC Alpha / AMD K8 / Apple A4-A5 / Tesla / Intel)
**Tech stack:** Next.js + Tailwind v4 (with `--spacing: calc(1rem / var(--base-unit))` and full design-token CSS layer)

---

## Aesthetic / Mood
**Premium silicon vendor with a research-lab tint.** The background is a distinctive **pale teal-aqua off-white `#f1f8f8`** — not warm cream, not pure white, not cool gray. It reads as "clean room" — laboratory-clean but slightly oxidized, like a chip die under good lighting. The text is `#071614` (near-black with teal undertone), so the entire page feels color-coordinated even before you notice an accent.

The signature display font is **TT Wormhole** — named after Tenstorrent's "Wormhole" chip product. Few companies name a custom typeface after their own SKU. That's the entire personality: "we make the chips, we made the type." Combined with **Berkeley Mono** for technical labels, **Neue Haas Unica Pro** for body, and **Degular Display** for secondary headlines, the type stack is among the most expensive and considered in the AI-hardware category — a deliberate signal of seriousness.

If modal.com is "lime-green developer rigor" and workers.cloudflare.com is "warm-cream edge platform," Tenstorrent is **"sovereign-silicon laboratory"** — the same dev-tool seriousness, but rendered in a teal-aqua palette that looks like nothing else in AI infra.

---

## Color Palette (exact tokens)

### Surface / text — the core brand pair
| Value | Usage | Frequency |
|---|---|---|
| `#f1f8f8` | **Page background** (pale teal-tinted off-white) | 60 occurrences |
| `#071614` | **Primary text** (near-black, teal cast) | 62 |
| `#678583` | Secondary text / subtle borders | 14 |
| `#55746f` | Tertiary / muted | 10 |
| `#dcd7cb` | Sand / dune (warm contrast accent for cards) | 9 |
| `#000000` | Pure black (used sparingly) | 10 |

The `#f1f8f8 + #071614` pair is the fingerprint — recognize it instantly in screenshots.

### Full multi-hue token ladders (Tailwind v4 design-token style)
Tenstorrent ships **5 full color ladders** (0–900 each). This is unusually generous for a B2B silicon site — most ship 1 or 2 ladders. Suggests they're building a public design system / lots of internal product UI:

#### Blue ladder
| Step | Hex |
|---|---|
| `--color-blue-0` | `#f5f7fe` |
| `--color-blue-50` | `#e6eaff` |
| `--color-blue-100` | `#ccd4ff` |
| `--color-blue-200` | `#99a8ff` |
| `--color-blue-300` | `#6179ff` |
| `--color-blue-400` | `#4958df` |
| `--color-blue-500` | `#3c48b4` |
| `--color-blue-600` | `#2d3a8f` |
| `--color-blue-700` | `#252f6f` |
| `--color-blue-800` | `#1e2652` |
| `--color-blue-900` | `#161b3c` |

#### Green ladder (teal-leaning)
| Step | Hex |
|---|---|
| `--color-green-0` | `#f4faf9` |
| `--color-green-50` | `#e6f9f6` |
| `--color-green-100` | `#c6f1e9` |
| `--color-green-200` | `#a5e9dc` |
| `--color-green-300` | `#78ddcb` |
| `--color-green-400` | `#40bfa8` |
| `--color-green-500` | `#29a38d` |
| `--color-green-600` | `#227767` |
| `--color-green-700` | `#13584b` |
| `--color-green-800` | `#0f3d35` |
| `--color-green-900` | `#112c26` |

#### Pink ladder
| Step | Hex |
|---|---|
| `--color-pink-0` | `#fdf7fb` |
| `--color-pink-50` | `#fdedf7` |
| `--color-pink-100` | `#fccfeb` |
| `--color-pink-200` | `#ffade0` |
| `--color-pink-300` | `#f17ec5` |
| `--color-pink-400` | `#e557af` |
| `--color-pink-500` | `#be378a` |
| `--color-pink-600` | `#91306c` |
| `--color-pink-700` | `#6b2450` |
| `--color-pink-800` | `#441d35` |
| `--color-pink-900` | `#2e0f22` |

#### Purple ladder
| Step | Hex |
|---|---|
| `--color-purple-0` | `#f8f7fd` |
| `--color-purple-100` | `#dad5fb` |
| `--color-purple-200` | `#c0b7f9` |
| `--color-purple-300` | `#8e81e4` |
| `--color-purple-400` | `#7265c8` |

#### Yellow / sun ladder (used most as the actual visible accent)
- `#ffd88a`, `#ffc88a`, `#ffc757`, `#ffb71b`, `#ffb057`
- `#fffcf5`, `#fff5e0`, `#ffebc2` (light tints)
- This is the warm splash that pops against the cool teal page background

### Practical accent usage
On the live homepage, the **yellow ladder** + **green/teal mid-tones** carry most of the visible accent. The other ladders (pink, purple, blue) appear in product pages and ecosystem diagrams. The signature combo is `#f1f8f8` page + `#071614` text + `#ffb71b` highlight + `#dcd7cb` sand cards.

---

## Typography (the most distinctive in this collection)

Five custom woff2 faces:

| Font | Style | Usage |
|---|---|---|
| **TT Wormhole** Regular | Custom display | **Hero / brand wordmarks** — named after their Wormhole chip product |
| **Degular Display** Light + Medium | Premium display | Secondary headlines, large UI |
| **Neue Haas Unica Pro** Regular + Medium | Premium sans | Body, paragraphs |
| **Berkeley Mono** Regular + Bold | Premium dev mono | Technical labels, specs, code, metric callouts |
| **Noto Sans JP** | Google Fonts | Japanese localization (Tenstorrent has Japan presence — `--font-noto-jp` is a top-level token) |

**Five custom faces is rare** — most sites use 1–2. Combined with the exact teal-aqua palette, the type stack is the single biggest budget signal on the page: "we are not a typical startup."

CSS tokens:
```css
--font-tt-wormhole: ...
--font-degular-display: ...
--font-unica-pro: ...
--font-berkeley-mono: ...
--font-noto-jp: "Noto Sans JP", "Noto Sans JP Fallback"
```

**Why Berkeley Mono matters:** it's a paid mono ($75 personal, $200+ commercial) most known on Linear, Vercel-adjacent and serious dev-tool sites. Tenstorrent using it for *spec callouts* (not just code blocks) is a deliberate "this is a developer-first hardware company" signal.

**TT Wormhole** — likely commissioned, no public foundry listing matches (the `tt_` prefix is the giveaway). Names a product → the type. Same playbook as Cloudflare's "FT Kunst Grotesk" or Stripe's "Sohne."

---

## Border Radius System

Tailwind v4-style scale with named tokens:

| Token | Value (rem) | Pixels |
|---|---|---|
| `--radius-sm` | `.25rem` | 4px |
| `--radius-md` | `.375rem` | 6px |
| `--radius-lg` | `.5rem` | 8px |
| `--radius-xl` | `.75rem` | 12px |
| `--radius-2xl` | `1rem` | 16px |
| (utility) | `calc(N * var(--spacing))` | up to 24×4 = 96px |
| (utility) | `3.40282e38px` | full pill (max float) |

**Usage pattern:** sharp 4–8px on inline UI (chips, inputs, buttons), 12–16px on cards, full pills for status badges. Never extreme rounding (no 28px+ "consumer fintech" radius). Reads as "instrument-grade hardware brand."

---

## Layout

- Tailwind v4 with `--spacing: calc(1rem / var(--base-unit))` (10/16-base hybrid — same trick as guild.ai)
- Page max-width: standard Tailwind container scale
- Hero: edge-to-edge product photography / video (Galaxy/Blackhole hardware shots) with bold type overlay
- Generous vertical rhythm — sections are tall, not cramped

**Page structure (top → bottom):**
1. Nav — Products / Developers / Customers / Company / Newsroom + region/language switcher (incl. JP)
2. **Hero — *"Where AI Runs"*** + product video / hardware photography + "Watch TT-Deploy" CTA
3. Product overview tiles — Cards (Blackhole®, $999+) / Workstations (TT-QuietBox™, $9,999+) / Servers (Galaxy™, $70,000+)
4. Software section — TT-Forge™ open-source MLIR compiler (PyTorch / JAX / ONNX support)
5. **Animated scrolling timeline** — "computer innovations between 1950 and today" — positions Tenstorrent in lineage
6. Customer / partner ecosystem
7. Open-source / "own your silicon future" section (philosophical hook)
8. Newsroom / press
9. Footer with extensive product nav, legal, region/lang switchers

---

## Brand Voice (informs design)
Distinctive lines (verbatim):
- *"Where AI Runs"*
- *"AI is changing the laws that once governed computing"*
- *"Our architectures are open, and our software is open source so you can edit, select, fork, and own your silicon future"*
- *"Compute for every scale"*

Voice patterns: **technical precision + philosophical conviction.** The site sells a *worldview* (sovereign compute, anti-lock-in) alongside the SKUs. Every product is named: Wormhole, Blackhole, Grayskull (older), Galaxy, QuietBox, TT-Forge, TT-Deploy. The naming is sci-fi-cosmic + utility, very He-Man / cosmology-coded — adds personality without compromising credibility.

Design echoes voice: the unusual teal-aqua palette and custom-named display font reinforce "we build at the chip + identity level — we own the whole stack."

---

## Component Notes

### Hero
- Edge-to-edge media (video or hardware photography)
- Bold TT Wormhole headline overlay
- Single CTA, often a video play (Watch TT-Deploy)

### Product cards
- Sand `#dcd7cb` or pale teal `#f1f8f8` surfaces against page bg
- Berkeley Mono for spec callouts ("Starts at $999")
- Real product photography — no stylized illustrations

### Buttons / chips
- Conservative 4–8px radius
- Often outlined rather than filled (lab-instrument feel)

### Animated timeline
- Horizontal-scroll era markers (1950 → present)
- Positions Tenstorrent products on the silicon-history continuum
- Distinctive section that you don't find on competitor sites (Nvidia, AMD, Groq, Cerebras)

---

## Comparison to Other Saved References

| | tenstorrent.com | modal.com | workers.cloudflare.com | guild.ai | adaline.ai | varickagents.com |
|---|---|---|---|---|---|---|
| Category | AI silicon hardware | AI infra cloud | Edge serverless | AI agent control plane | AI dev infra | Enterprise AI ops |
| BG | **Pale teal `#f1f8f8`** | Dark `#181818`+ | Warm cream `#fffbf5` | Warm cream `#f8f6f3` + dark mode | Olive off-white `#f8f9f5` | Off-white `#f8f8f8` |
| Text | Near-black-teal `#071614` | Light gray on dark | Oxblood `#521000` | Black/off-white | Deep olive | `#202020` |
| Signature accent | **Yellow + sand** (`#ffb71b`, `#dcd7cb`) | **Lime green** `#7fee64` | **Cloudflare orange** `#ff4801` | Orange `#ff5500` selection | Olive `#4a6d47` | Electric blue `#0099ff` + navy `#10296e` |
| Type stack | **TT Wormhole + Degular Display + Neue Haas Unica Pro + Berkeley Mono + Noto JP** | Degular Display+Text + Fira Mono + KaTeX | FT Kunst Grotesk + Apercu Mono Pro | Syndicat Grotesk + Suisse Neue + Suisse Mono | Akkurat + fragmentMono | Framer default |
| Custom typeface? | **Yes (TT Wormhole, named after their chip)** | No | Yes (FT Kunst commissioned) | No (off-the-shelf) | No | No |
| Token ladders | **5 full ladders** (blue/green/pink/purple/yellow × 0–900) | 16-step gray + named ladders + dataviz | Semantic tokens × light+dark | Single brand colors | Material 3 surface tiers | Single blue ladder |
| Localization | **JP** (Noto Sans JP) | English only | Multiple | English | English | English |
| Distinguishing trick | **Pale teal-aqua page + chip-named typeface + 5-ladder token system + sci-fi product naming** | Lime accent + 16-step gray + KaTeX math notation | Bracket-corner annotations + Three.js wireframe globe | Orange selection + dot-grid gradient hero | Material 3 surface tiers | Square CTAs + SVG particle wave |
