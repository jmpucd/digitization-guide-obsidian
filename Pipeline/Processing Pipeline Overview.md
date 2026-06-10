---
tags: [pipeline]
---

# Processing Pipeline Overview

The full path a project takes **from capture to long-term archive** (and optional sharing). This is the **target workflow** we're building toward — some steps are live today, some are manual, and some are still planned. Each is labeled.

> [!tip] Looking for the step-by-step operator walkthrough?
> This page is the tooling/data-flow view. For "what do I do, on which machine, in what order," see **[[Full Workflow (Start to Finish)]]**.

> [!info] Two tools do the moving
> - **`digi`** (`digitization-tasks-helper`) — moves Capture One **sessions** between the capture station, the Synology queue, and edit workstations, with locking so no two people edit the same session. → [[Session Handoff (digi)]]
> - **`archive-project`** (`archive-tool`) — pushes a **finished project** from a local queue to long-term CentOS archives with MD5 verification, logs it in a Google Sheet, and (planned) shares it on Box. → [[Archiving & Delivery (archive-tool)]]

---

## The stages

| # | Stage | Tool / where | Status |
|---|---|---|---|
| 1 | **Preflight + Capture** | Capture One on the Mac Studio → `~/Pictures/capture_sessions/` | ✅ live |
| 2 | **Park** the finished session to the Synology queue | `digi park` | ✅ built |
| 3 | **Checkout → edit/QA → checkin** (locked, on an edit mini) | `digi checkout` / `digi checkin` | ✅ built |
| 4 | **Export derivatives** (TIFF masters per standard) | Capture One | ⚙️ manual today |
| 5 | **Stage for archive** — move "done" project into an `archive_queue/` | manual move | ⚙️ manual handoff |
| 6 | **Archive** — MD5 manifest → Synology staging → CentOS, verified | `archive-project` | ✅ built (some config to confirm) |
| 7 | **Log** the project in the Google Sheet | `archive-project` | ✅ built |
| 8 | **Share on Box** (tick box in Sheet → poller copies + sets collaborators) | CentOS poller | 🚧 planned |
| 9 | **AV / course-video / DVD** digitization path | MakeMKV + ffmpeg/HandBrake | 🚧 planned/stubbed |

Legend: ✅ built · ⚙️ manual today (automation planned) · 🚧 not yet built

## Flow

```
        ┌─────────────────┐      digi park        ┌──────────────────────┐
        │  Capture station │ ───────────────────▶ │   Synology QUEUE      │
        │  (Mac Studio)    │ ◀─────────────────── │  capture_sessions/    │
        │  Capture One     │      digi checkin     │  (single source of    │
        └─────────────────┘                        │   truth + lock file)  │
                ▲                                   └──────────┬───────────┘
                │ occasional QA                        digi    │  checkout
                │                                       ▲       ▼
        ┌───────┴────────┐   digi checkout    ┌─────────┴────────────────┐
        │  Edit mini 1/2  │ ◀───────────────── │  Edit mini TB SSD         │
        │  crop / QA      │                    │  /Volumes/Edit_SSD/...     │
        └────────────────┘                    └───────────────────────────┘

   when a project is "done":  move into  archive_queue/  (has .archive-source marker)
                                              │
                                  archive-project (MD5 manifest)
                                              ▼
        archive_queue ──rsync──▶ Synology archive-staging ──verify──▶
                          rsync (run from Synology) ──▶ CentOS /archives/<collection>/ ──verify──▶
                          append row to Google Sheet  ──▶ (planned) Box share via CentOS poller
```

## Narrative

1. **Capture** — after [[General Preflight]] and the relevant [[Imaging Workflow|workflow]], images land in Capture One on the capture station.
2. **Park** — when capture is done, `digi park` copies the session to the Synology **queue** and removes the local copy. The queue is the single source of truth.
3. **Edit / QA** — on an edit mini, `digi checkout` writes a **lock** and copies the session to a fast local SSD. Crop and QA in Capture One, then `digi checkin` returns it (with a **stage** + **note**), releases the lock, and records the event in an append-only JSONL log.
4. **Export** — export TIFF masters to the [[Imaging Standards by Material Type|material standard]]. (Manual in Capture One today.)
5. **Stage** — move the finished project into an `archive_queue/` folder (any drive or the Synology), marked with a `.archive-source` file so the archive tool will accept it.
6. **Archive** — `archive-project` computes an **MD5 manifest**, rsyncs to **Synology staging**, **verifies** with `md5sum -c`, then has the Synology rsync onward to **CentOS archives** (avoids the campus firewall) and **verifies again**. The staging copy is kept as a backup.
7. **Log** — a row is appended to the tracking **Google Sheet** (`archived, not shared`) with source/dest paths and the manifest checksum.
8. **Share (planned)** — ticking **Share on Box** in the Sheet triggers a CentOS **poller** (every ~2 min) to `rclone` the project to Box and set collaborators, then write back the Box path and `shared` status. Unticking removes access.
9. **AV path (planned)** — disc rips ([[Optical Media (DVD-Blu-ray) Ripping]]) and course-video feed an ffmpeg/HandBrake compression step; presets exist but the `digi` AV commands aren't wired up yet.

> [!warning] Out of scope (by design)
> Special Collections delivery and long-term ASC specifics, multi-machine source assembly (consolidate before archiving), and any web UI / email/Slack notifications — the Google Sheet is the dashboard.

---

## Related
- [[Session Handoff (digi)]] · [[Archiving & Delivery (archive-tool)]]
- [[General Preflight]] · [[Bound Volumes]] · [[Large & Flat Art]] · [[File & Folder Naming]]
