---
tags: [reference]
---

# Color Management & Calibration

Accurate color depends on three things being under control: the **room**, the **monitor**, and the **camera**. Get these right and you need far less digital correction later.

---

## The Room

A spectrally neutral environment prevents "color contamination" — light bouncing off colored surfaces onto your originals.

- Aim for **dark, matte, neutral** surroundings. Light surfaces bounce more light than dark matte ones.
- A black ceiling (or working in a tent) reduces reflections on glass platens and reflective materials.
- Neutral gray walls reduce light bouncing and create a more controlled environment.
- Set your desktop background to a neutral gray (~L\*50, a\*0, b\*0) so it doesn't shift your color perception.

## The Monitor

> You must calibrate your monitors.

- Target brightness ~**120 cd/m²**.
- Keep ambient light low and neutral.
- **Turn off HDR** — it manipulates contrast and misrepresents the image.
- Recalibrate periodically (FADGI suggests weekly; once a semester is a practical minimum).
- Monitor hoods help isolate ambient and monitor light from the capture station.
- Calibration hardware: X-Rite i1. Quality display brands: NEC, Eizo.

> [!note] 📷 Placeholder — photo: monitor calibration device on screen + hood
> Replace with a lab photo.

## The Camera — Color Profiling

> Color is a human sensation… the sensor in a camera does not respond to light identically to the eye. Therefore we profile the response of the camera sensor so it can emulate an eye. — *Doug Peterson, DT R&D*

Profiling is a **three-step** process:

1. **Profile** — calibrate the device with a profiling target + software.
2. **Verify** — check the profiling target's color for user/software error.
3. **Validate** — assess a *different* (independent) target to judge profile quality.

> [!tip] Our shortcut
> Our DT Phase One + Capture One CH setup ships with **pre-built Cultural Heritage ICC profiles**, so we get consistent, high-quality color **without** profiling software or a profiling target. We still capture a color target each session for white balance and exposure — see [[White Balance]] and [[Exposure]]. Refresh LCCs at least 3×/year, or any time the station is reconfigured (see [[LCC (Lens Cast Calibration)]]).

## Color Targets

We use targets to compare a captured image against known reference values.

- **GoldenThread** FADGI 19264 target (device-level)
- ISA Device-Level target
- X-Rite ColorChecker
- IT8 target (flatbed scanner calibration)
- Film-specific targets

Each target type has specific patches for white balance and exposure — those exact patch numbers and L\* values live in [[White Balance]] and [[Exposure]].

## FADGI

In cultural-heritage digitization, the [FADGI guidelines](https://www.digitizationguidelines.gov/guidelines/digitize-technical.html) inform imaging best practices. They are **guidance, not law** — use them to set lab standards within what's practical for your equipment and goals. FADGI grades conformance with a star system based on ISO 19264. Our material-type targets in [[Imaging Standards by Material Type]] are set with FADGI in mind.

---

## Related
- [[Image Types & File Formats]] · [[Imaging Standards by Material Type]]
- [[General Preflight]] · [[LCC (Lens Cast Calibration)]] · [[White Balance]] · [[Exposure]]

> [!quote] Source
> Adapted from *The Digitization Lab Management Guide* (April Martin, 2025) and *DT Digitization Guide — Preflight* (2025).
