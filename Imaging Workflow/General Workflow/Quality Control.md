---
tags: [workflow, sop, qc]
---

# Quality Control

Phase 4 of the [[Imaging Workflow]]. QC happens in **two rounds**: a first pass **while you crop**, and a final pass in **Photo Mechanic** on the exported TIFFs. Use [[Common Mistakes]] as the "what to look for" checklist.

---

## First round (while cropping)

You're already viewing every image during [[Cropping & Straightening]], so catch problems then:

- **Focus** — keep the **Focus** window (Production tab) open at **100%** and scroll around after cropping.
- **Debris** — hair, dust, etc.
- **Missing / duplicate pages** and ordering.
- Glancing at the whole image on screen also reveals problems.

If you find an issue:
1. Flag the image with a **red color tag** — **Adjustments → Color Tag → Red**, right-click the thumbnail, or press **`-`**.
2. Note it on the **Quality Control Google Sheet**.

## Final round (Photo Mechanic)

Done on the exported TIFFs from [[Export]]. Since first-round QC is done, the focus here is **page order** and **no missing pages** — but still watch for dust/focus.

1. Open **Photo Mechanic**.
2. In the **Navigator**, go to the **Archive Tiff** (or project Tiff) folder on the drive.
3. Double-click the folder to open the **grid**; use the size slider and scan for obvious errors.
4. Double-click the first image for the **single-image** viewer. Wait ~30s for all images to load, then page through.
5. **Issue found:** tag **Red** — `Image → Set Color Class of Photos → Red`, or **⌘1**.
6. Click **`i`** and write a brief note in **Description/Caption**.
7. Continue through all files, only flagging + noting when something's wrong.
8. Close the single-image viewer (red **✕**, top-left).
9. Label the **folder**: no issues → `Color Label → Green`; issues → `Color Label → Red`.
10. Next folder, repeat.

When the project passes, hand it off: [[Processing Pipeline Overview]] → [[Session Handoff (digi)]] → [[Archiving & Delivery (archive-tool)]].

---

## Related
- [[Imaging Workflow]] · [[Cropping & Straightening]] · [[Common Mistakes]] · [[Finder Color Tag Guide]]
