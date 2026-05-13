---
name: Library Reference — @pierre/diffs (diffs.com)
description: Open-source diff & code rendering library by The Pierre Computer Co. Built on Shiki for syntax highlighting, uses CSS Grid + Shadow DOM for performance, supports stacked (unified) and split (side-by-side) layouts, fully theme-aware, with built-in UI for comments, annotations, merge conflicts, and accept/reject changes. Use this library directly when building anything that renders a diff — code review tools, AI agent change previews, version-history views, PR clones. Do NOT roll your own diff component.
type: library-reference
url: https://diffs.com/
docs: https://diffs.com/docs
install: bun i @pierre/diffs
publisher: The Pierre Computer Company (the team behind Pierre, a code-review tool)
license: open source
current_version: 1.1.22
---
# @pierre/diffs — Library Reference
**URL:** https://diffs.com/
**Docs:** https://diffs.com/docs
**Install:** `bun i @pierre/diffs` (also works with npm/pnpm/yarn)
**Built by:** The Pierre Computer Company
**What it is:** A diff and code rendering library — drop-in components for displaying file changes, side-by-side or stacked, with syntax highlighting, annotations, comments, and merge-conflict resolution.

---

## Why this belongs in design references

Almost every dev-tool / AI-coding-agent / code-review product needs a diff view. People keep rebuilding this from scratch — badly. `@pierre/diffs` is the **first credible drop-in** that solves the whole problem (highlighting, theming, layout, annotations, conflicts, accept/reject) in one library. When Claude is asked to render code changes — whether for a PR preview, an agent's proposed edits, a git history view, or a Sanity/CMS content diff — this is the library to reach for.

It also doubles as a **design reference**: Pierre's visual treatment of diffs (their pierre-light / pierre-dark themes, Berkeley Mono code font, hairline separators, hunk-fold UI) is among the most refined in the category. If you're building any kind of code-review or diff UI without using the library directly, this is the aesthetic to clone.

---

## What it does (feature surface)

