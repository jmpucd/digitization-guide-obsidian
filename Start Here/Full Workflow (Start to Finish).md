---
tags: [meta, sop, pipeline]
---

# Full Workflow (Start to Finish)

The whole journey of one project — **where to capture, how it moves between computers, and how it ends up archived** — in the order you actually do it. Each step links to its detailed page.

> [!info] Two views of the pipeline
> This page is the **operator's walkthrough** (what you do, on which machine, in what order). For the tooling/data-flow view with the diagram and what's built vs. planned, see [[Processing Pipeline Overview]].

---

## The machines

| Machine | Role | Key location |
|---|---|---|
| **Versa Mac** (Mac Studio, `mac-studio-versa`) | Capture station — the camera + Capture One | `Pictures/Capture Sessions/` |
| **Synology** (NAS) | The **queue** — shared hub; the single source of truth between steps | `…/capture_sessions/` |
| **Edit Mini 1 / 2** | Cropping & QA | TB SSD `/Volumes/Edit_SSD/capture_sessions/` |
| **CentOS** | Long-term archive | `/archives/<collection>/` |

---

## 1. Capture — on the Versa Mac

**Where it lives:** capture into a Capture One **session** under
`Pictures/Capture Sessions/<Session_Name>/`
(e.g. `27_Geology_Summer_1978` — naming rules in [[File & Folder Naming]]). Inside the session you make a **Preflight** folder and a folder named after the volume/item ([[Capture]]).

### 1a. Preflight
Run **[[General Preflight]]** — set PPI/focus, mode/profile/curve, LCC, white balance, exposure. This is the shared baseline for every project.

### 1b. Capture
Follow your material's workflow:
- **[[Bound Volumes]]** → [[Capture]] (unbind, image cover-to-cover, pages pile to the left)
- **[[Large & Flat Art]]** → [[Capture & Subsequent Boxes]] (recto-only, matted items)

Images land in the session's volume/item folder on the Versa Mac.

## 2. Move to a cropping computer

A session must end up on an **Edit Mini's SSD** to be cropped — never edited straight off the Synology.

### The way we're moving to (tooling): `digi`
On the **Versa Mac**, when capture is done:
1. Close the session in Capture One.
2. `digi park` → the session copies to the **Synology queue** and the local copy is removed.

On an **Edit Mini**:
3. `digi checkout` → it copies the session to that Mini's SSD and writes a **lock** so no one else grabs it.
4. Open the session in Capture One **from the SSD path** it reports.

Full steps + safety rules: [[Session Handoff (digi)]].

> [!note] Current manual method (being replaced)
> Today this is sometimes done by hand — quit Capture One, copy the session onto the **MBP_Workstation SSD**, run **Move to NAS**, and carry the SSD to the cropping computer. See [[Page Splitting#Move to the cropping workstation]]. The `digi` flow above replaces the SSD shuttle.

## 3. Page splitting & cropping — on the Edit Mini

1. **[[Page Splitting]]** — duplicate variants, split spreads, loose auto-crop each side (bound volumes).
2. **[[Cropping & Straightening]]** — precise crop (straighten to the **top edge**, crop slightly in) and a **first round of [[Quality Control]]** at the same time.

Track status with the [[Finder Color Tag Guide]] (Yellow → split, Purple → cropped, etc.).

## 4. Export the TIFFs — on the Edit Mini

**[[Export]]** — export **two copies** of TIFF masters (one with the session, one for final QC) to the [[Imaging Standards by Material Type|material standard]] (e.g. 400 ppi, 8-bit, Adobe RGB). Bound volumes first run [[Delete Verso]] to drop blank back pages.

## 5. Final QC

**[[Quality Control]]** in Photo Mechanic on the exported TIFFs — confirm page order, no missing pages, no dust/focus issues. Label the folder **Green** (pass) or **Red** (issues).

### Return the session to the queue
On the Edit Mini: close the session, `digi checkin` → choose stage **done** + a note → the lock releases and the session is back in the queue.

## 6. Archive — `archive-project`

1. Move the finished project into an **archive queue** folder (must contain a `.archive-source` marker).
2. Run `archive-project`: pick the source → pick the **CentOS** collection → it computes an **MD5 manifest**, copies to **Synology staging** (verify), then **Synology → CentOS** (verify again), and logs the project in the tracking **Google Sheet**.
3. *(Planned)* Tick **Share on Box** in the Sheet to share with external collaborators.

Full steps: [[Archiving & Delivery (archive-tool)]].

---

## At a glance

```
Versa Mac  ──capture──▶  Pictures/Capture Sessions/<session>
   │  (preflight → capture)
   │  digi park
   ▼
Synology QUEUE  ──digi checkout──▶  Edit Mini SSD
                                     │  page split → crop → first QC → export TIFFs → final QC
                                     │  digi checkin (stage: done)
                                     ▼
Synology QUEUE  ──▶  archive queue (.archive-source)  ──archive-project──▶
        Synology staging ─verify─▶ CentOS /archives/<collection> ─verify─▶ Google Sheet ─▶ (Box)
```

---

## Related
- [[Processing Pipeline Overview]] (tooling/data-flow view) · [[General Preflight]]
- [[Bound Volumes]] · [[Large & Flat Art]] · [[Session Handoff (digi)]] · [[Archiving & Delivery (archive-tool)]]

← [[Home]]
