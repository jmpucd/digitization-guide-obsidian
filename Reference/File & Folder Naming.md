---
tags: [reference, standards]
---

# File & Folder Naming

> When you have an opportunity to establish a naming convention, do it! The goal is to make names that are **unique, identifying, and no longer than they need to be.**

Consistent names are what make the whole [[Processing Pipeline Overview|pipeline]] — capture, handoff, archive — work without confusion.

---

## Rules of thumb

- **No spaces.** A space can be read as a delimiter and breaks scripts. Use underscores `_` between words and hyphens `-` inside identifiers.
- Be unique and identifying; don't pad with redundant words.
- Keep a consistent pattern across a whole project so sorting is predictable.

## Sessions (our day-to-day)

Name a Capture One session for the document/book/project title with **underscores between words**:

```
27_Geology_Summer_1978
```

→ See [[Capture]] for how this is created and structured.

## Project names

`PartnerCode_CollectionCode_KeyTerm`

```
UA_70-202_UnivNegs
UA_11-200-CR_Commencement
GC_ETD
```

## Bound collections

- Non-serials: author + year — `Smith-John-1987_###`
- Serials: broadest descriptor → most specific — `GC_RGE-2007-v04_###`

## Non-bound collections

Identifiers point back to the item's location within the collection:

```
[PartnerCode]_[CollectionCode]-[container#]-[subcontainer#]-[item#]_[image#]
UA_11-200-17-03-01_006
```

## Image / export naming (our workflow)

On export, images follow:

```
ImageFolderName_####    (four-digit counter)
```

Always **Reset Output Counter** before exporting so numbering starts clean and verso handling stays correct → see [[Export]].

## Target images

```
ProjectName_Target_YYYY-MM-DD
```

(Our preflight target captures are named by ppi + date, e.g. `400PPI_8_19` — see [[General Preflight]].)

## Workflow folders

Order processing-stage folders with two-digit prefixes:

```
00.toCapture
01.toPhysicalCheck
02.toQA
03.toCreateAccessFiles
04.toTransfer
```

> This vault uses the same idea — numbered section folders (`10 Reference`, `20 Preflight`, …) keep things ordered.

---

## Related
- [[Capture]] · [[Export]] · [[Processing Pipeline Overview]]

> [!quote] Source
> Adapted from *The Digitization Lab Management Guide* (April Martin, 2025).
