# Observed Practice in the Grand Heights Sample Xrefs

Source: nine sample Xref files read directly from the DWG data (AutoCAD 2007/2008 format): `GH-X-LA-PU-Hardscape`, `-PU-Planting`, `-PU-Lighting`, `-PU-Staking`, `-LP-Hardscape`, `-LP-Planting`, `-SV-Hardscape`, `-SV-Planting` and `GH-X-LA-GENERAL-MATCH_LINE_1-500`. Per-layer data for all nine is in `xref-layer-catalog.csv` (columns: xref_file, layer, aci_color, linetype, pen_lineweight_mm, pen_screening_pct, layer_lineweight_property, entities).

**Status of this file.** This is what the sample files do, not what the manual says. Where the two differ, the manual stays the standard (SKILL.md section 1). When drafting, follow the manual and use this file to match the company's real habits. When the user asks to copy the samples, say which differences from the manual you are copying. Never present an observed habit as a rule. The Stage 3 conventions marked "confirm" below need Hana's decision before they become rules.

## 1. File names and position

- Xref model files are named `GH-X-LA-<AREA>-<Content>`: area `PU`, `LP` or `SV`, content `Hardscape`, `Planting`, `Lighting` or `Staking` (mixed case, as seen). The match-line file is `GH-X-LA-GENERAL-MATCH_LINE_1-500`. `GH` is the project code and `X` marks an Xref. Areas also appear in the sample sheets (`GH-LA-PU-XX-NN`), so the same `PU` code is used. The meaning of `PU`, `SV` and `LP` is not stated in the files. The block `GH-B-LA-SI-Linear Park Entry Sign` in the LP file suggests `LP` is the Linear Park. Confirm all three.
- The geometry in all nine files lies in the same real-world coordinate range (about X 602,300 to 606,400 and Y 806,900 to 810,800), so the files overlay each other when attached at 0,0,0, which is what the datum rule in 5.2 asks for. The geometry is in site (survey) coordinates, far from the drawing origin. (A few objects with a reversed extrusion direction store a negative X, see section 7.)
- `$INSUNITS` is 0 (unitless) in all nine files. The manual requires meters (2.5). `$MEASUREMENT` is 0 (imperial hatch and linetype files) in seven files and 1 (metric) in `PU-Lighting` and `SV-Hardscape`. Treat both as REVIEW items. `LTSCALE` is 1 in all.
- No file contains an attached Xref (no nesting), which matches 5.2.

## 2. Layers

Observed major groups under `LA`: `HARD` (hardscape), `PLNT` (planting), `GNRL` (general: notes, design text, leaders, cross reference), `GRAD` (spot levels), `STAK` (staking), `DRFT` (match line) and `LI` (lighting). Also `GN-Project-Phase-Limit-Phase 1` (in two files) and `GH-LP-PROPOSED ELECTRICAL` (one file).

Observed minor groups under `HARD`: `PAVE` (paving, most layers), `FURN` (furniture), `WALL` or `WALLS`, `FOUN`, `SIGN`. Under `PLNT`: `TREE`, `SHRUB`, `SUCCULENT`, `GROUNDCOVERS`, `LAWN`, `PALMS`, `GNRL`, `GRAVEL`.

Real names follow a five-level pattern much more often than the manual's four: `LA-HARD-PAVE-LINE-01`, `LA-HARD-PAVE-HATCH-(UI-DB-01-..-RA-..-01)`, `LA-HARD-FURN-(SE-01)`, `LA-PLNT-TREE 5M BOUN`. `LINE` and `HATCH` act as a fourth level, and the item description is the fifth. Hatch layers carry a hyphenated material code in parentheses (for example `(UI-DB-01-..-RA-..-01)`).

Differences from manual 6.4 (counts are layer definitions, excluding `0` and `Defpoints`, out of 231 across the nine files):

