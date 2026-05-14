# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

A single-page static cheat sheet for Go + gRPC + Hexagonal Architecture, deployed via GitHub Pages. No build step, no dependencies — the entire site is `index.html`.

## Running locally

```bash
open index.html
# or
python3 -m http.server 8080
```

## Architecture

Everything lives in one file: `index.html`. It is structured as:

1. **`<style>`** — all CSS using custom properties (`--go`, `--grpc`, `--hex`, `--amber`) for the three-pillar color system. No external CSS.
2. **`<header>` / `<nav>`** — sticky nav with IntersectionObserver-driven active state (plain JS at bottom of file).
3. **`<main>`** — eight `<section id="...">` blocks, each containing `.card` elements.
4. **`<script>`** — minimal IntersectionObserver that syncs nav highlights to the visible section.

### Card anatomy

Each card follows a fixed structure:
```html
<div class="card go|grpc|hex">
  <div class="ch">          <!-- card header: icon, label, freq badge -->
  <div class="td">          <!-- Thai description prose -->
  <pre><code>...</code>     <!-- syntax-highlighted code (manual span classes) -->
</div>
```

Syntax highlighting is manual via `<span>` with classes: `.kw` (keyword), `.fn` (function), `.str` (string), `.cm` (comment), `.tp` (type), `.nu` (number).

### Frequency badges

Cards carry one of three `.freq` classes that map to the legend dots:
- `.freq.a` — green — ใช้ทุกวัน (daily)
- `.freq.o` — amber — ใช้บ้าง (sometimes)
- `.freq.r` — red — ใช้น้อย (rarely)

### Color / theme system

| Variable | Color | Represents |
|---|---|---|
| `--go` | `#00ADD8` | Go language |
| `--grpc` | `#7C4DFF` | gRPC / proto |
| `--hex` | `#00E5A0` | Hexagonal arch |
| `--amber` | `#FFB830` | Wire-up / combined |

Section dots (`.sdot`), card hover borders, nav link colors, and tag badges all derive from these four variables.
