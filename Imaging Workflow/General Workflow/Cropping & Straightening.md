---
tags: [workflow, sop]
---

# Cropping & Straightening

Phase 2 of the [[Imaging Workflow]]. Crop each image to the right border and straighten it. Do a **first round of [[Quality Control]]** at the same time — you're already looking at every image.

> [!info] For two-page spreads
> Bound-volume spreads are **split into single pages first** — see [[Page Splitting]] — then cropped with the steps below.

---

## Tools for cropping

- **Manual Crop tool** — toolbar above the image, or Production tab → Crop, or press **`C`**. Drag the edges in/out; grab a corner to **rotate** the crop frame. Best for one-offs, slow in bulk.
- **CropControl scripts** — **Scripts → DT CropControl CH** tweak crops quickly without dragging sliders. The **Stream Deck** is usually faster than the menus.
  ![[crop-cropcontrol-scripts.png]]
- **Auto Crop** — for batches, set Method/Straighten/Padding and let it crop a whole selection (used in [[Page Splitting]] for the loose first pass).

## Syncing a crop across many images

Crop the **Primary Variant** (the one with the thicker white border — it edits alone within a selection), then **sync** it to the rest: hold **Shift** and click the **double-arrow** in the Crop tool.
![[split-sync-crop.png]]

## Straightening & border guidelines

Border and straightening targets vary by material — check [[Imaging Standards by Material Type]] (e.g. documents 1/8", oversized 1/4"). General rules:

- **Straighten to a consistent edge.** For **bound volumes**, use the **top edge** of each page as the guide — make the top straight even if other edges end up slightly crooked or the text looks askew.
- **Crop tight, but not too tight.** Crop the least possible into the item, while making sure **no edges of pages/items underneath are visible**.
- Leave the small border the material standard calls for. Respect the original orientation (rotate printed text so it's readable for OCR; match handwritten pages to the book).

See [[Common Mistakes]] for cropping pitfalls (cutting off gutter text, page slope).

## First-round QC while you crop

You're looking at every image anyway, so catch problems now — focus, debris, missing/duplicate pages. The full checklist and how to flag issues is on **[[Quality Control#First round (while cropping)]]**.

✅ When cropping is done → **[[Export]]**.

---

## Related
- [[Imaging Workflow]] · [[Page Splitting]] · [[Export]] · [[Quality Control]] · [[Common Mistakes]] · [[Finder Color Tag Guide]]
