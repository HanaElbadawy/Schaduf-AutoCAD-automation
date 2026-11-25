# Sheet Set and Publishing

Source: manual 8 and 9. The Sheet Set (.dst) is the primary deliverable of the project.

## Limits

The Sheet Set Manager is part of the AutoCAD interface. It is not known whether the available tools can create or edit a `.dst`. Create the sheet DWG files and layouts, then tell the user exactly which Sheet Set steps they must do in AutoCAD. Do not say a Sheet Set was built unless it was.

## Creating a Sheet Set (8.3)

1. File menu, New Sheet Set, "An example sheet set", browse to the template `PR-PH-T-Sheet Set.dst` (in the standards `02-Templates` folder. The manual prints the path with `05-Fonts\02-Templates`, which looks like a typing error).
2. Name the new Sheet Set and save its `.dst` in `...\05-Discipline\00-Discipline##\01-CADD\00-Sheet Set\`.

## Sheet Set properties (change only these)

- Sheet Set tab: Page Setup Overrides File = `PR-PH-T-Page Setups.dwt`.
- Project Control tab: Project Number (the discipline office's code), Project Name (for example "Sites Cad - Phase (1)"), Project Phase (for example "100% Design Development").
- Custom Properties: SET Approver, SET Checker, SET Date (`YYYY.MM.DD`), SET Sheet Size (for example A0).

## Sheet properties (change only these)

- Sheet tab: Sheet Title (the manual's example is `GH-LA-00-02`).
- Custom Properties: SHEET Author, SHEET Rev # (for example `1A`), SHEET Scale (for example `1:250`), SHEET Title (for example "HARDSCAPE PLANS"), SHEET Type (for example `12`, from the T-F table of 4.1).

The title block variable text is built from fields. Never type it by hand in the sheet file. After entering properties, use Resave All on the Sheet Set title to update every sheet file.

## Organizing sheets (8.4)

Each discipline organizes sheets in subsets (can be nested), imports layouts as sheets, and can remove a sheet (this only unlinks it, nothing is deleted).

## Checking properties (8.6)

Import a temporary blank sheet named "Sheet Set Table", right-click the Sheet Set title, Insert Sheet List Table, add the columns Project Number, Project Name, Project Phase, SET Approver, SET Checker, SET Date, SET Sheet Size, Sheet Title, SHEET Author, SHEET Rev #, SHEET Scale, SHEET Title, SHEET Type, and place the table. Use it to find sheets with errors and repeat until clean.

## Publishing (9)

- Check that the Page Setup Overrides File is `PR-PH-T-Page Setups.dwt`.
- PDF: right-click the Sheet Set, Publish, "Publish Using Page Setup override", `SITES-A0-PDF`. DWF: `SITES-A0-DWF`. Printer: create a page setup named `SITES-A0-<Printer Name>` starting from `GH-A0`.
- A PDF is created for every drawing file at each revision. Transparent objects and wipeouts may print differently, so check PDF transparency settings.

## Open items

1. The T-F table (SHEET Type values) is referred to in 4.1 and not in the pages available.
2. Confirm the Sheet Set template path (typing error above).
3. Whether the tools can drive the Sheet Set Manager.
