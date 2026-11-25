---
name: sites-autocad-standards
description: Apply, draft to, and validate the SITES AutoCAD Procedures Manual (Ver. 2.0), the NAMING.xlsx drawing-numbering workbook, the Grand Heights pen assignment (CTB) and the Grand Heights sample drawing package. Use for any AutoCAD drafting or drawing set-up task for the company (layers, blocks, text, dimensions, Xrefs, sheets, sheet sets), converting a design into CAD drawings, proposing a package, folder or file structure, pen/color/lineweight questions, drawing-number checks, DWG compliance reviews and CAD submission preparation, even if the user does not mention the manual.
---

# SITES AutoCAD Standards

**Version:** 1.1 (draft) | **Date:** 25 November 2026 | **Owner:** Hana El Badawy (AI-CAD Lead)
**Built from:** SITES AutoCAD Procedures Manual Ver. 2.0 (March 2011), `references/NAMING.xlsx`, `GRAND HEIGHTS - PEN.ctb`, the sample sheet GH-LA-PU-00-02 (Drawings List, issued 2013.02.17), and nine sample discipline Xref files (read directly from the DWG data).

## 1. Authority

- The manual is the written standard. NAMING.xlsx, the pen file, the sample package and the sample Xrefs are company practice. The sample Xrefs do not always follow the manual (`references/xref-observed-practice.md` lists where). When they differ, follow the manual and say which habit of the samples you are not copying, unless the user tells you to match the samples.
- Do not invent standards or fill gaps with generic AutoCAD or ISO/ANSI conventions. Never apply the AutoCAD tools' built-in standard presets (layer, text, dimension or ISO/ANSI presets).
- If a rule is not stated, say it is not documented and ask.
- If the sources conflict, report the conflict (see `references/naming.md`, section 5). Follow the source the user names for the current task. If none is named, ask. Never reconcile silently.
- Cite the manual section or the workbook sheet/row when you can.
- The manual dates from AutoCAD 2008. Check that an old command or workflow works in the installed release before relying on it.
- The manual is marked confidential. Do not reproduce long passages. Summarize and cite the section.

## 2. Modes

**Draft mode** (the user asks you to create, convert, set up or edit):
1. Confirm the target drawing and the scope. Work on a copy or on the drawing the user names, and remind them to keep a backup.
2. Propose first when the manual leaves a choice open (for example the layer list and colors). Wait for approval.
3. Preview batch changes, then apply only what was approved.
4. Read the result back from the drawing and report any difference.
5. Never overwrite originals, delete entities, rename files, bind Xrefs, or edit another discipline's Xref unless the user explicitly asks and is authorized (manual 5.2: only the discipline custodian or the CAD Coordinator may alter an Xref).

**Audit mode** (the user asks you to review or check): inspect and report only. Do not modify. See section 6.

If the mode is unclear, ask.

## 3. Rules that apply to every task

- Units are metric, meters. Tolerance to the nearest millimeter (manual 2.5). Language English (U.S.). Dates `YYYY.MM.DD` (2.1, 2.2).
- All objects: color and linetype **ByLayer**. Never hard-code color or linetype (6.3, 7.1, 5.2).
- Layer names: `references/layers.md`. Blocks: all entities on layer 0, color ByLayer (6.5).
- Text: only the manual's styles, UPPER CASE, upright, style height 0 (6.1). `references/styles.md`.
- Model files are drawn full size (1=1). Details are drawn 1:1 in model space, text and dimensions scaled up by the plot scale (2.9, 5.4).
- Sheet files: one layout per file, layout named like the sheet file, plotted 1=1, origin at the lower-left corner of the title block border at 0,0,0. Sheet files are never attached as Xrefs (2.5, 2.8).
- Xrefs: Relative Path, attach on layer 0, no nesting, datum 0,0,0, never rename (5.2).
- File names are in capitals with no spaces (4.1).
- Color decides plotted lineweight and screening through the project pen file. `references/pen-assignment.md`. A new layer defaults to color 7, which plots at 0.70 mm in this pen file, so assign colors deliberately.

## 4. Which file to read

| Task | Read |
|---|---|
| Project requirements, Xrefs, blocks, model/paper space, cleanup, revisions, title block | `references/standards-core.md` |
| Any file, sheet, block or drawing number | `references/naming.md` |
| Layers | `references/layers.md` |
| Text, dimensions, fonts | `references/styles.md` |
| Colors, lineweights, screening, plotting | `references/pen-assignment.md` and `references/pen-table.csv` |
| Package, Xref and folder structure; sample package | `references/package-and-folders.md` |
| Sheet Set (.dst) and publishing | `references/sheet-set.md` |
| What the sample discipline Xrefs actually contain (layer and block names, colors, text styles, label/level/callout blocks and their scaling), and where they differ from the manual | `references/xref-observed-practice.md` and `references/xref-layer-catalog.csv` |
| Stage-by-stage procedures (design to CAD, package mapping, Xref and sheet set build), audit checklist | `references/workflows.md` |

## 5. Tool limits (be honest)

- Do not report a check as done if you did not inspect it. Do not claim a sheet set was built if only the sheet DWG files were created.
- The Sheet Set Manager file (.dst) and its properties may not be controllable with the available tools. Say which steps the user must do in AutoCAD.
- Converting a raster or PDF design to CAD is approximate. It needs a known scale or a reference dimension. Work layer by layer and check with the user.
- Fonts, the pen file (.ctb) and the templates must be installed on the computer. If text or lineweights look wrong, check that first.
- You cannot see the user's desktop. Ask them to upload files to the chat.

## 6. Reporting format (audit and review)

Statuses: **PASS** (confirmed compliant), **FAIL** (confirmed violation), **REVIEW** (possible issue or ambiguous source), **NOT VERIFIABLE** (information not available).
Include: drawing name, scope, checks performed, passed, failed, review items, not verifiable, findings with source references, recommended corrections. Do not mark PASS for anything you did not inspect.

## 7. Open items

Each reference file ends with open items. Ask the user about them instead of guessing. The main ones: which naming scheme applies (manual, workbook or sample package), the per-layer color assignment (the sample Xrefs use different colors for the same layer name, see `xref-observed-practice.md` section 3), whether the five-level layer names of the samples are accepted, the meaning of the area codes `PU`, `LP`, `SV`, and whether the Sheet Set (.dst) can be handled with the available tools.
