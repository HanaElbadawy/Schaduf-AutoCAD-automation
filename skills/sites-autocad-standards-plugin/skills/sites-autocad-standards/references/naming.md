# Naming (files, sheets, blocks, drawing numbers)

There are three naming sources and they do not fully agree. Read section 5 before naming anything.

## Contents
1. Manual 4.1-4.5 and 6.6
2. Discipline codes
3. NAMING.xlsx scheme
4. Sample package scheme (Grand Heights Phase 1)
5. Conflicts and what to do
6. Validation procedure
7. Open items

## 1. Manual formats (4.1 to 4.5, 6.6)

All file names are in capitals, no spaces. Model (Xref) file names are never changed. Changing sheet file names should be avoided.

| Item | Format | Notes |
|---|---|---|
| Model file (Xref) | `PR-PH-X-DD-Ssss.dwg` | `X` = Xref designator. `Ssss` = descriptor, format set by the discipline |
| Sheet file | `PR-PH-DD-BBF-SSS.dwg` | `BB` = building number or subset (set by the Discipline Manager). `F` = floor level or drawing type (set by the Discipline Manager). `SSS` = `00A`, `00B`, `00C`... for general sheets and notes, `001`, `002`... for sheet sequence |
| Sketch | `PR-PH-SK-DD-Ssss` | Stored only in the discipline's `05-Sketches` folder |
| Template or prototype | `PR-PH-T-Ssss` | Descriptor set by the CAD Coordinator |
| Raster image | `PR-PH-R-DD-BBF-SS-Ssss` | `SS` = sequence of the drawing that references the image |
| Excel file | `PR-PH-E-DD-Ssss` | |
| Block | `PR-PH-B-DD-Ssss` | `DD` = `00` for a standard project block |
| Title block lines (Xref) | `PR-PH-X-00-Title Block A0 Lines` | Manual 2.7 (contains spaces as printed) |

`PR-PH` is the project and phase identifier, assigned by the project manager. The real values are not in the manual.

## 2. Discipline codes

`00` Project Standard Item, `AR` Architectural, `CV` Civil, `EL` Electrical, `FR` Fire Protection, `GN` General, `HV` HVAC, `IN` Interiors, `LA` Landscape Architecture, `ME` Mechanical, `PB` Plumbing, `QP` Equipment, `SR` Structural, `TL` Telecommunications, `ZZ` Contractor/shop drawings.

## 3. NAMING.xlsx scheme

Format `PR-PH-DD-BBT-NNN`, example `PR-PH-LA-IN0-000`. `BB` = subset, `T` = drawing type, `NNN` = three-digit serial. This is the manual's `BBF` with the last character called "drawing type".

Landscape (LA):

| Subset | Name | Drawing types |
|---|---|---|
| `IN` | Info. and Generals | 0 General sheets |
| `GR` | Grading | 0 General sheets; 1 Plans; 2 Details |
| `HS` | Hardscape | 0 General sheets; 1 Plans |
| `PL` | Planting | 0 General sheets; 1 Plans |
| `LI` | Lighting | 0 General sheets; 1 Plans-Destribution (as written); 2 Plans-Wiering (as written) |
| `SG` | Signage and Way Finding | 0 General sheets; 1 Plans-Distribution; 2 Plans-Features Design |
| `DL` | Details | 0 Landscape Details; 1 Electromechanical Details; 2 Structural Details |
| `SC` | Security CCTV | 0 General sheets; 1 Plans |
| `IR` | Irrigation | 0 General sheets; 1 Plans-Main Line and Controller; 2 Plans-Trees; 3 Plans-Groundcovers; 4 Plans-Lawns; 5 Details |

Fixed serials in `IN0`: `000` Cover Sheet, `001` List of Drawings, `002` Sheet Division, `003` Master Legend. Other rows show `999` as a placeholder.

Architecture (AR): the workbook lists a letter and digit pair (A/0 General; B/1 Site plans, demolition, temporary work; C/2 Plans (Floor/Roof); D/3 Elevations/Sections; ../4 Enlarged scale; ../5 Schedules/Diagrams; ../6 Reflected Plans (Ceiling); ../7 Vertical circulation) and a floor code (0 not applicable, B Basement, 1 to 4 floors, M Mezzanine; with "Elevations/Sections when T=3"). How these combine is not stated. The "Example" column for AR repeats LA examples (such as `PR-PH-LA-HS1-999`). Do not build AR sheet names from it. Ask.

## 4. Sample package scheme (Grand Heights Phase 1, Landscape)

The sample sheet `GH-LA-PU-00-02` (Drawings List, issued 2013.02.17) numbers sheets as `GH-LA-PU-XX-NN`:

- `GH` project, `LA` discipline, `PU` (meaning not stated; same on every sheet), `XX` two-character group, `NN` serial.
- Groups seen: `00` General, `HG` Hardscape and Grading, `SK` Staking, `PL` Planting, `LI` Lighting, `DE` Landscape Details, `FU` Furniture Details, `SR` Structural Details, `EM` Electromechanical Details.
- Serials: `0A`, `0B` for legends and tables; `01`, `02`... for sheets. Full list in `package-and-folders.md`.
- The Drawing No. in the title block equals the file name (`GH-LA-PU-00-02.dwg`).

## 5. Conflicts and what to do

| Point | Manual 4.1 | NAMING.xlsx | Sample package |
|---|---|---|---|
| Sheet number pattern | `PR-PH-DD-BBF-SSS` | `PR-PH-DD-BBT-NNN` | `GH-LA-PU-XX-NN` |
| Discipline position | 3rd segment | 3rd segment | 2nd segment (`LA`), `PU` in 3rd |
| General sheets | `00A`, `00B`... | `000` to `003` in `IN0` | `00-00`, `00-01`, `00-02`; legends `0A`, `0B` |
| Subset codes | Set by the Discipline Manager | `IN`, `GR`, `HS`, `PL`, `LI`, `SG`, `DL`, `SC`, `IR` | `00`, `HG`, `SK`, `PL`, `LI`, `DE`, `FU`, `SR`, `EM` |
| Sheet Set example (8.5) | `GH-LA-00-02` (a fourth form) | | |

What to do: use the scheme the user names for the task. If the user says to follow the sample package, use section 4 and say that it differs from the manual and the workbook. If none is named, show this table and ask. Never reconcile silently.

## 6. Validation procedure

1. Keep the original string exactly.
2. Split it into segments at hyphens without assuming missing delimiters.
3. Compare each segment with the scheme in use (and say which one).
4. Report valid, invalid, ambiguous and unlisted segments separately.
5. Check capitals and no spaces (4.1).
6. Do not invent codes or normalize spelling, and state any change you propose.

## 7. Open items

1. What are the real `PR` and `PH` values, and what does `PU` mean in the sample numbering?
2. Which scheme applies to new drawings: manual, workbook or sample package?
3. How are AR names built from the letter, digit and floor code?
4. What is the numbering rule for serials (the sample uses `01`-`08`, then `10`, `12`, `14`, `16`)?
5. The Sheet Set section refers to a "T-F Table" in section 4.1 for the sheet type. It is not in the pages available.
6. Spelling of "Destribution" and "Wiering" (workbook, Lighting).
