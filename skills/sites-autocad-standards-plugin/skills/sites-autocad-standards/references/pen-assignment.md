# Pen Assignment (GRAND HEIGHTS - PEN.ctb)

Source: manual 7.1 to 7.3, and the file `GRAND HEIGHTS - PEN.ctb` read directly. The exact values for all 255 colors are in `pen-table.csv` (columns: `aci_color`, `lineweight_mm`, `screening_pct`). Always read that file for exact values. The summary below is not enough on its own.

## How it works

- The color of the layer an object is on decides its plotted lineweight and screening. Objects are ByLayer. Never hard-code an object's color (7.1).
- The pen file keeps the object's own color and linetype (the file sets only lineweight and screening). Plots are therefore controlled by choosing the layer color.
- One pen file is used by all disciplines. It is stored in `Z:\Sites Project\03-Standards\01-AutoCAD Procedure Manual\06-Pen Assignment\`. The manual calls it "Sites Cad-PEN" / `SITES-PEN.ctb`, and the project file is named Grand Heights - PEN. It is installed through the Plot Style Manager (drag the file in), then restart AutoCAD (7.2).
- Checker notes use True Color so they do not convert to grayscale (10.1).

## Structure (manual 7.3, confirmed against the file)

- Colors 1 to 9: all 100% screening, lineweights 0.10, 0.20, 0.30, 0.40, 0.50, 0.60, 0.70, 0.80, 0.90 mm.
- Colors 250 to 255: all 0.01 mm, screening 10, 20, 40, 60, 80, 100 %.
- Colors 10 to 249: groups of 50 colors starting at 10, 60, 110, 160 and 210 (the manual names the groups reds, greens, blues, cyans, magentas). In each block of ten colors (10-19, 20-29, ...): four solid 100% pens (two thin, two heavy), then screened pens at 0.05 mm and 0.01 mm. The thin weights step up block by block (0.01, 0.05, 0.10, 0.15, 0.20 mm) and the heavy ones too (0.25, 0.30, 0.35, 0.40, 0.45 mm). Screening values vary by block and have a few irregularities, so read them from the CSV.

## Choosing a color for a layer

1. Decide the output wanted: lineweight and screening.
2. Find a color with those values in `pen-table.csv`.
3. Pick among the colors with the same values for on-screen readability (the five hue groups allow this).
4. Use the same color for the same layer role across the whole package, and record the choice.
5. New layers default to color 7, which plots at 0.70 mm and 100%. Do not leave layers at the default by accident.

## Open items

1. The per-layer color assignment of the project is not in the manual. It must come from the sample Xrefs (see `workflows.md`, Stage 3) or from the AI-CAD Lead.
2. The manual's text and the file agree on structure. If a plotted sheet does not match the table, check that the right `.ctb` is installed and selected in the page setup.
