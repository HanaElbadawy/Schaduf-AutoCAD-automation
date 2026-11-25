# Stage 03 — Discipline Xrefs and CAD Standards Validation

## Objective

Analyze discipline-specific AutoCAD drawings and external references (Xrefs) to understand their contents, validate their compliance with official SITES CAD standards, and prepare them for coordinated project delivery.

## Instructions

### 1. Review the Official Standards
- Read the installed SITES AutoCAD Standards skill.
- Review all relevant reference documents.
- Identify official requirements for:
  - Layer naming.
  - Layer colors.
  - Lineweights.
  - Linetypes.
  - Block naming.
  - Text styles.
  - Dimension styles.
  - Annotation and labeling.
  - Xref organization.
- Use only documented standards.
- Clearly identify any missing or ambiguous requirements.

### 2. Inspect Each Discipline Xref
For every supplied discipline drawing or Xref:

- Identify the drawing name and discipline.
- Inspect its layers and layer properties.
- Identify blocks and their insertion layers.
- Inspect text, labels, and annotations.
- Identify levels and elevation information.
- Review geometry and drawing units.
- Identify external references and their paths.
- Report missing, unresolved, or incorrectly linked Xrefs.

### 3. Validate Layer Naming
- Compare actual layer names against the official naming conventions.
- Identify valid, invalid, and undocumented layer names.
- Check whether objects are assigned to appropriate layers.
- Identify inconsistent naming across disciplines.
- Suggest corrections only when supported by official standards.

### 4. Validate Colors and Pen Assignments
Use the official project pen table, including the supplied `GRAND HEIGHTS - PEN` reference where applicable.

For each relevant layer, inspect:
- Layer name.
- Assigned color.
- Plot style or pen-table mapping.
- Lineweight.
- Screening percentage, if applicable.
- Linetype.

Important:
- Do not assume that an AutoCAD color automatically corresponds to a particular lineweight or screening percentage.
- Verify the actual CTB/STB or pen-table mapping.
- Report any missing or conflicting assignments.

### 5. Inspect Blocks and Symbols
Identify and validate:
- Landscape symbols.
- Trees and planting blocks.
- Furniture blocks.
- Level markers.
- Section and detail markers.
- Other annotation symbols.

For each block, inspect:
- Block name.
- Insertion layer.
- Insertion point.
- Scale.
- Rotation.
- Nested entities where relevant.

Compare block naming with the official SITES requirements.

### 6. Review Labels and Levels
Inspect:
- Text content and formatting.
- Text styles and heights.
- Level labels and elevation values.
- Leader annotations.
- Dimension styles.
- Annotation scales.

Verify that labels and levels are readable and consistent with the project standards.

Do not modify or reinterpret engineering elevations without reliable reference information.

### 7. Review Xref Coordination
- Identify the relationship between discipline drawings.
- Check reference paths and attachment/overlay settings.
- Identify duplicated or conflicting content.
- Check whether layer names and properties are consistent across references.
- Report coordination issues.

### 8. Prepare a Compliance Report
Create a structured report containing:

1. Drawing and discipline overview.
2. Layer inventory.
3. Layer naming validation.
4. Color and pen-table validation.
5. Block inventory and naming validation.
6. Text, labels, and levels review.
7. Xref dependency and path review.
8. Identified inconsistencies.
9. Recommended corrections.
10. Unresolved questions.

### 9. Apply Approved Corrections
Only after approval:

- Correct documented layer naming violations.
- Apply verified layer properties.
- Correct block names where appropriate.
- Fix confirmed Xref path issues.
- Update annotation styles according to official requirements.

Never apply uncertain corrections automatically.

Preserve original files and save corrected drawings as separate versions.

## Important Rules

1. Never invent official SITES standards.
2. Never guess pen-table assignments.
3. Never rename or modify Xrefs without understanding their dependencies.
4. Never change engineering levels or dimensions based on assumptions.
5. Distinguish confirmed violations from recommendations.
6. Request clarification whenever a requirement is ambiguous.
7. Maintain an audit trail of modifications.

## Expected Output

A detailed Discipline Xref Compliance Report and, after approval, corrected editable AutoCAD drawings that follow verified SITES standards and the applicable project pen table.