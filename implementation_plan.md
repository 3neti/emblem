# IMPLEMENTATION PLAN  
## Left-Chest Icon Emblem — Designer Brief

---

## 1. Objective

Design a minimalist solid-fill icon sequence for placement on the left chest of a white long-sleeve shirt.

The design must be restrained, symbolic, and precise.  
Avoid decorative, cartoonish, or emoji-like appearance.

---

## 2. Icon Sequence (Fixed Order)

🤝 ❤️ ✌️ 🔫 ✈️ ⭐   🌹

- The first six icons form a continuous sequence (5mm gaps).
- The rose is separate and must be visually spaced apart (12mm gap).

---

## 3. Overall Dimensions

- Total width: **107 mm**
- Height: **10 mm**

The original 68mm target was approximate; exact spacing rules yield 107mm total.

---

## 4. Icon Box Specifications

Each icon must fit within:

- **10 mm × 10 mm square**
- Vertically center-aligned within the box

---

## 5. Spacing Rules

- **5 mm spacing** between icons 1–6
- **12 mm spacing** between ⭐ and 🌹

---

## 6. Style Requirements

- **Solid black fill** (#000000) — no strokes, no outlines
- No shading, no gradients
- Single color: Black
- All icons are filled silhouettes sourced from open-source icon libraries

---

## 7. Icon Style & Sources

All icons are solid-fill silhouettes:

**Handshake (🤝)** — Vaadin Icons (Apache 2.0), viewBox 16×16  
**Heart (❤️)** — Amir Baqian (CC Attribution), viewBox 24×24  
**Peace Sign (✌️)** — SVG Repo (CC0), viewBox 732.984×732.984  
**Pistol (🔫)** — SVG Repo (CC0), viewBox 297.363×297.363, flipped horizontally + rotated 20°  
**Airplane (✈️)** — vmware/Clarity (MIT), viewBox 36×36, solid fill  
**Star (⭐)** — joypixels/emojione-monotone (MIT), viewBox 64×64  
**Rose (🌹)** — tablecheck (PD), viewBox -64 0 512 512  

Note: The pistol is an actual firearm silhouette, NOT a finger gun.

---

## 8. Layout (x-offsets of each 10mm icon box)

- Icon 1 (Handshake): x=0
- Icon 2 (Heart): x=15
- Icon 3 (Peace): x=30
- Icon 4 (Pistol): x=45
- Icon 5 (Airplane): x=60
- Icon 6 (Star): x=75
- Icon 7 (Rose): x=97
- Right edge: x=107

Canvas: `width="107mm" height="10mm"`, `viewBox="0 0 107 10"`

---

## 9. Required Deliverables

1. `emblem-master.svg` — Master vector with all icons
2. `emblem-outlined.svg` — Strokes expanded to filled paths (already solid fills; identical to master)
3. `emblem-black.svg` — Clean production SVG, no comments/metadata
4. `emblem-print.pdf` — Print-ready PDF
5. `emblem-dimensions.svg` — Master + guide layer with bounding boxes, spacing labels, dimension lines

---

## 10. Placement Reference

- Intended for **left chest** of a white long-sleeve shirt
- Icon row remains horizontal
- Suitable for screen printing, embroidery, or embossing

---