| Difference | Count | Examples |
|---|---|---|
| More than four hyphen-separated segments | 116 (96 still exceed four if a parenthesized code counts as one segment) | `LA-HARD-PAVE-LINE-01`, `LA-DRFT-Match Line 1-500 - Lines` |
| Major group is not four characters | 12 | `LA-LI-Bollard-350` (nine `LI` layers), `GN-Project-Phase-Limit-Phase 1` |
| Discipline code not in the manual's list | 1 | `GH-LP-PROPOSED ELECTRICAL` |
| Empty segment | 1 | `LA-HARD--Design Leader` |
| Layer has no objects in model or paper space (some are used only inside block definitions, such as the `TRUNK` layers) | 29 | `LA-LI-Key Line`, `LA-HARD-FURN-Wood-01` |
| Leftover layers with an ` @ 1` / `VP1` / `VP2` / `VPModel` suffix, no objects | 8 | `LA-HARD-PAVE-HATCH-(SS-BG-01-FP-01-04) @ 1 VPModel` (`PU-Hardscape`) |

Spaces appear in many names (for example `LA-PLNT-TREE 3M`), so the manual's examples with spaces ("Type 01") reflect practice. Names that contain a hyphen inside the description (`Match Line 1-500`) split into extra segments.

Confirm: whether `LINE`/`HATCH` as a fourth level and parenthesized material codes are accepted practice (then the four-segment limit needs an exception), and whether `LI` should be `LIGH` or similar.

## 3. Colors and pen results

The colors are assigned per Xref, not from one company table. 35 of the 38 layer names that occur in more than one file have a different color in different files, with the same linetype. Example: `LA-HARD-PAVE-LINE-01` is color 252 in `LP-Hardscape` (0.01 mm at 40%), 140 in `PU-Hardscape` (0.15 mm, 100%), 215 in `SV-Hardscape` (0.05 mm at 50%) and 228 in `SV-Planting` (0.01 mm at 10%).

| Xref family | Pattern seen (pen file results) |
|---|---|
| `PU-*` | The design Xrefs. Lines at 0.10 to 0.30 mm solid (for example `LA-HARD-PAVE-LINE-01` color 140 gives 0.15 mm; `LA-HARD-Design Text` color 3 gives 0.30 mm; tree boundary `LA-PLNT-TREE 5M BOUN` color 113 gives 0.25 mm). Hatches and fills at 0.01 mm with 20 to 90% screening. |
| `LP-*`, `SV-*` | Almost every layer uses 0.01 to 0.05 mm, with screening. `LP-Hardscape` and `SV-Planting` have no layer at 0.10 mm or heavier. These look like light, background-style Xrefs. Whether that is intended is not stated in the files. |
| `GENERAL-MATCH_LINE` | Line layer color 1 (0.10 mm, 100%), linetype `ACAD_ISO05W100`. Text layer color 18. |

Because layer colors differ by Xref, there is no single per-layer color table to copy. For new drafting, use the PU Xrefs as the reference for the full-weight scheme and ask whether the LP and SV scheme (light) applies to the area being drawn. Confirm with Hana.

Other observations:
- More than 99% of objects are ByLayer for color. Hard-coded colors were found in `PU-Hardscape` (367 objects on six layers, for example 214 objects in color 227 on `LA-HARD-Contour Lines`) and in two objects in `PU-Planting`. Hard-coded linetypes: 22 objects `DASHED2` on `LA-HARD-FURN-Mechanical room`, 7 `DASHED` on `LA-HARD-FURN-(ST-01)`, 57 explicit `Continuous` in `LP-Hardscape`. Treat these as FAIL under 6.3.
- Layer 0 has colors other than 7 in four files (5, 108 and 252).
- Layer lineweight property is "default" on 240 of 249 layer entries. A few layers carry explicit values (for example 0.30 mm on `LA-HARD-PAVE-LINE-01` in `LP-Hardscape`, `SV-Hardscape` and `SV-Planting`, and 0.20 mm on `LA-HARD-WALL-(KW-01) Lines`). Printing is meant to follow the pen file, so these explicit values are REVIEW items.
- The three firewall linetypes are not in any of the nine files. Linetypes in use: `Continuous`, `DASHED`, `DASHED2`, `CENTER2`, `PHANTOM2`, `HIDDEN`, `HIDDEN2`, `ACAD_ISO05W100`, `ACAD_ISO07W100`, `ACAD_ISO10W100`, `ACAD_ISO02W100`. Non-standard leftovers: `XR-HARDSCAPE$0$HIDDEN`, `GR-TRB$0$HIDDEN` (bound-Xref remnants) and `KH-Dash-dot-01`.

