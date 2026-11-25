# Core Standards (SITES AutoCAD Procedures Manual, Ver. 2.0)

Section numbers refer to the manual.

## Contents
1. Project requirements (2.1-2.5)
2. Sheets, title block, details (2.6-2.9)
3. Revisions (2.10)
4. Templates (5.1)
5. Xrefs (5.2)
6. Raster files (5.3)
7. Model space and paper space (5.4)
8. Blocks (6.5)
9. Cleanup and exit (5.5)
10. Checking (10.1)
11. Open items

## 1. Project requirements

- Language: English (U.S.). Date format: `YYYY.MM.DD`, no spaces (2.1, 2.2).
- Approved software: AutoCAD Release 2008 or higher (2.3).
- Units: metric, meters. Dimension tolerance to the nearest millimeter (2.5).
- Model file: a subset of the geometry, drawn life-size (1=1), no scale. Sheet file: one plotted drawing with one or more scaled views of models inside a title block border. A sheet file is "ready to plot" and is never attached as an Xref (2.5).
- Deliverables of an e-submission: DWG files in the folder structure of section 3 (sheets coordinated with the Sheet Set, Xrefs, raster images, Excel files, plot configuration: CTB, plotter config, fonts, templates), plus PDF for every revision, and DWF where required (2.4).

## 2. Sheets, title block, details

- Paper: A0 (841 x 1189 mm) or A1 unless the contract says otherwise. A3 for check plots, A4 for sketches or details (2.6).
- Every drawing has an A0 title block border made of two files (2.7):
  - graphics: `PR-PH-X-00-Title Block A0 Lines`, attached as an Xref in paper space at 1=1, insertion 0,0,0;
  - variable text (attributes and fields): `PR-PH-T-Sheet Creation Template`, inserted as a block in paper space at 1:1, origin 0,0,0. The fields fill from the Sheet Set properties, so variable text must not be typed in by hand (8.2).
- Every sheet file has a single layout. Multiple-layout files are not allowed. The layout is named like the sheet file (2.8).
- Sheet origin: lower-left corner of the title block border at 0,0,0 (2.5).
- Details: drawn at full scale (1=1) in model space. Dimensions and text are drawn in model space and scaled up. Text is drawn at plotted height x plot scale, in meters. Example from the manual: 2.5 mm text at 1:20 is drawn 0.0025 x 20 = 0.05 m. The dimension style scale (dimscale) equals the plot scale. The title block, viewports and detail titles are in paper space (2.9, 5.4).

## 3. Revisions (2.10)

Every drawing carries a revision number, date and description in the title block attributes. A revision triangle with the number goes beside a cloud that marks the changed area. After a formal issue, remove the clouds from earlier revisions and keep the triangles.

| Issue code | Meaning | Revision designator |
|---|---|---|
| IFI | Issued for Information | A, B, C... |
| IFR | Issued for Internal and Client Review | 1A, 2B, 3C... |
| IFA | Issued for Client Approval | OA, OB, OC... |
| IFT | Issued for Tender | T1, T2, T3... |
| IFC | Issued for Construction | 0 (zero) |
| AFC | Approved for Construction / Revision No. | 1, 2, 3... |

A PDF is created for every drawing file at each new revision.

## 4. Templates (5.1)

