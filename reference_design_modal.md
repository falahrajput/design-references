---
name: Design Reference — modal.com
description: AI infrastructure dev-tool with extreme-discipline design tokens. Degular display+text+base type system, signature lime green #7fee64, full color ladder system (gray/green/blue/orange/pale-green/dataviz tokens), warm dark surfaces, SvelteKit. Use when referencing this aesthetic for technical infra products that want vibrant-but-systematic.
type: reference
url: https://modal.com/
---
# modal.com — Full Design Reference
**URL:** https://modal.com/
**Product:** Modal — cloud infrastructure for AI workloads (inference, training, batch, sandboxes, notebooks)
**Tagline:** *"AI infrastructure that developers love"*
**Pitch:** *"Run inference, training, and batch processing with sub-second cold starts, instant autoscaling"*
**Audience:** ML engineers / AI teams (devs at Hugging Face, Harvey, Tesla, Substack, Lovable in social proof)
**Tech stack:** **SvelteKit** (`/_app/immutable/assets/...`) + Tailwind v4 + Adobe Typekit (Degular family)

---

## Aesthetic / Mood
**Discipline-grade dev infrastructure with a vibrant lime accent.** Modal is one of the most **systematically tokenized** sites in this collection — dozens of explicit color ladders (`--color-c-gray-*`, `--color-c-green-*`, `--color-c-blue-*`, `--color-c-orange-*`, `--color-c-pale-green-*`) plus a full **dataviz palette** (8 distinct chart-friendly hues). Every value has a name. Every surface has a tier.

The signature accent is **lime green `#7fee64`** — bright, energetic, faintly retro-terminal. It's used for the gradient logo, key CTAs, success indicators, and code-output highlights. Combined with deep dark `#181818` surfaces and the **Degular** typeface (Ohno Type Co's contemporary geometric sans, used by Linear/Stripe-tier brands), it reads as "premium technical product run by people who think about typography."

If guild.ai is "warm warehouse editorial dev infra" and adaline.ai is "sage AI-infra," Modal is "clean-room dev infra with a green LED on the rack" — same enterprise-credible AI-infra category, but more systematic, more technical, and with the lime-green pulse of compute happening.

---

## Typography — three Degular variants + supporting

| Token | Font | Loaded via | Usage |
|---|---|---|---|
| (Typekit) | **Degular** | use.typekit.net/jcd8ppx.css | Default UI sans |
| (Typekit) | **Degular Display** | Typekit | Large headlines (more dramatic optical size) |
| (Typekit) | **Degular Text** | Typekit | Body text (optimised for paragraph) |
| `Goga` | Goga | self-host | Custom display moments |
| `Inter Variable` | Inter | self-host | Fallback / specific UI |
| `Fira Mono` | Fira Mono | self-host | **Code blocks** (Modal shows lots of Python) |
| `KaTeX_*` | KaTeX | self-host | Math typesetting (rare on landing pages — signals serious technical content) |

**Why this matters:** Degular is one of the few "dev-tool tier" typefaces with a true display/text/base optical-size system. Most sites use one weight of Inter and call it done; using **Degular Display for headlines + Degular Text for body** produces visibly better proportions at every size. Pair this with **Fira Mono** for code, and you're in Linear/Vercel/Stripe typography territory.

**Supporting note:** the presence of **KaTeX** is a tell — Modal documentation and landing-page diagrams include actual math notation for ML topics. Other AI-infra sites screenshot LaTeX; Modal renders it.

---

## Color Palette — the most systematic in this collection

Modal uses **named color ladders** rather than ad-hoc hex values. Each ladder is a 5–100 scale.

### Brand signature: lime green
| Token | Value | Usage |
|---|---|---|
| `--color-c-green-100` | `#7fee64` | **The signature lime** — logo, CTAs, success |
| `--color-c-green-90` | `#75d95c` | Hover state |
| `--color-c-green-80` | `#6ac355` | |
| `--color-c-green-70` | `#60ae4d` | |
| `--color-c-green-60` | `#569846` | |
| `--color-c-green-50` | `#4c833e` | |
| `--color-c-green-40` | `#416e36` | |
| `--color-c-green-30` | `#37582f` | Dark green sections |
| `--color-c-green-20` | `#2d4327` | |
| `--color-c-green-15` | `#273823` | |
| `--color-c-green-10` | `#222d20` | Near-black green |
| `--color-c-green-5` | `#1d231c` | Deepest |

### Pale green (success-tints, code highlight)
| Token | Value |
|---|---|
| `--color-c-pale-green-100` | `#c8f9b6` |
| `--color-c-pale-green-15` | `#3e4a3c` |
| `--color-c-pale-green-10` | `#272e27` |

