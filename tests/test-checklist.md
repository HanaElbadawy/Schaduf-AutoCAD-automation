# AutoCAD MCP & SITES Standards — Test Checklist

## 1. Environment Setup

- [ ] Windows environment is ready.
- [ ] AutoCAD is installed and opens successfully.
- [ ] Claude Desktop is installed.
- [ ] Git is installed.
- [ ] uv and uvx are available.
- [ ] The AutoCAD MCP configuration is added correctly.
- [ ] Claude Desktop connects to the AutoCAD MCP server.
- [ ] AutoCAD is accessible through MCP tools.

## 2. SITES Standards Skill

- [ ] Claude can load the SITES Standards skill.
- [ ] Claude can explain the drawing naming structure.
- [ ] Claude understands the Xref rules.
- [ ] Claude understands Model Space and Paper Space requirements.
- [ ] Claude can identify drawing cleanup requirements.
- [ ] Claude can retrieve relevant layer naming rules.
- [ ] Claude can identify documented pen-table requirements.
- [ ] Claude distinguishes official standards from assumptions.
- [ ] Claude does not invent undocumented standards.

## 3. Stage 01 — Render to CAD

- [ ] A landscape render is provided.
- [ ] Claude identifies the visible landscape elements.
- [ ] Claude identifies missing scale or dimensional information.
- [ ] Drawing units are verified.
- [ ] Appropriate layers are created.
- [ ] Geometry is reconstructed as editable CAD entities.
- [ ] Blocks are used where appropriate.
- [ ] Roads, parking, pathways, planting, and furniture are represented.
- [ ] Geometry is inspected for duplicates and unintended overlaps.
- [ ] The drawing is saved as a separate DWG.
- [ ] Assumptions and estimated dimensions are reported.

## 4. Stage 02 — Design Package Mapping

- [ ] A sample design package PDF is provided.
- [ ] Claude identifies the sheet register.
- [ ] Drawing numbers and titles are extracted.
- [ ] Disciplines are identified.
- [ ] Sheet relationships are documented.
- [ ] Xref dependencies are mapped where evidence exists.
- [ ] Naming conventions are analyzed.
- [ ] A proposed folder structure is prepared.
- [ ] Observed facts are distinguished from recommendations.
- [ ] Missing information and inconsistencies are reported.

## 5. Stage 03 — Discipline Xrefs

- [ ] Discipline drawings and Xrefs are inspected.
- [ ] Layer inventory is extracted.
- [ ] Layer naming is checked against official standards.
- [ ] Layer colors are inspected.
- [ ] Pen-table assignments are verified.
- [ ] Lineweights and screening are checked.
- [ ] Block names and insertion layers are inspected.
- [ ] Labels and text styles are reviewed.
- [ ] Level annotations are inspected.
- [ ] Xref paths and dependencies are checked.
- [ ] Compliance issues are documented.
- [ ] Corrections are applied only after approval.
- [ ] Original drawings are preserved.

## 6. Final Quality Assurance

- [ ] All drawings are editable.
- [ ] All required layers and blocks are organized.
- [ ] Drawing units are correct.
- [ ] Xrefs are resolved.
- [ ] Plot output is reviewed.
- [ ] PDF output is readable.
- [ ] No original files were overwritten.
- [ ] Final deliverables are saved in the correct locations.
- [ ] All unresolved issues are documented.

## Test Results

For each test, record:

- Test date:
- Tester:
- Test stage:
- Result: Pass / Fail / Needs Review
- Evidence or screenshots:
- Issues found:
- Corrective action:
- Retest result:

## Important

This checklist is a testing plan, not proof of compliance.

Mark a test as Pass only after performing it and reviewing the actual output.

Do not approve production drawings based only on Claude's verbal confirmation.