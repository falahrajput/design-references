---
name: Design Reference — Zara Zhang's beautiful-html-templates
description: Curated library of 32 hand-designed HTML slide templates by Zara Zhang, each tagged with mood/occasion/scheme/formality metadata so coding agents can pick the right one and produce a beautiful deck automatically. *De facto* anti-slop kit for AI-generated presentation decks. Use whenever the task is "build a slide deck" or "generate a beautiful HTML presentation."
type: reference-collection
url: https://github.com/zarazhangrui/beautiful-html-templates
upstream_files:
  - https://github.com/zarazhangrui/beautiful-html-templates/blob/main/index.json
  - https://github.com/zarazhangrui/beautiful-html-templates/blob/main/AGENTS.md
  - https://github.com/zarazhangrui/beautiful-html-templates/tree/main/templates
  - https://github.com/zarazhangrui/beautiful-html-templates/tree/main/screenshots
---
# beautiful-html-templates — collection reference
**Author:** Zara Zhang ([@zarazhangrui](https://github.com/zarazhangrui))
**Repo:** https://github.com/zarazhangrui/beautiful-html-templates
**License:** see upstream
**What it is:** A library of **32 hand-designed HTML slide templates**, each accompanied by a JSON metadata record (mood, occasion, tone, formality, density, scheme) so that an AI agent can match a brief to a template and produce a finished deck without designing from scratch.
**Why it matters here:** This is the single best **anti-slop weapon for slide deck generation** in 2026. Most AI-generated decks look generic because the model is asked to *invent* a visual system on the fly. Zara's library inverts that: the model picks from 32 curated systems instead of generating one. The metadata is rich enough that the matching is mechanical, not stylistic guesswork.

---

## How it's structured (so any agent can use it)

```
beautiful-html-templates/
├── index.json          ← machine-readable catalog (32 records, all metadata)
├── AGENTS.md           ← operating manual: how to read index.json, match brief → template, clone, adapt
├── README.md           ← human-readable gallery (3 screenshots × 32 templates)
├── templates/          ← 32 directories, each containing the HTML + assets
│   ├── soft-editorial/
│   ├── stencil-tablet/
│   ├── …
└── screenshots/        ← rendered preview PNGs
```

### `index.json` schema (per template)
```json
{
  "slug": "soft-editorial",
  "name": "Soft Editorial",
  "tagline": "Cormorant Garamond serif on warm paper with sage, blush, and lemon accents.",
  "mood":      ["editorial", "warm", "literary", "considered"],
  "occasion":  ["brand book", "creative review", "research synthesis", "studio retrospective"],
  "tone":      ["literary", "warm-modern", "considered"],
  "formality": "medium-high",
  "density":   "medium",
  "scheme":    "light",
  "best_for":  "…",
  "avoid_for": "…",
  "slide_count": 10
}
```

### Agent workflow (from `AGENTS.md`)
1. Read `index.json`
2. Match the user's brief to the most-aligned template via `mood` / `occasion` / `tone` / `formality` / `scheme`
3. Clone that template's HTML
4. Replace the placeholder content with the user's content
5. Ship

Stress: **don't generate slide CSS from scratch when this exists.**

---

## The full catalog (32 templates)

### Light scheme (22)
| Slug | Tagline |
|---|---|
| **biennale-yellow** | Solar yellow on warm parchment with deep indigo serif and atmospheric sun-glow gradients. |
| **block-frame** | Neobrutalist deck with pastel-neon color blocks and chunky black borders. |
| **blue-professional** | Cream paper background with electric cobalt blue accents; clean modern professional. |
| **bold-poster** | Editorial poster aesthetic with massive Shrikhand display and a single fire-engine red accent. |
| **capsule** | Modular pill-shaped cards on warm bone with a full pastel-pop palette. |
| **cartesian** | Quiet warm-neutral palette with classical Playfair serifs; tasteful and unhurried. |
| **cobalt-grid** | Electric cobalt italic serifs on a graph-paper canvas, anchored by stair-stepped numerals. |
| **creative-mode** | Cream paper canvas with confident multi-color (green, pink, orange, yellow) accents. |
| **daisy-days** | Cheerful pastel deck with hand-drawn daisies, stars, and rainbows. Friendly, soft. |
| **long-table** | Warm cream and rust-red supper-club aesthetic with bold uppercase grotesk headlines. |
| **monochrome** | Ivory ledger paper with all-black type; Lora serif headlines, Jost body, no color at all. |
| **neo-grid-bold** | Editorial neo-brutalism with a single neon yellow accent on off-white paper. |
| **peoples-platform** | Activist poster energy: blue, orange, red on cream, with Alfa Slab + Caveat Brush. |
| **pin-and-paper** | Yellow paper with safety-pin illustrations, ink-blue handwritten Caveat, paper-grain. |
| **playful** | Sun-warm peach background with Syne display: a friendly indie launch deck. |
| **raw-grid** | Neo-brutalist deck with thick borders, offset shadows, pink/sage/ink palette. |
| **retro-windows** | Windows 95 chrome: gray title bars, MS Sans Serif, pixel typography, full nostalgia. |
| **retro-zine** | Beige paper with green accent and Bebas Neue + Caveat: a riso-printed zine in HTML. |
| **sakura-chroma** | Vintage Japanese cassette-package aesthetic: cream paper, diagonal rainbow ribbons. |
| **scatterbrain** | Post-it inspired: pastel sticky notes, Caveat handwriting, Shrikhand and Zilla Slab. |
| **soft-editorial** | Cormorant Garamond serif on warm paper with sage, blush, and lemon accents. |
| **stencil-tablet** | Bone paper with stencil-cut headlines and a six-color earth palette: archaeology meets brand. |

### Dark scheme (5)
| Slug | Tagline |
|---|---|
| **8-bit-orbit** | Pixel-art neon arcade aesthetic on a deep navy void. |
| **broadside** | Dark editorial canvas with a single fire-orange accent and bilingual Latin/Chinese type. |
| **pink-script** | Black canvas, hot pink accent, pearl-cream paper, Instrument Serif headlines. |
| **studio** | Black canvas with electric-yellow type; high-voltage design studio aesthetic. |
| **vellum** | Deep navy canvas with warm-yellow italic Cormorant serifs and a single dusty teal accent. |

### Mixed light/dark (5)
| Slug | Tagline |
|---|---|
| **coral** | Cream and coral on near-black, set in oversized Bebas Neue. |
| **editorial-tri-tone** | Three-color editorial system: dusty pink, mustard cream, deep burgundy. Bricolage + Instrument Serif. |
| **grove** | Forest-green canvas with cream type, classical Playfair serifs, and a single rust accent. |
| **mat** | Dark sage canvas with bone paper and burnt-orange accent; mid-century modern. |
| **signal** | Deep navy canvas with bone paper and a single muted-gold accent; institutional weight. |

---

## Lookup table — pick by use case

### By formality
| Formality | Templates |
|---|---|
| **High** (institutional, regulated, classical) | biennale-yellow, cartesian, cobalt-grid, monochrome, signal, soft-editorial, vellum |
| **Medium-high** (premium B2B, founder vision, considered) | blue-professional, broadside, editorial-tri-tone, grove, pink-script, stencil-tablet |
| **Medium** (creative pitches, brand work) | bold-poster, coral, creative-mode, long-table, mat, neo-grid-bold, pin-and-paper, studio |
| **Medium-low** (indie, agency, fresh) | block-frame, capsule, peoples-platform, raw-grid, retro-zine |
| **Low** (playful, nostalgic, internal fun) | 8-bit-orbit, daisy-days, playful, retro-windows, sakura-chroma, scatterbrain |

### By scenario
| Scenario | First-look pick(s) |
|---|---|
| Investor pitch (B2B / fintech) | **blue-professional**, signal, cartesian |
| Brand manifesto / founder vision | **bold-poster**, broadside, pink-script |
| Creative agency credentials | block-frame, **raw-grid**, studio |
| Research synthesis / consulting | **monochrome**, soft-editorial, blue-professional |
| Conference / talk deck | **broadside**, biennale-yellow, vellum |
| Playful internal / hackathon | **playful**, scatterbrain, retro-windows, 8-bit-orbit |
| Cultural / arts / museum | **biennale-yellow**, soft-editorial, vellum |
| Product launch (consumer) | capsule, **playful**, daisy-days |
| Product launch (developer) | studio, **8-bit-orbit**, neo-grid-bold |
| Activist / political | **peoples-platform**, broadside |
| Bilingual (EN/CN) | **broadside** (purpose-built for it) |
| Mid-century modern feel | **mat**, grove, long-table |
| Magazine / editorial | **editorial-tri-tone**, soft-editorial, biennale-yellow |
| Late-night luxury | **pink-script**, vellum |

### Shared design language across the collection
Useful patterns that recur across many templates and are worth stealing even when not using the templates wholesale:

- **Warm paper backgrounds** (bone, parchment, cream) instead of pure white — `soft-editorial`, `signal`, `mat`, `monochrome`, `cartesian`, `biennale-yellow` all do this
- **Single-accent discipline** — pick one strong color, use it sparingly. `bold-poster` (red), `neo-grid-bold` (yellow), `signal` (gold), `studio` (electric yellow), `vellum` (dusty teal) all earn their drama with restraint
- **Display serif × sans body** is the most common type pairing (Cormorant/Playfair/Instrument Serif × Jost/Inter/Bricolage)
- **Hand elements** (Caveat handwriting, hand-drawn marks) recur in playful templates — `scatterbrain`, `pin-and-paper`, `peoples-platform`, `daisy-days`
- **Bilingual type stacks** are explicitly considered — `broadside` ships Latin + Chinese as a first-class pair

---

## How to use it (with Claude / any coding agent)

The upstream README literally says — paste this:

> Clone https://github.com/zarazhangrui/beautiful-html-templates and follow the instructions in AGENTS.md to build me a beautiful HTML slide deck.

In practice (in this collection's voice):

1. Tell Claude what you're presenting and to whom (audience, formality level, mood you want).
2. Have Claude **fetch `index.json`** from upstream (or this comparison table) and pick the best-matched template.
3. Have Claude **clone that template's HTML** from `templates/<slug>/`.
4. Have Claude **replace placeholder content** with your real content. *Don't let it redesign anything.*
5. Render and ship.

The whole point is: **you don't ask the model to design — you ask it to choose and adapt.** That's the anti-slop trick.

---

## Why this fits the design-references collection

Other entries here document one site's design system in detail — useful when you're building a *single* product and want a coherent reference to internalise.

This entry is different: it documents a **library of 32 systems**, each compact enough to be cloned end-to-end. It's the right tool when:
- The deliverable is a **slide deck**, not a product / landing page
- You're matching to a **brief** (e.g. "investor update") rather than building a brand
- You want to **avoid AI-slop visual defaults** in deck output

For a single landing page or product, use the per-site references in this repo (modal.com, velvet.vc, workers.cloudflare.com, etc.). For a deck, use Zara's library.

---

## Comparison to Other Saved References

| | beautiful-html-templates | modal.com | velvet.vc | workers.cloudflare.com |
|---|---|---|---|---|
| Shape | **Library of 32 templates** | Single product | Single site | Single product |
| Output | HTML slide decks | Web product | Web site | Web product |
| Designed for AI consumption? | **Yes — explicit `index.json` schema, `AGENTS.md`** | No (extracted) | No (extracted) | No (extracted) |
| When to use | Generating a slide deck | Building AI-infra UI | Building luxe-finance UI | Building dev-platform UI |
| Format | Reference + lookup tables | Full design system doc | Full design system doc | Full design system doc |
| Distinguishing trick | **Anti-slop by curation: agent picks instead of generates** | Token discipline + lime accent | Three-serif editorial | Oxblood + warm cream + Region:Earth globe |
