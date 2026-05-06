# Design References

A living collection of design systems extracted from sites that are visually interesting or useful as references.

Each reference file documents: exact color tokens (with hex codes), typography stack and scale, border-radius system, layout structure, component specs, brand voice, and a comparison row against other references in this collection.

## Index

- [tahahossain.com](reference_design_tahahossain.md) — Blueprint editorial brutalism. Cream `#f6f5f1`, red/green/blue hairline registration lines, Unica 77 + Diatype Mono + EB Garamond, 24px grid system.
- [zerotoagent.com](reference_design_zerotoagent.md) — Premium B2B minimalism. White bg, bold geo sans-serif, blue/teal accents, operator voice ("no theatre"), custom tenex SVG icons.
- [useallowance.com](reference_design_useallowance.md) — iOS-native consumer fintech. Pure white, forest green `#0A7C52`, SF Pro Rounded, 100px pill buttons, 12–28px rounded cards, Lucide 1.5 stroke icons. YC-backed.
- [adaline.ai](reference_design_adaline.md) — AI-infra dev platform. Warm off-white `#f8f9f5`, olive-forest primary `#4a6d47`, deep-olive text, Akkurat + fragmentMono, Material 3 surface tokens, conservative 8–12px radius.
- [guild.ai](reference_design_guild.md) — AI agent control plane. Warm cream `#f8f6f3` + black, full dark mode (`#141413`), Syndicat Grotesk + Suisse Neue, GitHub-dark inline code, signature orange `#ff5500` selection accent.
- [varickagents.com](reference_design_varickagents.md) — Enterprise AI ops. Off-white `#f8f8f8`, electric blue `#0099ff` + navy `#10296e` CTAs, square-cornered buttons, signature SVG `<animateMotion>` particle-wave hero. Built in Framer.
- [generalintelligencecompany.com](reference_design_generalintelligencecompany.md) — Boutique applied-AI-lab editorial. PP Mondwest display serif + custom "af" sans + Geist Mono, warm cream `#f9faf7`, hand-drawn sun glyph, generous 24px card radius. Tailwind v4. Monochrome warm-grayscale (no brand hue).
- [velvet.vc](reference_design_velvet.md) — Couture editorial private-capital network. Three serifs (Gloock display + Calluna body via Typekit + Geist Sans/Mono), warm cream `#fbf8f3` + stone `#cdbfb5`, multi-hue magazine accents (oxblood `#831c1a`, rust `#d83d26`, teal `#0089a2`, sand `#ddca9e`), 28–40px card radius, full-bleed video hero.
- [modal.com](reference_design_modal.md) — AI infra cloud with extreme token discipline. Degular Display+Text+base via Typekit, signature lime green `#7fee64`, 16-step gray ladder + named green/blue/orange ladders + 8-color dataviz palette, dark surfaces (`#181818`+), sharp 5–10px radius, Fira Mono + KaTeX. SvelteKit.
- [workers.cloudflare.com](reference_design_workerscloudflare.md) — Cloudflare Workers / edge serverless. Warm cream `#fffbf5`, signature oxblood text `#521000` (not black), Cloudflare orange `#ff4801` accent + AI green `#5eff3a` sub-accent, FT Kunst Grotesk + Apercu Mono Pro, semantic token system (foreground/background/accent/ai ladders × light+dark mode), bracket-corner annotation pattern, Three.js "Region: Earth" wireframe globe. Built in Astro.

## Collections (libraries, not single sites)

