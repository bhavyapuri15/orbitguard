---
version: alpha
colors:
  primary: "#4d9ef6"
  background: "#070e1c"
  surface: "#0d1830"
  text: "#e4ebf8"
  danger: "#ef6b5b"
typography:
  sans:
    fontFamily: "IBM Plex Sans, system-ui, sans-serif"
  mono:
    fontFamily: "IBM Plex Mono, ui-monospace, monospace"
rounded:
  panel: "12px"
  control: "8px"
omitted:
  - section: spacing
    reason: "Runtime CSS owns the established spacing system."
  - section: components
    reason: "Shared React primitives and CSS remain canonical."
---

# OrbitGuard console

## Overview
An orbital risk instrument for operators and datathon judges. The signature is IBM Plex typography, restrained blue actions, and explicit uncertainty beside every claim. Preserve the original console: Encounters opens by default, followed by Manoeuvre planning and Validation. Additional explanatory content belongs in an optional final How it works tab. Avoid decorative telemetry, invented metrics, or an implied live spacecraft connection.

## Colors
`frontend/src/style.css` is the canonical runtime token source. The console uses one deep-space dark theme derived from the Stitch project "OrbitGuard console" (design system "OrbitGuard Deep Space"). Blue identifies actions and the controlled satellite, amber the primary object, teal another object, violet the learned model. Status includes text and an icon; color alone never communicates acceptance.

## Typography
IBM Plex Sans carries headings, controls and explanatory prose. IBM Plex Mono is reserved for fingerprints and runtime details. Tables use tabular numerals. Explain Pc, CDM, TCA and metric definitions through shared keyboard-accessible terms.

## Layout
The natural-height page has a 1280px maximum width with 24px side padding. Optional How it works content separates historical forecasting from synthetic planning in two tracks. Its evidence uses a three-column comparison that stacks on narrow screens. Preserve existing page layouts. Tables own horizontal overflow; they do not constrain the page height.

## Imagery
Each tab opens with a photographic hero (`Hero` in `ui.tsx`) using public-domain NASA photographs bundled in `frontend/src/assets/imagery/`, credited in the page footer. Globes use NASA's Blue Marble texture. Hero statistics come from `/api/evidence` and show a dash when unavailable.

## Elevation & Depth
Bordered translucent panels over a static starfield; soft shadows on panels and tooltips. Never apply `backdrop-filter` or a persistent `transform` to an element that contains a `Tip`, because both re-anchor its fixed-position tooltip. The header remains visible during document scrolling.

## Shapes
Panels use 12px radii, controls 8px. Card titles pair a heading with a Lucide icon in a neutral tile (`CardTitle`, `IconTile`). Keep colour minimal: one blue accent for actions and satellite A, green/red only for status, and amber/teal only to tell objects apart in charts and orbit views. Preserve existing density and avoid ornamental geometry.

## Components
`ui.tsx` owns loading, empty, notice, status, tooltip and async request behavior. `App.tsx` owns navigation and evidence download. Lucide supplies functional icons. Charts read runtime CSS tokens.

## Do's and Don'ts
Show artifact-derived numbers and unavailable states. Distinguish ranking from threshold detection, training validation from held-out results, current server from benchmark environment, and geometry from probability. Motion is purposeful: staggered entrance, count-up of measured values, risk-line drawing, scanning bar while screening, staggered cells in the 37-candidate strip, flowing connectors in How it works, slow hero drift. Entrance animations use `backwards` fill so no transform persists. Every animation is disabled under `prefers-reduced-motion`.
