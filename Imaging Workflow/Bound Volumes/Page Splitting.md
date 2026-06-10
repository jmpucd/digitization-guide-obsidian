---
tags: [workflow, bound-volumes, sop]
---

# Page Splitting

A bound-volume step in the [[Capture]] → [[Cropping & Straightening]] transition. After imaging, prep the session: **duplicate variants → split spreads → loose auto-crop** of each side. Uses the **DT CropControl CH** scripts in Capture One.

---

## Split the pages

1. Select **all** images in the folder (**⌘A**) — a white border shows they're all selected.
   ![[split-select-all-1.png]]
   ![[split-select-all-2.png]]
2. **Scripts → DT CropControl CH → Duplication and Splitting → Duplicate Variants**.
   ![[split-duplicate-variants-script.png]]
3. **Scripts → DT CropControl CH → Duplication and Splitting → Split**.
   ![[split-split-script.png]]

## Loose auto-crop — back (verso / left) pages

Goal: a rough base crop to be refined in [[Cropping & Straightening]].

1. Select the first **variant 1** (note the **`1`** in the top-right corner).
   ![[split-select-first-variant.png]]
2. **Select → Select By Same → Variant Position (1)**.
   ![[split-select-by-same-variant-1.png]]
3. **Primary Variant** = the one with the thicker white border. Edits (crop, rotate) apply to it alone without affecting the others in the selection.
   ![[split-primary-variant.png]]
4. **Manually** crop the primary variant loosely — doesn't need to be accurate. Just crop **inside the Versa gutter** and leave space on all sides.
   ![[split-manual-loose-crop.png]]
5. **Sync** the manual crop to all selected images: hold **Shift** and click the **double-arrow** in the Crop tool.
   ![[split-sync-crop.png]]
6. With variant 1 still selected, in the **Auto Crop** tool set: **Method → Loose Material · Straighten → Top Edge · Pre-Pass → None · Padding → -15 px**, then **Auto Crop**.
   ![[split-autocrop-settings.png]]

## Loose auto-crop — front (recto / right) pages

1. Select the first **variant 2** (note the **`2`** top-right).
   ![[split-select-variant-2.png]]
2. **Select → Select By Same → Variant Position (2)**.
   ![[split-select-by-same-variant-2.png]]
3. Repeat the manual-crop → sync → Auto Crop steps above.

## Move to the cropping workstation

The session is now ready for precise [[Cropping & Straightening]] on whichever workstation does that round.

> [!note] Today this move is manual (SSD shuttle + "Move to NAS")
> Our long-term plan replaces this with the `digi` queue so sessions move by command, not by carrying an SSD between rooms. See [[Session Handoff (digi)]].

Current manual procedure (Bodega Bay): quit Capture One, eject the **MBP_Workstation** SSD, carry it to the Versa room, copy `Pictures/Capture Sessions/<session>` onto the SSD, run **Move to NAS**, then bring the SSD to the cropping computer and work directly off it.

---

## Related
- [[Bound Volumes]] → next: [[Cropping & Straightening]]
- [[Session Handoff (digi)]] (the planned replacement for the manual move)