- [Zara Zhang's beautiful-html-templates](reference_collection_zara_html_templates.md) — Library of **32 hand-designed HTML slide templates** with machine-readable metadata (`index.json`) so coding agents can match a brief to a template and produce a finished deck without designing from scratch. *De facto* anti-slop kit for AI-generated decks. Use when the deliverable is a slide deck.

## Demos

- [Particle Wave Animation](demos/particle-wave.html) — Recreation of the Varick Agents hero animation. Pure SVG with `<animateMotion>` along invisible paths. No JS frameworks, no canvas. Open in a browser.
- [Rotating Wireframe Globe](demos/rotating-globe.html) — Recreation of the Cloudflare "Region: Earth" globe. Three.js wireframe sphere (custom lat/lng grid), animated great-circle arcs between cities, bracketed annotation callouts. Open in a browser.

## How to use this collection (looking for inspiration)

Two ways:

### 1. By aesthetic — quick lookup table
Find the row that matches the vibe you're after, then open the linked reference for full tokens / fonts / radius / component recipes.

| Looking for… | Open these refs |
|---|---|
| **Editorial / literary / boutique studio** | [generalintelligencecompany.com](reference_design_generalintelligencecompany.md), [velvet.vc](reference_design_velvet.md), [tahahossain.com](reference_design_tahahossain.md) |
| **Premium dev infrastructure** | [modal.com](reference_design_modal.md), [workers.cloudflare.com](reference_design_workerscloudflare.md), [guild.ai](reference_design_guild.md), [adaline.ai](reference_design_adaline.md) |
| **Enterprise B2B / operations** | [varickagents.com](reference_design_varickagents.md), [zerotoagent.com](reference_design_zerotoagent.md) |
| **Consumer / fintech / soft rounded** | [useallowance.com](reference_design_useallowance.md) |
| **Couture / luxe / multi-serif editorial** | [velvet.vc](reference_design_velvet.md) |
| **Display serif headline + sans body** | [generalintelligencecompany.com](reference_design_generalintelligencecompany.md) (PP Mondwest), [velvet.vc](reference_design_velvet.md) (Gloock + Calluna), [tahahossain.com](reference_design_tahahossain.md) (EB Garamond) |
| **Warm cream backgrounds (not pure white)** | [workers.cloudflare.com](reference_design_workerscloudflare.md), [guild.ai](reference_design_guild.md), [generalintelligencecompany.com](reference_design_generalintelligencecompany.md), [velvet.vc](reference_design_velvet.md), [adaline.ai](reference_design_adaline.md) |
| **Dark mode done well** | [modal.com](reference_design_modal.md), [workers.cloudflare.com](reference_design_workerscloudflare.md), [guild.ai](reference_design_guild.md) |
| **Discipline-grade token systems** | [modal.com](reference_design_modal.md) (named ladders + dataviz), [workers.cloudflare.com](reference_design_workerscloudflare.md) (semantic tokens × light+dark) |
| **Hero animation ideas** | [varickagents.com](reference_design_varickagents.md) (SVG particle wave), [workers.cloudflare.com](reference_design_workerscloudflare.md) (Three.js globe), [guild.ai](reference_design_guild.md) (choreographed pulse + logo marquee) |
| **Building a slide deck (HTML)** | [Zara's beautiful-html-templates](reference_collection_zara_html_templates.md) — 32 curated templates, agent-readable index |
| **Code-forward dev sites (real code on landing)** | [guild.ai](reference_design_guild.md), [modal.com](reference_design_modal.md), [workers.cloudflare.com](reference_design_workerscloudflare.md) |
| **Square / brutalist / blueprint** | [varickagents.com](reference_design_varickagents.md) (square CTAs), [tahahossain.com](reference_design_tahahossain.md) (hairline grid) |

### 2. Hand the URL to Claude

When you're starting a design task, paste this repo URL or a specific reference URL into Claude alongside your prompt:

> "I'm building a landing page for [X]. Use the aesthetic from
> https://github.com/falahrajput/design-references/blob/main/reference_design_modal.md
> as a reference — match the token system, type stack, and accent
> color discipline."

Claude will fetch the reference and apply the documented tokens / fonts / radius / component patterns. The references are written specifically to be Claude-readable: every hex code is exact, every font has a fallback, every component pattern has a code recipe.

### 3. Compare across references

Each reference file ends with a comparison table against the others. Skim those to triangulate — e.g. if you want "warm cream + signature accent + custom serif," the comparison rows make it obvious which 2–3 files to read in detail.