Stored in `Z:\Sites Project\03-Standards\01-AutoCAD Procedure Manual\02-Templates\` (the drive letter is a recommendation).

| File | Content | Use |
|---|---|---|
| `PR-PH-T-Settings.dwt` | Settings only (styles, dimension styles, layers, linetypes) | Start a new drawing |
| `PR-PH-T-Styles.dwg` | Prototype with graphics and settings, including scale-specific blocks and styles | Open for review |
| `PR-PH-T-Sheet Creation Template.dwt` (the manual shows both .dwt and .dwg) | Layout settings for each sheet, prepared by the prime firm | Insert a new layout (right-click Model tab, From Template) |

The manual says the project fonts, plotter configuration and pen assignment must all be installed for the templates to work properly.

## 5. Xrefs (5.2)

- Store discipline model files in the discipline's `02-Xref` folder. The prime architectural firm moves them to the overall submission `02-Xref` folder. Each discipline notifies the others when it releases or changes an Xref.
- Attach with Relative Path. Never full path.
- Attach every Xref on layer 0.
- No nested Xrefs. Attach each Xref directly to each drawing. For a temporary reference use Overlay, with caution, and detach it before exiting.
- Binding: never bind drawings that stay active. When binding, use the Insert option (layers merge) or Bind (layers stay separate with long names). Purge after binding.
- Datum (insertion point) 0,0,0, which is the lower-left corner of the floor. Never change it after attaching.
- Never rename an Xref file. Follow the naming protocol.
- Never hard-code color or linetype in an Xref. Always ByLayer.
- Only the discipline custodian designer or the CAD Coordinator may change an Xref. Report errors to the responsible discipline.
- The AutoCAD Reference Manager (AdRefMan.exe) is recommended for checking Xref paths (5.6).

## 6. Raster files (5.3)

Same relative-path rules as Xrefs, attached with the IMAGE command. They cannot be bound, so include them when archiving or sending drawings.

## 7. Model space and paper space (5.4)

| Paper space (sheet files only) | Model space (model files) |
|---|---|
| Graphics that are not real-world objects | Graphics for real-world objects, or shared between sheets and disciplines |
| Title block lines and variable text | Walls, doors, windows, equipment, walks, driveways |
| Text (general notes, titles) | Structural grid markers and text, dimensions, room names |
| Graphic scale | Match lines, raster images, symbols and tags (north arrow, key notes) |
| Cross-reference symbols that point to the original detail location | Cross-reference symbols to a detail sheet, schedules |

Rule: anything shared between sheets or disciplines, including annotation, lives in a model file. Models are always referenced by other files. Sheets are never referenced.

## 8. Blocks (6.5, 6.6)

- All entities inside a block are on layer 0. Entities converted from non-AutoCAD systems return to layer 0 when exploded.
- To differentiate inner objects by lineweight or screening, place them on other layers but keep their color ByLayer.
- Block naming: `PR-PH-B-DD-Ssss` (see `naming.md`).
- Standard blocks scaled for 1:2, 1:5, 1:10, 1:20, 1:25, 1:50, 1:100, 1:200, 1:250, 1:400, 1:500 and paper space are in `PR-PH-T-Styles.dwg`. Use the version that matches the plot scale.

## 9. Cleanup and exit (5.5)

| Step | Result |
|---|---|
| BASE | 0,0,0 |
| WIPEOUT | Frame OFF |
| UCS | WORLD |
| PLAN | Plan |
| DDPTYPE | "NONE" and 0 (as printed) |
| IMAGEFRAME | 0 |

Extra steps for Xref (model) files: erase all paper space information (text, viewports, etc.), detach all Xrefs, detach all images, replace or install missing text styles and fonts.

- Purge regularly. A purge removes unused layers and linetypes, so restore them by inserting `PR-PH-T-Settings.dwt` (without graphics) as a block.
- Audit regularly. If Audit cannot fix errors, use Recover.
- Exit view: model (Xref) files zoom to extents before saving. Sheet files stay in paper space and zoom to extents.
- Detach all Overlays before exiting.

## 10. Checking (10.1 to 10.3)

Checkers use colored pencils on plots: red = add, blue = delete, yellow = correct (do not change), green = correction done, black = note. In the drawing file the checker uses a layer named `X-CHKR` for all notes and symbols, and colors objects with True Color so they do not convert to grayscale with the project pen file. HOLD areas are clouded and labelled in upper case. Drawings that need a seal are sealed and signed by the responsible Professional Engineer. Checking and approval stay with people.

## 11. Open items

1. The manual says layer lists are referenced for `X-CHKR` and for per-layer colors, but no layer list is in the pages available. Ask for it.
2. The Sheet Creation Template is shown as both `.dwt` and `.dwg`. Confirm the actual file.
3. The manual predates current AutoCAD releases. Confirm the installed release supports the steps above.
