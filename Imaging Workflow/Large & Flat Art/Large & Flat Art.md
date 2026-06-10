---
tags: [workflow, flat-art]
---

# Large & Flat Art

Workflow for **matted prints, artwork, and oversized flat items** captured recto-only. The big difference from [[Bound Volumes]] is volume: many items across many boxes, so we **save and reuse presets** instead of running a full preflight every session.

> [!example] Worked example: the **Shrem** project
> Specifics (preset names, box structure) come from the Shrem Museum printed-materials project. Substitute your own session/preset names.

> [!info] Standard for this material
> Oversized: 300–400 ppi (400 preferred) · 24-bit · Adobe RGB (1998) · TIFF. Photographs: 600 ppi · 48-bit. See [[Imaging Standards by Material Type#Oversized Items]] and [[Imaging Standards by Material Type#Photographs]].

---

## Steps in order

1. **[[General Preflight]]** → the start-of-day preflight below (preset reuse).
2. **[[Capture]]** → technique: **[[Capture & Subsequent Boxes]]** (recto-only matted items).
3. **[[Cropping & Straightening]]** — crop/straighten + first-round QC.
4. **[[Export]]** — TIFF masters, two-recipe pattern (no verso to delete).
5. **[[Quality Control]]** — final QC in Photo Mechanic.
6. Hand off via the [[Processing Pipeline Overview|pipeline]].

## Why it's different from bound volumes

- One **Capture Session per box**, often **several boxes per day** → reuse presets so you don't redo preflight each time.
- Items are **matted and mylar-protected**; image the **front (recto) only** — do **not** fold items over.
- Mat depth changes the focus plane, so **refocus on the print** (without changing the entered PPI) when depth changes.

## Start-of-day preflight (first box)

Run a **[[General Preflight]]**, with these Shrem-specific choices:

1. **Wash and fully dry hands** ([[Handling Archival Materials]]).
2. Find the **box number**; open the matching session in `Pictures/Capture Sessions/Shrem_Batch_1/Imaging_Queue`.
3. Set the **Preflight** folder as Capture Folder; **Reset Capture Counter**.
4. Camera starting point: **ISO 50 · 1/3 s shutter · f/8**.
5. **Next Capture Naming:** `DestinationFolderName_###` (three-digit counter).
6. Place the **Golden Thread** target; open Live View.
7. Base Characteristics: **Mode** Photography · **ICC** `Flat Art Reproduction – LED DT Photon` · **Curve** Linear Scientific (for measuring).
   ![[flatart-base-characteristics.png]]
8. Set **400 ppi** and verify with the Capture Resolution Ruler ([[PPI & Focus]]).
9. **Reuse presets** (the **⋯ / three-lines** menu in each tool):
   - **LCC** → preset `No_Glass_400_SHREM`
   - **White Balance** → preset `No_Glass_400PPI`
10. **Exposure:** place **Add Color Readout** on three white values; make sure no top **L** reading exceeds the target's printed values. If over, **speed up the shutter**, re-capture, re-measure. **Do not touch the Exposure slider** for this project. ([[Exposure]])
11. Once exposure is right, set the **ICC profile** in Base Characteristics to `NoGlass_400ppi_SHREM_111225`.
12. Capture the **larger target** (in the big plastic box).
13. In the **Production** tab, set **ICC Profile → Copy From Last** (not Defaults).
    ![[flatart-copy-from-last.png]]

→ Then start imaging: **[[Capture & Subsequent Boxes]]**.

## Export

Export TIFFs to the material standard above (TIFF, Adobe RGB (1998); bit depth/ppi per item type). The two-recipe pattern from [[Export]] (one copy with the session, one for QC/archive) applies here too — there's just no verso to delete.

Then hand off via the [[Processing Pipeline Overview|pipeline]].

---

## Related
- [[Capture & Subsequent Boxes]] · [[General Preflight]]
- [[Imaging Standards by Material Type]] · [[Handling Archival Materials]] · [[Finder Color Tag Guide]]
- Other workflow: [[Bound Volumes]]
