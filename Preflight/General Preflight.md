---
tags: [preflight, sop]
---

# General Preflight

**Preflight** is everything you do *before* imaging to set up the camera and space for consistent, accurate capture. This page is the **shared baseline for every project.** Each [[Imaging Workflow|workflow]] links here and then adds only its own differences.

> [!tip] Do this in order
> The Capture One **Preflight & Production** tab is laid out top-to-bottom in roughly this order. Work down it. Each step below links to a detailed page.

---

## 1. Room & hardware setup

1. Plug in / power on the **camera**, turn on the **imaging lights**, turn **off the room lights** (keeps stray light out of frame).
   - Phase One camera: the plug is by the power strip to the right of the Versa. The power-box light turns **green** when the camera is ready.
   ![[preflight-phase-one-power-box.jpeg]]
2. Foot **pedals** under the Versa raise/lower the platen and trigger capture. The light-control box switches the two lights.
   ![[preflight-versa-pedals-light-control.jpeg]]
3. Place your **color target** under the glass, centered on the platen, holding it by the edges (no fingerprints). Raise the platen to the glass with the pedal. (We usually use the larger target.)
   ![[preflight-target-on-platen.png]]

→ The station: [[DT Versa]] (or [[DT V-Cradle]] for intact volumes) · environment: [[Color Management & Calibration#The Room]] · handling: [[Handling Archival Materials]]

## 2. Open the session & set the Preflight folder

1. Open Capture One. Create or open the session per [[Capture]] (naming, folders).
2. In **Library → Session Favorites**, select the **Preflight** folder, right-click → **Set as Capture Folder** (so preflight shots land there).
   ![[preflight-set-capture-folder.png]]

## 3. Set PPI & focus → [[PPI & Focus]]

Set the target resolution (usually **400 ppi**; 600 for photos/postcards) and let the camera focus and position itself. Verify with the Capture Resolution Ruler.

## 4. Set Mode, Profile & Curve → [[Mode, Profile & Curve]]

In **Base Characteristics**: Mode **Photography**, the **Cultural Heritage** ICC profile for your light source (LED DT Photon), and the appropriate **Curve**. (Use **Linear Scientific** while *measuring* exposure, then switch to **Linear Response** for flat-art capture.)

## 5. Create the LCC → [[LCC (Lens Cast Calibration)]]

Capture a white board filling the frame, confirm it reads ~L\* 50–70, name it (e.g. `400PPI_8_19`), and **Create LCC** for even lighting and lens-cast correction.

## 6. Set White Balance → [[White Balance]]

With the target back under the glass, use the white-balance dropper on the correct neutral patch for your target.

## 7. Set Exposure → [[Exposure]]

Use color readouts on the mid-tone patches and adjust shutter speed (and, sparingly, the Exposure slider) so no readout exceeds the target's printed values.

## 8. Finalize

1. Switch the **Curve** to **Linear Response** (if you measured under Linear Scientific).
   ![[preflight-curve-linear-response.png]]
2. In **Library → Session Favorites**, set your **capture folder** (the volume/item folder, not Preflight).
   ![[preflight-set-capture-folder-library.png]]
3. In the Preflight tab, **Next Capture Naming → ⋯ → Reset Capture Counter**.
   ![[preflight-reset-capture-counter.png]]

✅ **Preflight is complete.** Go to your workflow's capture step.

---

> [!warning] Redo preflight (or at least the LCC) if anything changes
> A new LCC and re-check are required if you change the **aperture, light position/angle, camera position, lens, or camera**, or reconfigure the station. For projects spanning many sessions/boxes, see the shortcut in [[Large & Flat Art]].

## Related
- Steps: [[PPI & Focus]] · [[Mode, Profile & Curve]] · [[LCC (Lens Cast Calibration)]] · [[White Balance]] · [[Exposure]]
- Reference: [[Imaging Standards by Material Type]] · [[Color Management & Calibration]] · [[Equipment & Lighting]]
- Workflows: [[Bound Volumes]] · [[Large & Flat Art]]

> [!quote] Sources
> Combines our lab's preflight notes with *DT Digitization Guide — Preflight, Ch. 7* (2025) and *The Digitization Lab Management Guide* (April Martin, 2025).
