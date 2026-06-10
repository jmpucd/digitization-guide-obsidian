---
tags: [workflow, av]
---

# Optical Media (DVD / Blu-ray) Ripping

Rip video discs to **MKV** files using **MakeMKV**. This is part of our planned AV path (see [[Processing Pipeline Overview]]).

---

## 1. Insert the disc

1. Open the DVD/Blu-ray slot (Eject button) and insert the disc.
2. Launch **MakeMKV**.

## 2. Open the disc

1. MakeMKV should auto-detect the disc.
2. Click the large **Open Disc** icon. This scans the disc and lists its video titles.

## 3. Select the correct title

1. You'll see a list of **titles** with durations.
2. Select the **longest title** (usually the full program).
3. Uncheck the others.

## 4. Choose the save location

On the **right side** of the window:

1. Click the **folder icon** next to **Output Folder**.
2. Navigate to the **SSD** location (a `Rips` folder is usually preselected).

## 5. Start the rip

1. Click **Make MKV** (the large green-arrow icon).
2. The rip begins. **Typical time: 15–30 minutes per disc.**

---

> [!note] Where this fits
> Ripped files feed the AV / course-video portion of the [[Processing Pipeline Overview|pipeline]], which is **planned** (ffmpeg/HandBrake compression presets exist; the `digi` AV commands aren't wired up yet).

## Related
- [[Processing Pipeline Overview]]