## 4. Text styles and heights

| Style name in the files | Font | Matches the skill's list? |
|---|---|---|
| `Standard` | `arial.ttf` (`txt` in `SV-Hardscape`) | Manual lists Romans. REVIEW. |
| `TXT- (2)` | `gh-general font.shx` | Name differs (`TXT-2` in the skill). |
| `TXT- (3)` | `gh-general font.shx` | Name differs (`TXT-3`). |
| `TXT- (design)` | `stylu.ttf` (Stylus BT, so ".ttp" in the manual is a TrueType file) | Name differs (`TXT-design`). |
| `TXT- (dim)` | `gh-dimenion font.shx` in `PU-Hardscape` only. `archquik.shx` in five other files. | Font differs in five files. |
| `TXT- (stk)` | `gh-staking font.shx` | Name differs (`TXT-stk`). |

All style heights are 0 (matches 6.1). `TXT- (1)` is not used in any of the nine files. File `GENERAL-MATCH_LINE` has a style `txt` pointing to a path under `05-Configurations\03-Fonts\02-Windows Fonts` (Arial Black), a different folder name from the manual's `05-Fonts`. The actual style names (space after the hyphen, parentheses) are the ones to use when matching these files. Confirm which spelling the template `PR-PH-T-Settings.dwt` uses.

Heights match the manual when read at 1:500: `TXT- (design)` text at 1.5 is 3.0 mm; `TXT- (3)` text at 1.0 is 2.0 mm. `TXT- (dim)` MTEXT at 1.5 is 3.0 mm (manual: 2.0 mm), and `Standard` text at 0.75 is 1.5 mm at 1:500 (manual: 2.5 mm). Treat those two as REVIEW.

Dimension styles present: `DIM (1-500)` and `DIM (1-250)` (match the manual), and `ISO-25` in `PU-Hardscape`, `PU-Lighting` and `SV-Hardscape` (an ISO preset, which the manual prohibits: FAIL or purge). Leaders use `DIM (1-500)` in the PU files and `DIM (1-250)` in `SV-Planting`.

## 5. Blocks

Names follow `GH-B-LA-<code>-<Description>`: `GH-B-LA-FU-Seat-01`, `GH-B-LA-PL-TREE 5M`, `GH-B-LA-SK-StakingPoint`, `GH-B-LA-GR-Level-01`. Codes seen: `FU`, `FO`, `HD`, `SI`, `GN`, `PL`, `GR`, `SK` (and `GH` in one name). The manual form is `PR-PH-B-LA-Ssss`; the samples have no phase segment, so `PR` is `GH` and `PH` is absent. Confirm.

Not following the pattern: `P100`, `P200`, `P300`, `p1200` (very heavily used, about 22,800 inserts in `PU-Hardscape`), `tr70`, `MID LINE`, `GH-WATER FLOW`, `GH-JET02`, `GH-SIGNAGE`, `GH-Lighting Legend` and the `LI-...` blocks in `PU-Lighting`. Several name variants of the same tree block also exist (`TREE 7M-Flowering`, `TREE7M-Flowering`).

Layer 0 rule (6.5): many blocks follow it, but many do not. Blocks with parts on named layers: 24 of 42 named blocks in `PU-Hardscape`, 15 of 18 in `LP-Planting`, 14 of 16 in `PU-Planting`. The planting blocks put the trunk on `LA-PLNT-TREE-TRUNK` or `LA-PLNT-SHRUB-TRUNK`, and the rest on layer 0. This probably gives the trunk its own pen (not stated in the files). Report it as a difference from 6.5 and ask whether it is an accepted exception. Some blocks have all content on layer 0 (the furniture blocks).

## 6. Label, level and callout blocks (attributes) and text scaling

Annotation blocks are defined at paper size in meters, then inserted with a scale factor equal to the plot scale. The attribute text height scales with the block, which gives the right plotted size.

