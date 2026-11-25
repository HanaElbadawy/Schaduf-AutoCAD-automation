# Text Styles, Dimension Styles, Linetypes and Colors

Source: manual 6.1, 6.2, 6.3, 2.9, 5.4.

## Text styles and fonts (6.1)

Only these styles and standard AutoCAD fonts are used, except in authorized cases (for example the company title or Arabic text). Font definitions are not stored in the drawing, so the fonts must be installed on the computer. The styles come from `PR-PH-T-Settings.dwt`, or by inserting that template into the drawing. Scale-specific styles are in `PR-PH-T-Styles.dwg`. If a drawing lacks the styles, tell the user to start from the template or insert it. Do not rebuild styles by hand.

Rules: all English text in UPPER CASE; text upright with no angle; styles and fonts are different things; style height is always 0.

| Style | Font | Type | Style height | Plotted height | Width factor | Use |
|---|---|---|---|---|---|---|
| STANDARD | Romans | .ttp (as printed) | 0 | 2.5 mm | .8 | General notes, annotation, dimensions |
| TXT-1 | SITES-GENERAL FONT | .shx | 0 | 4.0 mm | .7 | Text in plans and elevations |
| TXT-2 | SITES-GENERAL FONT | .shx | 0 | 2.5 mm | .75 | Minor titles |
| TXT-3 | SITES-GENERAL FONT | .shx | 0 | 2.0 mm | .8 | Major titles |
| TXT-design | Stylus BT | .ttp (as printed) | 0 | 3.0 mm | .7 | Sketchy text in details and plans |
| TXT-dim | SITES-DIMENION FONT (as printed) | .shx | 0 | 2.0 mm | .7 | Text in dimensions |
| TXT-stk | SITES-STAKING FONT | .shx | 0 | 2.0 mm | .8 | Coordinate point numbers |

## Text height in model space

Drawing units are meters. Actual height (m) = plotted height (m) x plot scale. Examples: 2.5 mm at 1:20 is 0.0025 x 20 = 0.05 m (manual). TXT-1 (4.0 mm) at 1:500 is 0.004 x 500 = 2.0 m. For dimensions, the dimscale equals the plot scale.

## Fonts to install (6.1)

Folders under `Z:\Sites Project\03-Standards\01-AutoCAD Procedure Manual\05-Fonts\`: `01-AutoCAD Fonts` (.shx, copy into the AutoCAD Fonts folder) and `02-Windows Fonts` (TrueType, copy into `C:\WINDOWS\Fonts\`). Start AutoCAD afterwards.

## Dimension styles (6.2)

The company dimension style is in the template files. Scale-specific styles: `DIM (1-2)`, `DIM (1-5)`, `DIM (1-10)`, `DIM (1-20)`, `DIM (1-25)`, `DIM (1-50)`, `DIM (1-100)`, `DIM (1-200)`, `DIM (1-250)`, `DIM (1-400)`, `DIM (1-500)`, `DIM- (PAPERSPACE)`. Use the one that matches the plot scale. Do not create or edit dimension styles by hand and do not use ISO/ANSI presets.

## Linetypes and colors (6.3)

Linework uses predefined linetypes plus three additional firewall linetypes. Always draw with color and linetype ByLayer. The layer color sets the plotted line thickness (see `pen-assignment.md`).

## Open items

1. The sample Xrefs show TXT-design uses `stylu.ttf` (a TrueType file), so ".ttp" is TrueType. STANDARD in the samples uses `arial.ttf`, not Romans: confirm which is right.
6. The sample Xrefs name the styles `TXT- (2)`, `TXT- (3)`, `TXT- (design)`, `TXT- (dim)`, `TXT- (stk)` (space and parentheses), not `TXT-2` etc. Confirm the names in the template. Details in `xref-observed-practice.md` section 4.
2. TXT-3 "Major titles" (2.0 mm) is smaller than TXT-2 "Minor titles" (2.5 mm). Confirm it is intended.
3. "SITES-DIMENION FONT" is printed with that spelling. Confirm the font file name.
4. The names of the scale-specific text styles inside `PR-PH-T-Styles.dwg` are not given.
5. The names and values of the three firewall linetypes are not given.
