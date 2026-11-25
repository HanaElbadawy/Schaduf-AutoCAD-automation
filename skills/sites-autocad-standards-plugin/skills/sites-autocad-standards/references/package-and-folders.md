# Package, Xref and Folder Structure

Source: manual sections 2.4, 3, 4.1, 5.2 and the sample sheet `GH-LA-PU-00-02` (Drawings List, Grand Heights Phase 1, Landscape, issued 2013.02.17).

## Contents
1. Folder structure (manual 3)
2. What each folder holds
3. Sample package map (Grand Heights Phase 1, Landscape)
4. Title block data seen on the sample
5. How to propose a package for a drawing
6. Open items

## 1. Folder structure (manual 3)

Root (the drive letter and root name are recommendations): `Z:\Sites Project\`

```
Z:\Sites Project\
  01-Submissions\
    00-Submission##   (named "YYYY.MM.DD - Submission Title - Rev.##",
                       for example "2011.03.06 - 100% Design Development - Rev.01")
      01-CADD\                      overall package, prime firm only
        00-Sheet Set\   01-Sheets\   02-Xref\   03-Images\
        04-Excel\       05-Sketches\ 06-Configurations\
      02-PDF\
      03-DWF\
      04-Master Specifications\
      05-Discipline\
        00-Discipline##\
          01-CADD\
            00-Sheet Set\   01-Sheets\   02-Xref\
            03-Images\      04-Excel\    05-Sketches\
  02-Documentation\
  03-Standards\
    01-AutoCAD Procedure Manual\
      02-Templates\   05-Fonts\   06-Pen Assignment\
```

Notes: the manual's text on page 11 shows the submission folder without "Rev.##" and the outline on page 12 with it. The discipline-level paths are given in 4.1 and 8.3 (`...\05-Discipline\00-Discipline##\01-CADD\01-Sheets`, `\02-Xref`, `\03-Images`, `\04-Excel`, `\05-Sketches`, `\00-Sheet Set`). Project files stay on the network server, not on a local drive. Relative paths for Xrefs only work if this structure is kept.

## 2. What each folder holds

| Folder | Content | Who moves or edits |
|---|---|---|
| `01-Sheets` | Sheet DWG files (one layout each) | Each discipline. The prime firm collects them in the overall folder |
| `02-Xref` | Model DWG files referenced by sheets, including the title block lines Xref | Each discipline. The prime firm collects them |
| `03-Images` | Raster images referenced by drawings | Same |
| `04-Excel` | Excel files referenced by drawings | Same |
| `05-Sketches` | Sketches (`PR-PH-SK-DD-Ssss`) | Stay in the discipline folder only |
| `00-Sheet Set` | The `.dst` Sheet Set file | Each discipline. The prime firm assembles a grand Sheet Set |
| `06-Configurations` | Plot configurations: fonts, pen assignment | |
| `02-PDF`, `03-DWF` | Published PDF and DWF sheets | Prime firm |
| `03-Standards` | Templates, fonts, pen file | Prime firm or CAD Coordinator only |

## 3. Sample package map (Grand Heights Phase 1, Landscape)

Numbering `GH-LA-PU-XX-NN`. Sheets A0. Plans at 1:500, legends and tables N.T.S., details VAR. (as listed on the Drawings List).

| Group | Name | Sheets | Scale |
|---|---|---|---|
| `00` | General | `00-00` Cover Sheet, `00-01` Sheet Division, `00-02` Drawings List | N.T.S. |
| `HG` | Hardscape and Grading Plans | `0A` Hardscape Legend (N.T.S.); `01`-`08`, `10`, `12`, `14`, `16` Hardscape Plan | 1:500 |
| `SK` | Staking Plans | `0A`, `0B` Staking Table (N.T.S.); `01`-`08`, `10`, `12`, `14`, `16` Staking Plan | 1:500 |
| `PL` | Planting Plans | `0A` Plant Schedule (1:500); `01`-`08`, `10`, `12`, `14`, `16` Planting Plan | 1:500 |
| `LI` | Lighting Plans | `0A` Lighting Legend; `01`-`08`, `10`, `12`, `14`, `16` Lighting Plan | 1:500 |
| `DE` | Landscape Details | `01`-`19` (the list shows `19` twice) | VAR. |
| `FU` | Furniture Details | `01` | N.T.S. |
| `SR` | Structural Details | `01`-`04` | VAR. |
| `EM` | Electromechanical Details | `01`-`06` | VAR. |

Observations: the group order is general, hardscape and grading, staking, planting, lighting, details, furniture, structural, electromechanical. The plan groups (`HG`, `SK`, `PL`, `LI`) share the same sheet numbers, so the same plan area has the same number in each group. The numbers `09`, `11`, `13`, `15` are absent from the lists (the reason is not stated).

## 4. Title block data seen on the sample

Fields: Project, Owner, Landscape Architecture Consultant, Project Manager, Master Plan Concept Designer, Master Plan Consultant, Infrastructure Consultant, Disclaimer, revision table (Rev., Date, Description), Issue, Issue Date, Scales, Original Size, File Name, Consultant, Title, Drawing No., Project No., Rev., Current Issue Signatures (Author, Checker, Approver).
Values on the sample: issue "100% Construction Documents", date `2013.02.17`, scale N.T.S., size A0, file name `GH-LA-PU-00-02.dwg`, Drawing No. `GH-LA-PU-00-02`, Project No. `KG-10 006 0160`, Rev. `2B` (earlier `1A`, dated 2011.09.15), Author `SITES - M.A`, Checker `SITES - E.T`, Approver `SITES - M.S`. Title lines: "GRAND HEIGHTS - PHASE (1) 100% Construction Documents" and "DRAWING LIST".

## 5. How to propose a package for a drawing

1. Say which naming scheme you use (see `naming.md`, section 5). If the user said to follow the sample package, use section 3 and note that it differs from the manual.
2. List the content of the drawing by type (hardscape, planting, lighting, staking, details...).
3. Propose the Xref (model) files: one per area and content, stored in `02-Xref`. The sample Xrefs are named `GH-X-LA-<AREA>-<Content>` (areas `PU`, `LP`, `SV`; contents Hardscape, Planting, Lighting, Staking; plus `GH-X-LA-GENERAL-MATCH_LINE_1-500`), while the manual's pattern is `PR-PH-X-DD-Ssss`. Say which one you use and ask if unsure. The title block lines Xref is `PR-PH-X-00-Title Block A0 Lines`. The content split per Xref is in `xref-observed-practice.md`.
4. Propose the sheets: groups as in section 3, with serials and scales, one layout per sheet file, layout named like the file.
5. Propose the folder tree with the real submission name, and where each file goes.
6. List what you assumed and the open items.
7. Present it as a proposal for approval. Do not create folders or files until the user approves.

## 6. Open items

1. The meaning of `PU`, `LP`, `SV`, and the real `PR` and `PH` codes (the Xrefs and blocks suggest `PR` = `GH`; the sample blocks have no phase segment).
2. Which Xref naming applies: sample `GH-X-LA-PU-Hardscape` or manual `PR-PH-X-DD-Ssss`.
3. The rule behind the sheet numbers `10`, `12`, `14`, `16` after `08`.
4. The duplicate `DE-19` row in the sample list.
5. Whether the sample package follows the manual's folder structure or its own.