| Block | Attributes (tag: style, defined height) | Inserted at | Resulting height |
|---|---|---|---|
| `GH-B-LA-GR-Level-01` | `LEVEL`, `TYPE`: `TXT- (3)`, 0.002 (default `+00.000`, `F.F.L.`), layer `LA-GNRL-NOTES-Text-03` | 1:500 (from attribute heights) | 1.0 (2.0 mm) |
| `GH-B-LA-GN-Blowup-Callout` | `DETAIL-NUMBER`: `TXT- (2)`, 0.0025; `SHEETNUMBER`: `TXT- (3)`, 0.002 (default `00-00-00-00`) | 1:500 | 1.25 (2.5 mm) and 1.0 (2.0 mm) |
| `GH-B-LA-PL-Planting-Callout` | `AMOUNT`, `PLANTING-ABR.`: `TXT- (design)`, 0.002 (0.0025 in `SV-Planting`), layer `LA-GNRL-Design Text` | `PU-Planting`: scale 500 for 8,406 of 8,501 inserts, 400 for 84, 450 for 11. `SV-Planting`: 250 for all 257. | 1.0 at 1:500 (2.0 mm), 0.625 at 1:250 (2.5 mm); some attribute heights are 0.8 or 0.9999 (rounding) |
| `GH-B-LA-SK-StakingPoint` | `POINT#`: `TXT- (stk)`, 0.002, layer `LA-STAK-Staking PointText` | 1:500 (all 4,283) | 1.0 (2.0 mm) |
| `GH-B-LA-GN-DimTick`, `GH-B-LA-GN-Leader-Arrow` | none | defined, not used in the files | |

How to scale: model height = paper height (m) × plot scale. Insert the block with X, Y scale equal to the plot scale (500 for 1:500, 250 for 1:250). The planting callouts (8,388 of 8,501) and the staking points are inserted at a rotation of about 36.1°, which suggests the plans are drawn in a rotated UCS or view so that the text reads upright on the sheet. This is an inference; ask the user for the plan rotation before placing such blocks. Ask the user for the plan rotation before placing such blocks. `TXT- (design)` callouts use 2.0 mm in the sample, while the manual lists 3.0 mm for that style: REVIEW.

Attribute prompt text contains a spelling error ("Amouunt") in the sample block. Fix it when rebuilding.

## 7. Other findings

- Objects with a reversed extrusion direction (Z = -1) exist, for example 227 of 239 inserts in `SV-Hardscape`, and about 2,300 in `PU-Hardscape` and 2,900 in `PU-Planting`. Their position is correct in the drawing, but the insertion point shows a negative X in the object's own coordinate system. This usually comes from mirroring or from working in a view seen from below. Report as REVIEW.
- Four files contain layout viewport objects (`LP-Planting` 1, `PU-Hardscape` 3, `PU-Planting` 1, `PU-Staking` 2), which points to paper-space layouts. The cleanup list expects paper space in an Xref file to be empty (standards-core.md, section 9). Verify in AutoCAD before reporting.
- `PU-Planting` is very heavy (about 215,000 database entities, of which about 135,000 are polyline vertices, plus 17,000 attributes). That is a performance point to keep in mind when attaching it.

## Open items (ask Hana)

1. Meaning of area codes `PU`, `LP`, `SV`; project code `GH`; whether `GH-B-LA-...` (no phase) is the block pattern to follow.
2. Is the five-level layer pattern (`DD-MAJR-MINR-LINE|HATCH-Description`) and the parenthesized material code accepted? Should `LI` be a four-letter code?
3. Which color scheme applies to new Xrefs: PU (full weight) or LP/SV (light)?
4. Trunk parts on separate layers inside blocks: accepted exception to 6.5?
5. Style names: `TXT- (design)` with spaces and parentheses, or `TXT-design`? Which does the template use?
6. Are `Standard` = `arial.ttf` and `TXT- (dim)` = `archquik.shx` (five files) intended, or substitutions for missing fonts?
7. Is the site-coordinate position (about X 605,000, Y 809,000) required in new Xrefs, or only the 0,0,0 datum?
