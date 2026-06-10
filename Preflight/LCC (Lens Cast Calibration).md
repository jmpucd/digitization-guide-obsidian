---
tags: [preflight, sop]
---

# LCC (Lens Cast Calibration)

Part of [[General Preflight]] (step 5). The LCC corrects **lens cast** and creates **even luminance** across the frame. Do it **after** you've set your final height and focus ([[PPI & Focus]]).

---

## Capture the LCC reference

1. Place a plain **white foamcore board** on the imaging surface — flat, flush, covering the **entire** field of view. Nothing else should be visible in frame.
2. Capture it using the **same aperture and lighting** you'll use for the object. The image should look **uniformly gray**, around **L\* 60–70** (our lab notes target ~50–60; aim for an even mid-gray). Adjust **shutter speed** to land in range.

> [!note] 📷 Placeholder — the LCC capture: an even gray frame edge-to-edge
> Replace with a current lab capture. (Migrated reference shot of the create-LCC step is below.)

## Create the LCC profile

1. Rename the capture something intuitive first, e.g. **`400PPI_8_19`** or `72mm f8 400ppi distance` — this becomes the LCC's name.
2. With the gray capture selected, in the **LCC** tool press **Create LCC** (or right-click the image → **Create LCC…**).
   ![[preflight-create-lcc.png]]
3. In the dialog, **do not check** any options (no Dust Removal, no Wide Angle Lens Correction). Press **Create**.
4. Confirm success: an **LCC** badge appears above the thumbnail, and in the LCC tool **Color Cast** and **Enable Uniform Light** are checked.

## Applying the LCC

- **Automatic:** Capture One's **Next Capture Adjustments** is set to **Other → Copy from Last** by default, so the LCC (and other settings) carry forward to each new capture automatically. (Be careful — if you reset/change a setting and capture, that change also carries forward.)
- **Manual:** select the LCC reference image *together with* the images to fix, then in the LCC tool click **Copy and Apply** (the arrow), leave the box as-is, and **Apply**.

> [!warning] Make a new LCC if any of these change
> - Aperture
> - Light position or angle
> - Camera position
> - Lens or camera
>
> An LCC is only valid for images shot on the same back/camera under identical lighting.

---

## Related
- [[General Preflight]] → next: [[White Balance]]
- [[Color Management & Calibration]]

> [!quote] Source
> *DT Digitization Guide — Preflight §7.5–7.6* + lab notes.