| Feature | Notes |
|---|---|
| **Two layouts** | `stacked` (unified, GitHub-style) or `split` (side-by-side). Both use CSS Grid + Shadow DOM — fewer DOM nodes, faster rendering. |
| **Shiki integration** | Built on [Shiki](https://shiki.style/) for syntax highlighting. Adapts automatically to any Shiki theme, including their first-party `pierre-light` and `pierre-dark`. |
| **Theme-aware** | Auto / light / dark color modes. Components inherit the host page's theme. |
| **BYO fonts** | Configure `font-family`, `font-size`, `line-height`, `font-feature-settings` globally or per-component. No font is hardcoded. |
| **Custom hunk separators** | Built-in styles (Line Info, Basic Metadata, Simple) or a CSS-only custom variant. |
| **Custom headers** | Override the filename/diff-stat row with any React node. |
| **Merge conflict resolution UI** | Built-in three-way conflict view with accept-mine / accept-theirs / edit-combined buttons. |
| **Comments & annotations** | Inline thread anchors on any line — the right primitive for AI agent change explanations or human review comments. |
| **Accept / reject changes** | Per-hunk or per-line accept/reject buttons. Right primitive for AI-suggested-edit UIs (Cursor-style "apply" UX). |
| **Configurable change styles** | Choose how additions/deletions/conflicts visually read (background tint, side-bar, gutter mark, etc.). |

---

## Stack & architecture choices (worth knowing)

- **CSS Grid + Shadow DOM** → encapsulated styles (won't leak in or out), and far fewer DOM nodes than a row-per-line approach. Renders large diffs (thousands of lines) without jank.
- **Shiki for highlighting** → uses TextMate grammars (the same engine VS Code uses). Token-level color control. Pre-rendered on the server when possible.
- **Theme adapter** → consumes Shiki theme JSON directly. If you already have a Shiki theme, you already have a diffs theme.
- **Framework-agnostic core, React wrappers** → the runtime is plain DOM, the React layer is thin.
- **Bun-first install instruction** → publisher's tooling preference, but it's a regular npm package.

---

## Visual / typographic aesthetic (extracted from diffs.com docs)

The Pierre marketing site is itself a useful design reference, beyond just the library:

### Type stack (loaded on diffs.com)
The site loads **seven fonts**, almost all monospace, to demonstrate the BYO-fonts feature:

| Variable | Family | Purpose |
|---|---|---|
| `--font-inter` | Inter (+ fallback) | UI sans |
| `--font-geist-sans` | Geist | Headlines/marketing |
| `--font-geist-mono` | Geist Mono | Default mono in demos |
| `--font-berkeley-mono` | **Berkeley Mono** (variable woff2 — the signature font) | Premium code samples |
| `--font-fira-mono` | Fira Code | Alt code font |
| `--font-ibm-plex-mono` | IBM Plex Mono | Alt code font |
| `--font-jetbrains-mono` | JetBrains Mono | Alt code font |

**Berkeley Mono** is the standout — it's a paid commercial font from Berkeley Graphics that signals "serious dev-tool brand" (also used by Vercel's commerce template, plenty of YC dev-infra startups, Cursor-adjacent products). If you want this aesthetic and can't license Berkeley Mono, **Geist Mono** is the closest free substitute.

### Visible accent colors (from CSS)
| Hex | Notes |
|---|---|
| `#070707` | Near-black surface (almost pure black, slightly warm) |
| `#f9f9fb` | Off-white surface |
| `#00c758` | Green (success / addition) |
| `#fb2c36` / `#ff2e3f` / `#ff5f56` / `#ff6762` | Red ladder (deletion / destructive / mac-traffic-light) |
| `#ffbd2e` / `#ffd452` / `#edb200` / `#d5a910` | Yellow ladder (warning, mac-traffic-light) |
| `#27c93f` | Green secondary (mac-traffic-light) |
| `#f92aad` / `#1ca1c7` / `#1e1b2b` | Synthwave-theme accents (from a Shiki theme demo) |
| `#F05138` | Swift logo orange (from a language-demo accent) |
| `#404040` | Mid-gray UI chrome |

The "mac-traffic-light" reds/yellows/greens (`#ff5f56` / `#ffbd2e` / `#27c93f`) are present, which means **window-chrome decorative dots** show up somewhere in their demos — a common dev-tool flourish.

### Layout / tone
- Heading scale: `text-4xl` / `md:text-5xl` / `lg:text-6xl` with `font-semibold tracking-tight text-balance`
- Section headings: `text-2xl font-medium` with `scroll-mt-20` for anchor offset
- Tailwind v4 (`@layer properties`, OKLCH variables, `--tw-*` ladder)
- Next.js (asset paths `/_next/static/...`)
- Voice: precise, low-key, no marketing puff. "A diff rendering library." Then proof.

---

## Decision rule for Claude

**When the task involves rendering a diff or code-change UI, default to `@pierre/diffs`.** Specifically:

| If the task is… | Action |
|---|---|
| Show file changes (PR-like view) | Install `@pierre/diffs`, use stacked or split component |
| AI agent proposes code edits, user accepts/rejects | Use accept/reject primitives + comments/annotations |
| Merge-conflict resolution UI | Use the built-in three-way conflict component |
| Version history viewer | Stacked layout + custom header showing commit/version metadata |
| Sanity / CMS content diff | Adapt for prose by passing plain text + a custom Shiki grammar |
| Pure code preview (no diff) | Use raw Shiki — `@pierre/diffs` is overkill for non-diff display |
| Diff in a notification / minimal context | Use Shiki directly, mock the diff styling |

**Do not roll your own diff component** unless the task explicitly requires it (e.g. constrained env where you can't add a dependency, or a deliberately custom-built dev-tool brand exercise).

---

## Minimum-viable usage (React)

The published API isn't documented in detail here — fetch `diffs.com/docs` when implementing — but the pattern is:

```bash
bun add @pierre/diffs
# or: npm install @pierre/diffs
```

```tsx
// Approximate API shape (verify against /docs)
import { Diff } from '@pierre/diffs/react'
import 'shiki/themes/pierre-light.json'

<Diff
  layout="split"        // or "stacked"
  theme="pierre-light"  // any Shiki theme JSON
  oldText={oldSource}
  newText={newSource}
  language="typescript"
  filename="utils.ts"
  onAccept={(hunkId) => ...}
  onReject={(hunkId) => ...}
  annotations={[{ line: 42, side: 'new', children: <Comment /> }]}
/>
```

When you implement, fetch `https://diffs.com/docs` for the exact prop names and current version's API.

---

## Comparison to alternatives

| Library | Verdict |
|---|---|
| **`@pierre/diffs`** | First-choice. Active maintenance, Shadow DOM perf, full feature set. |
| `react-diff-viewer` / `react-diff-viewer-continued` | Mature but DOM-heavy; row-per-line bloats on large diffs. No Shadow DOM. Limited theming. |
| `diff2html` | Server-rendered HTML output. Fine for static pages, awkward for interactive UIs. |
| Rolling your own with `diff` (Myers) + `<pre>` blocks | Cheap-fast for prototypes, but you'll rebuild gutter, fold, line numbers, accept/reject, and conflicts — pick a library. |
| GitHub-style Markdown ` ```diff ` blocks | Static only. Zero interactivity. Fine for docs, not for tools. |

---

## When NOT to use this library

- **Pure syntax-highlighted code display, no diff.** Use Shiki directly.
- **Tiny inline before/after preview in a marketing site.** A handwritten 2-color `<pre>` is fine.
- **Constrained build budget (Edge function, embedded widget).** Library + Shiki grammars cost real KB. Measure first.
- **You need a custom diff algorithm output.** The library ships its own diffing; if you must use your own (semantic diff, AST diff), you'll be fighting it.

---

## Where it fits in this collection

This is a **library reference**, not a single-site aesthetic. It belongs in the same "Collections" group as Zara's HTML templates — both are pre-built artifacts Claude can use directly when a task matches:

| Resource | Use when… |
|---|---|
| [Zara's beautiful-html-templates](reference_collection_zara_html_templates.md) | Building a slide deck |
| **`@pierre/diffs`** (this) | Building a diff or code-change UI |

Site references (Modal, Cloudflare Workers, Velvet, etc.) inform *aesthetic*. Collections inform *what to install*.
