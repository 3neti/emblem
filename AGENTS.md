# AGENTS.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Project Overview

This is a **graphic design asset project**, not a traditional software codebase. The goal is to produce a minimalist monoline icon sequence for screen-printing on the left chest of a shirt.

The authoritative design brief is `implementation_plan.md`. All design decisions must conform to it.

## Icon Sequence (fixed order, do not change)

1. Handshake
2. Heart
3. Peace sign (two-finger V hand gesture)
4. Pistol (actual firearm silhouette, NOT a finger gun)
5. Airplane
6. Star (5-point)
7. Rose (separate, visually spaced from icons 1–6)

## Key Design Constraints

- **Monoline style**: uniform stroke, no fills, no shading, no gradients
- **Stroke**: 0.8mm black (#000000), round caps, round joins. Rose may use 0.7mm.
- **Icon boxes**: each icon fits within a 10×10mm square, drawn height 8–9mm, vertically centered
- **Spacing**: 5mm between icons 1–6; 8mm between star and rose
- **Total width**: ~103mm (the 68mm in the brief is approximate; exact spacing rules take priority)

## SVG Architecture

`emblem-master.svg` is the primary working file.

- **Canvas**: `width="103mm" height="10mm"`, `viewBox="0 0 103 10"` (1 viewBox unit = 1mm)
- **Global stroke group**: a single parent `<g>` element sets stroke properties for all children
- **Icon groups**: each icon is a `<g id="icon-{name}">` positioned at its box x-offset:
  - Handshake: x=0, Heart: x=15, Peace: x=30, Pistol: x=45, Airplane: x=60, Star: x=75, Rose: x=93
- **Paths**: all icon geometry is SVG `<path d="..."/>` elements using absolute coordinates in the global viewBox (not local transforms)

When editing icon paths, keep coordinates within each icon's 10mm box (e.g., pistol paths should have x values between 45–55).

## Icon Sourcing Approach

Hand-crafting complex Bézier paths (handshake, rose, peace hand) produces poor results. The preferred approach is:

1. Source paths from **open-source monoline icon libraries** (Lucide ISC license, Tabler Icons MIT license)
2. Extract `<path d="...">` data from the library's 24×24 viewBox SVGs
3. Scale and translate paths to fit our 10mm boxes at the correct x-offsets
4. Adjust stroke-width to match (library stroke-width="2" on 24-unit canvas → our 0.8 on 10-unit canvas)

Icons not found in standard libraries (pistol, rose) may need to be sourced from other open-source sets or carefully hand-drawn.

## Required Deliverables

All listed in `implementation_plan.md` §9:

1. `emblem-master.svg` — master vector with all icons
2. `emblem-outlined.svg` — strokes expanded/converted to filled paths
3. `emblem-black.svg` — clean production SVG, no comments/metadata/guides
4. `emblem-print.pdf` — print-ready PDF (convert via cairosvg or Node.js tooling)
5. `emblem-dimensions.svg` — master + guide layer showing bounding boxes, spacing labels, dimension lines

## Environment Notes

- **PDF conversion**: `cairo` is installed via Homebrew; Python `cairosvg` is installed but requires the Homebrew cairo dylib to be findable. May need: `export DYLD_LIBRARY_PATH=$(brew --prefix cairo)/lib`
- **Preview**: `open emblem-master.svg` opens in the default browser on macOS
- **No build system**: files are hand-edited SVG/XML. No npm, no bundler.
