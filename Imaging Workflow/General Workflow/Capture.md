---
tags: [workflow, sop]
---

# Capture

Phase 1 of the [[Imaging Workflow]]. Create the Capture One session, set up its folders and naming, run preflight, and image the material. The session-creation steps here are the **general pattern for every project**; the actual imaging technique is per-material (linked below).

---

## Create the session

1. Create a **session in Capture One**, named for the document/book/project title with **underscores** between words, e.g. `27_Geology_Summer_1978` ([[File & Folder Naming]]).
2. Make sure the session is in **`Pictures/Capture Sessions`** on the [[DT Versa|Versa Mac]].
   ![[capture-session-in-pictures.png]]
3. In **Library → Session Favorites**, click **+** → in the session's **Capture** folder, **Create Folder**:
   - a **`Preflight`** folder
   - a folder named the **same as the session** (this is where the images go)
4. Select both new folders (hold **⌘**) → **Add**.

## Preflight

Run **[[General Preflight]]** now (PPI/focus, mode/profile/curve, LCC, white balance, exposure), using the Base Characteristics settings for your material.

When preflight is done, select the folder **named after the item/volume** → right-click → **Set as Capture Folder**.
![[capture-set-as-capture-folder.png]]

## Naming & counter

- Capture naming: `DestinationFolderName_####` (four-digit counter; three digits on some projects).
- **Reset the Capture Counter** before you start imaging (Preflight tab → Next Capture Naming → ⋯ → **Reset Capture Counter**).

## Image the material

Imaging technique depends on the material — follow your project guide:

- **[[Bound Volumes]]** → [[Capturing a Bound Volume]] (unbind, cover-to-cover, pages pile to the left; spreads are split later in [[Page Splitting]]).
- **[[Large & Flat Art]]** → [[Capture & Subsequent Boxes]] (recto-only matted items; reuse presets across boxes).

✅ When imaging is done → **[[Cropping & Straightening]]** (bound volumes split first in [[Page Splitting]]).

---

## Related
- [[Imaging Workflow]] · [[General Preflight]] · [[File & Folder Naming]] · [[DT Versa]]
