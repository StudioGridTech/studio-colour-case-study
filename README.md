## Studio Colour

**The colour kit for people who actually ship websites.**

A Chrome extension for designers and front-end developers: pick colours from anywhere, fix contrast in a click, build gradients, and extract any live site's design system straight to code — Bricks, Tailwind, theme.json and more.

[**Install (Chrome Web Store — coming soon)**](#) · [Architecture](ARCHITECTURE.md) · [Roadmap](ROADMAP.md) · [studiogrid.io](https://studiogrid.io)
---

## The problem

Designers working in WordPress and Bricks constantly pull colours and design decisions off the web — but the tools stop at "here's a hex code." Nothing turns a page you admire into the *tokens* you actually build with, and nothing makes fixing contrast a one-second job instead of a chore. Existing pickers are generic; none speak the language of the people shipping real sites.

## What I built

A self-contained Chrome (Manifest V3) extension, **built in vanilla JavaScript — no framework**, that closes that gap.

<p align="center">
  <img src="screenshots/01-picker.png" width="49%" alt="Eyedropper with magnifier loupe">
  <img src="screenshots/02-tokens.png" width="49%" alt="Design tokens exported to code">
</p>
<p align="center">
  <img src="screenshots/03-contrast.png" width="49%" alt="Contrast checker and one-click Fix">
  <img src="screenshots/04-gradient.png" width="49%" alt="Gradient studio">
</p>

- **Pro eyedropper** — a custom in-page picker with a magnifier loupe + pixel grid, plus Shift-to-multi-pick (which the native eyedropper can't do).
- **Contrast + one-click Fix** — WCAG & APCA grading that *climbs* to passing one tier at a time, moving only lightness so the hue stays on-brand.
- **Gradient studio** — linear & radial with draggable, positioned stops; copy-ready CSS or Tailwind.
- **Every colour space** — HEX → OKLCH → Display-P3, hand-written conversions with zero round-trip drift.
- **Design tokens → code** — point it at any live site and lift its colours, type scale, spacing, radii and shadows, formatted for your builder. *No competing tool does this.*

## How it's built

A quick map — full detail in **[ARCHITECTURE.md](ARCHITECTURE.md)**:

- Chrome **Manifest V3**, Side Panel API, **vanilla JS — no framework, no core dependencies**.
- Custom **picker engine**: captures the tab, overlays a canvas magnifier, samples pixels.
- Hand-written **colour-space maths**, verified for zero drift.
- **Local-first & private** — no analytics, no telemetry; nothing about the pages you sample leaves your device.
- Freemium licensing via ExtensionPay (Stripe).

## Free vs Pro

**Free** — the full picker, contrast checker, gradient studio, every colour space, and a monthly allowance of token exports.
**Pro** — unlimited everything.

---

Built by **[Studio Grid](https://studiogrid.io)** · part of a family of tools for designers and developers who live in WordPress, Bricks, and the browser.

<sub>This repository is a public case study. The application source is private.</sub>