### Gray ladder (backbone of UI surfaces)
| Token | Value |
|---|---|
| `--color-c-gray-0` | `#181818` (deepest dark) |
| `--color-c-gray-2` | `#1c1c1c` |
| `--color-c-gray-5` | `#242424` |
| `--color-c-gray-7` | `#272727` |
| `--color-c-gray-10` | `#2f2f2f` |
| `--color-c-gray-15` | `#3b3b3b` |
| `--color-c-gray-20` | `#464646` |
| `--color-c-gray-30` | `#5d5d5d` |
| `--color-c-gray-40` | `#747474` |
| `--color-c-gray-50` | `#8b8b8b` |
| `--color-c-gray-60` | `#a3a3a3` |
| `--color-c-gray-70` | `#bababa` |
| `--color-c-gray-80` | `#d1d1d1` |
| `--color-c-gray-90` | `#e8e8e8` |
| `--color-c-gray-100` | `#fff` |

A 16-step gray ladder. Most sites use 5–7. This signals dark-mode discipline.

### Blue ladder (`--color-c-blue-5` → `--color-c-blue-100`)
- `#1e2123` → `#91c8ef` (deep slate to light cyan)
- 12+ named steps

### Orange ladder (`--color-c-orange-5` → `100`)
- `#241f1c` → `#ffab5e`

### Almanac (sub-brand tertiary)
- `--color-almanac-dark-green: #3e5b3c`
- `--color-almanac-gray-green: #879483`
- `--color-almanac-lime-green: #17450c`

### Dataviz palette (signature: 8 hand-tuned chart hues)
| Token | Value |
|---|---|
| `--color-c-dataviz-primary-1` | `#adeaab` (soft lime) |
| `--color-c-dataviz-primary-2` | `#d9866b` (terracotta) |
| `--color-c-dataviz-primary-3` | `#ffc1f7` (pink) |
| `--color-c-dataviz-primary-4` | `#4aa19d` (teal) |
| `--color-c-dataviz-primary-5` | `#decb6c` (mustard) |
| `--color-c-dataviz-primary-6` | `#4fbe5f` (forest green) |
| `--color-c-dataviz-primary-7` | `#648fe0` (blue) |
| `--color-c-dataviz-primary-8` | `#8d324c` (wine) |
| `--color-c-dataviz-primary-other` | `#6d6161` |

These are **chart-optimised** — high contrast against both light and dark surfaces, distinguishable for color-blind users. Reusing this palette for analytics/data dashboards is a legit pattern.

### Most-used hex values (frequency)
| Frequency | Value | What |
|---|---|---|
| 39 | `#ffffff` | UI text |
| 26 | `#7fee64` | **Signature lime** |
| 24 | `#000000` | True black |
| 22 | `#ddffdc` | Pale green surface tint (very Modal-coded) |
| 14 | `#fff` | (same as ffffff) |
| 8 | `#17450c` | Almanac lime green |
| 6 | `#3e5b3c` | Almanac dark green |
| 6 | `#3971ed` | Saturated blue |

Note `#ddffdc` (pale green tint) — this is the surface that softly hints at the brand color without overusing the lime.

---

## Border Radius

Mixed system — Tailwind tokens + bespoke values:

| Value | Token | Usage |
|---|---|---|
| `2px` | — | Tight UI (chips, badges) |
| `3px` / `5px` | — | Small interactive elements |
| `0.25rem` (4px) | `--radius-sm` | |
| `0.3125rem` (5px) | — | |
| `0.375rem` (6px) | `--radius-md` | Default |
| `--radius-lg` | `0.5rem` (8px) | Buttons |
| `--radius-2xl` | `1rem` (16px) | Cards |
| `10px` | — | Specific component |
| `19px` | — | Specific component (likely a special card) |
| `100%` | — | Avatars, circles |
| `3.40282e38px` | — | Pills |

**Note:** Modal uses **smaller radius values** (2–10px range dominates) than editorial sites like Velvet (28–40px). This is intentional — sharper corners read more "technical/precise" than "luxe/tactile."

---

## Layout & Animation

Tailwind v4 system:
- `--breakpoint-sm: 40rem`, `md: 52.5rem`, `lg: 64rem`, `xl: 75rem`
- `--blur-xs: 4px`, `sm: 8px`, `md: 12px`, `xl: 24px` (used for overlays/glassmorphism)
- `--animate-pulse: pulse 2s cubic-bezier(.4, 0, .6, 1) infinite`
- `--animate-spin: spin 1s linear infinite`

**Page structure (top → bottom):**
1. Nav
2. Hero — gradient logo (green shades), tagline, signup + contact CTAs
3. Product lineup — Inference / Training / Sandboxes / Batch / Notebooks
4. Platform capabilities — AI-native runtime, distributed storage, multi-cloud scheduling
5. **Code examples** — Whisper transcription, LLM voice chat (real Python in Fira Mono)
6. Customer testimonials — Substack, Lovable case studies
7. Community testimonials — devs from Hugging Face, Harvey, Tesla
8. Footer

