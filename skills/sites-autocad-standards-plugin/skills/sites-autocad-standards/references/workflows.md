# Workflows

Stage procedures for the AI-CAD tasks, plus the audit checklist. Use the mode rules in SKILL.md (Draft mode for creating, Audit mode for checking).

## Contents
1. Preflight (every task)
2. Stage 1: understand the standards, convert a design to CAD
3. Stage 2: map a sample package and propose a package structure
4. Stage 3: discipline Xrefs, pen assignment, full sheet set
5. Audit checklist

## 1. Preflight (every task)

1. Check the AutoCAD connection and which drawing is open. If it is not reachable, say so and stop.
2. Confirm the working drawing is a copy in the allowed folder, and that the user has a backup.
3. Confirm units are meters and the company template was used (`PR-PH-T-Settings.dwt`). If the styles are missing, tell the user to start from the template.
4. Confirm the naming scheme to use (`naming.md`, section 5).

## 2. Stage 1: standards and design-to-CAD

Goal: show that the standards are understood, then convert the supplied landscape design into a CAD drawing that follows them.

1. **Standards check.** Summarize, in your own words and with section numbers, the rules that will govern the drawing: units, layers, blocks, text, ByLayer, pen assignment, Xrefs, model/paper space. List open items you need answered.
2. **Read the design.** Identify what it contains (paving, planting, lighting, staking, levels...). Ask for the drawing scale or a reference dimension (a known length, a grid, a scale bar). Without one, say that dimensions will not be reliable.
3. **Fix the origin and orientation.** Ask where 0,0,0 should be and the north direction. Do not guess.
4. **Layer plan.** Propose a table of layers (names per `layers.md`), with a proposed color for each chosen from `pen-table.csv` to give the wanted lineweight and screening, and a linetype. Mark that the manual has no per-layer table, so this is a proposal. Wait for approval.
5. **Build.** Create layers, then draw one layer group at a time in model space at 1=1 in meters. Everything ByLayer. Blocks on layer 0. Annotation text with the manual's styles, scaled by the plot scale. Show the user a checkpoint after each group.
6. **Close out.** Run the cleanup list (`standards-core.md`, section 9), read the layers back from the drawing, and report.

Limits to say out loud: tracing from an image or PDF is approximate, curves and fills may need the user's review, and anything you could not verify is listed as NOT VERIFIABLE.

## 3. Stage 2: package mapping

Input: the sample package sheet (the Drawings List). Output: a proposed package for the drawing from Stage 1.

1. Read the sample (`package-and-folders.md`, sections 3 and 4) and summarize its structure: groups, numbering, scales, title block data.
2. Propose the package for the created drawing, following `package-and-folders.md`, section 5: Xref list, sheet list, folder tree, naming scheme used, assumptions, open items.
3. Present it for approval. Do not create files or folders yet.

## 4. Stage 3: discipline Xrefs, pen assignment, sheet set

The nine sample Xrefs have been read; the results are in `xref-observed-practice.md` and `xref-layer-catalog.csv`. Use them as the source for conventions. If the user supplies other or newer Xrefs, read those first (layers, colors, blocks, text styles) and compare.

1. **Read the Xrefs.** For each, list: layers and their colors, blocks (names, what they are used for, which scale version), text styles, and how labels, level markers and descriptive texts are made.
2. **Learn the conventions.** Start from `xref-observed-practice.md`. Record: layer and block names against the manual, the color chosen per layer against the pen table (what lineweight and screening it gives), and how labels and levels are built and scaled to the plot scale.
3. **Recreate the drawing as Xrefs.** Create model files with the same conventions. File names: ask which pattern applies (the samples use `GH-X-LA-<AREA>-<Content>`, for example `GH-X-LA-PU-Hardscape`; the manual uses `PR-PH-X-DD-Ssss`). Layers named per `layers.md`, with the sample's `LINE`/`HATCH` fourth level only if the user confirms it. Colors: propose from the pen table, using the PU Xrefs as the full-weight reference, and wait for approval. Label, level, callout and staking blocks: build at paper size in meters with attributes in the company text styles, and insert at a scale equal to the plot scale (`xref-observed-practice.md`, section 6). Each Xref attached at 0,0,0; the geometry is in site coordinates unless the user says otherwise.
4. **Create the sheet files.** One per sheet, from the Sheet Creation Template: single layout named like the file, title block lines Xref attached in paper space at 1=1 at 0,0,0, variable text block from the template, the model Xrefs attached with Relative Path on layer 0, viewports at the plot scale, no nested Xrefs.
5. **Sheet Set.** Tell the user which Sheet Set steps to do in AutoCAD (`sheet-set.md`). Do not claim the `.dst` was built unless it was.
6. **Check.** Run the audit checklist on the result and report PASS, FAIL, REVIEW and NOT VERIFIABLE.

## 5. Audit checklist (Audit mode)

Inspect and report. Do not modify.

- Units meters; file name per naming scheme; drawing from the company template; styles and dimension styles present.
- Layer names follow the format and discipline codes; no hard-coded colors or linetypes (ByLayer); layer colors give the intended lineweights.
- Blocks on layer 0, named per protocol.
- Text: UPPER CASE, upright, company styles, style height 0, model height = plotted height x plot scale.
- Dimension style matches the plot scale.
- Xrefs: relative path, layer 0, no nesting, datum 0,0,0, not renamed, none altered.
- Sheet files: single layout named like the file, title block Xref and variable text block, origin 0,0,0, not referenced by other files.
- Model space and paper space content in the right place.
- Cleanup list done (BASE, WIPEOUT frame, UCS, PLAN, IMAGEFRAME; Xref files: paper space empty, Xrefs and images detached); exit view per file type.
- Sheet Set properties and publishing setup (if available to inspect).
- Revision, date format `YYYY.MM.DD`, and checker layer `X-CHKR` where used.

Report using the format in SKILL.md, with the source section for each finding.
