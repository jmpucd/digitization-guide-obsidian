---
tags: [workflow, sop]
---

# Export

Phase 3 of the [[Imaging Workflow]]. Export **TIFF masters** from Capture One. We keep **two copies**: one stays with the session, one goes to the final [[Quality Control]] / archive drive.

> [!info] Match the material standard
> Format is always **TIFF, uncompressed, Adobe RGB (1998)**. Resolution and bit depth come from [[Imaging Standards by Material Type]] (e.g. bound/documents 400 ppi 8-bit; photos/postcards 600 ppi 16-bit).

---

## Two recipes

Make two export recipes that are **identical except for the Export Location**.

**Recipe 1 — stays with the session**
- Export Location: **Session Default (Output)**; Subfolder token: **Image Folder Name**.
  ![[export-recipe-session.png]]

**Recipe 2 — final QC / archive copy**
- Export Location: choose the external/archive drive (e.g. the project's **Tiff** or **Archive Tiff** folder); Subfolder token: **Image Folder Name**.
  ![[export-recipe-archive.png]]

**Shared settings (both recipes):**

| Setting | Value |
|---|---|
| Export Naming → Format | Image Name |
| Format | TIFF (bit depth per material standard) |
| Options | Uncompressed |
| Resolution | per material standard (e.g. 400 ppi) |
| Scale | Fixed 100% |
| Open With | None |
| Crop | Respect Crop |
| Output Sharpening | None |
| Color profile | Adobe RGB (1998) |

Leave **Export Watermark** and **Export Metadata** untouched.
![[export-recipe-settings.png]]

## Naming & counter

Export naming format: `ImageFolderName_####` (four-digit counter). **Before exporting, tap the ⋯ → "Reset Output Counter."** This keeps numbering clean and correctly handles any kept pages (e.g. verso pages with text in [[Delete Verso]]).
![[export-naming-reset-counter.png]]
![[export-naming-format.png]]

## Export & verify

1. Check the **checkmark** next to **both** recipes.
2. Click **Export**.
3. Confirm **two copies** exist — one in the session **Output** folder, one on the archive/QC drive.
4. Tag the session **Green** and move it toward completion ([[Finder Color Tag Guide]]).

✅ Then → final **[[Quality Control]]**.

---

## Related
- [[Imaging Workflow]] · [[Imaging Standards by Material Type]] · [[File & Folder Naming]] · [[Quality Control]] · [[Finder Color Tag Guide]]
- Bound-volume extra step before export: [[Delete Verso]]