---

## Component Notes

### Hero
- Gradient SVG logo as the centerpiece (green-shaded, geometric)
- Degular Display tagline: *"AI infrastructure that developers love"*
- Two CTAs: signup + contact (sales)

### Code blocks
- Fira Mono, dark surface (`--color-c-gray-5`-ish)
- Syntax highlighting uses dataviz/brand colors (lime for keywords, pale green for output)
- Real, runnable Python — not mockups

### Buttons
- Primary CTA: lime green `#7fee64` background, dark text — high contrast, readable
- Smaller radius than typical SaaS (5–10px range)
- Some buttons use full pills, but most are precise rectangles

### Cards
- Dark surfaces from the gray ladder (`--color-c-gray-5/7/10/15`)
- Subtle borders from adjacent gray steps
- 16px (`--radius-2xl`) standard, 19px for special cases

### Pulse / spin animations
- Subtle pulse on status indicators (live deployments, cold-start counters)
- Spin on loaders

---

## Brand Voice (informs design)
- *"AI infrastructure that developers love"*
- *"Just Python"* — simplicity claim
- *"Sub-second cold starts, instant autoscaling"* — performance specifics, not vague claims
- Tone: technical confidence + accessibility. No corporate jargon. Real code on the landing page.

Design mirrors voice:
- **Token discipline** = "we sweat the details"
- **Lime green accent** = compute alive, signal of liveness
- **Degular Display + Fira Mono** = premium typography that says "we are good engineers AND good designers"
- **KaTeX rendering** = "we render math correctly because we're an AI infra company that understands the math"

---

## Reproducing this aesthetic — minimum viable kit

1. **Adopt the token-ladder discipline.** Define `--color-c-gray-{0..100}` etc. before you start designing pages. Most teams skip this; Modal's polish comes from doing it.
2. **Pick ONE signature accent** (Modal: lime `#7fee64`). Use it for logo, primary CTA, success states. Don't dilute by using 5 brand colors.
3. **Two-tier display type** (Display + Text variants of the same family). Degular if licensable; alternatives: Söhne Display + Söhne, GT Walsheim Display + Text, Inter (no display variant — adequate but not equivalent).
4. **Fira Mono for code.** JetBrains Mono and Geist Mono are reasonable alternatives.
5. **Dark surfaces tier 5/10/15/20** — not pure black. Pure `#000` reads cheap; `#181818 → #2f2f2f` is the premium zone.
6. **Smaller radius** (5–10px) than consumer apps. Sharper = more technical.
7. **Hand-tune a dataviz palette** if your product has charts. Colors that work in both light and dark, pass colorblind checks. Modal's 8-color set is a good template.

---

## Comparison to Other Saved References

| | modal.com | velvet.vc | generalintelligencecompany.com | guild.ai | adaline.ai | varickagents.com |
|---|---|---|---|---|---|---|
| Category | AI infra cloud | Private capital network | AI lab | AI agent control plane | AI agent platform | Enterprise AI ops |
| BG | Dark `#181818` ladder | Cream `#fbf8f3` | Cream `#f9faf7` | Cream `#f8f6f3` | Olive cream `#f8f9f5` | Off-white `#f8f8f8` |
| Display | **Degular Display** | **Gloock (didone serif)** | **PP Mondwest serif** | Suisse Neue | Akkurat | Bold geo sans |
| Body | Degular Text | **Calluna serif** | af (custom sans) | Syndicat Grotesk | Akkurat | Framer default |
| Mono | Fira Mono + KaTeX | Geist Mono | Geist Mono | (none prominent) | fragmentMono | (none) |
| Signature accent | **Lime `#7fee64`** | Multi-hue editorial | None — monochrome | Orange `#ff5500` | Olive `#4a6d47` | Electric `#0099ff` |
| Token discipline | **Extreme** (16-step gray ladder, 8 dataviz colors, named blues/oranges/greens) | Standard Tailwind v4 | Standard Tailwind v4 | Custom semantic | Material 3 surface tiers | Framer default |
| Radius | **5–10px** (sharper) | 28–40px (lush) | 24px + 50px pill | 4–20px | 8–12px | Square corners |
| Tech | **SvelteKit** | Next.js | Next.js | Next.js | Next.js + Tailwind v4 | Framer |
| Code in design | **Real Python + KaTeX math** | None | None | Inline TS snippets | Minimal | None |
| Distinguishing trick | **Lime + Degular + obsessive token system + math rendering** | Gloock+Calluna double-serif + couture palette | PP Mondwest + sun glyph | Orange selection + warm cream | Material 3 surface tiers | SVG particle wave + square CTAs |
