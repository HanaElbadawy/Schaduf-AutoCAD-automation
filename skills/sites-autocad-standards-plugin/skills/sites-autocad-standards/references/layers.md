# Layers Naming Protocol

Source: manual 6.4 (Layers Naming Protocol), 6.5, 10.1.

The layer conventions shall be used to create all AutoCAD drawings. Layer names are a hierarchy, alphanumeric, with easy-to-remember abbreviations. A layer name has at most four segments separated by hyphens.

## Format

`DD-XXXX-XXXX-Description`

| Segment | Name | Length | Required |
|---|---|---|---|
| 1 | Discipline Code | 2 characters | Yes |
| 2 | Major Group | 4 characters | Yes |
| 3 | Minor Group | 4 characters, user-defined | Optional |
| 4 | Item Description | User-defined | As needed |

## Discipline codes (manual 4.1, same codes for layers and files)

`00` Project Standard Item, `AR` Architectural, `CV` Civil, `EL` Electrical, `FR` Fire Protection, `GN` General, `HV` HVAC, `IN` Interiors, `LA` Landscape Architecture, `ME` Mechanical, `PB` Plumbing, `QP` Equipment, `SR` Structural, `TL` Telecommunications, `ZZ` Contractor/shop drawings.

## Examples from the manual

| Layer name | Meaning |
|---|---|
| `AR-DOOR` | Architecture, Doors major group |
| `LA-HARD` | Landscape Architecture, Hardscape major group |
| `AR-DOOR-JAMB` | Door Jambs minor group |
| `LA-HARD-PAVE` | Landscape Hardscape Paving minor group |
| `AR-DOOR-JAMB-Type 01` | Door Jambs (Type 01) |
| `AR-DOOR-JAMB-Type 02` | Door Jambs (Type 02) |
| `LA-HARD-PAVE-Reddish Interlock` | Reddish Interlock Pavers |
| `LA-HARD-PAVE-Gray Interlock` | Gray Interlock Pavers |

Write names exactly in these forms (codes in capitals, item description as shown). The minor group is defined by the user to cover special project requirements.

## Other layer rules

- Objects take the color and linetype of their layer (ByLayer). The layer color decides the plotted lineweight and screening through the pen file (`pen-assignment.md`).
- Blocks are made on layer 0 (6.5).
- The checker's layer is `X-CHKR` (10.1).
- The manual says this section lists layer names, linetypes, colors and plotted pen weights, but the layer table itself is not in the pages available. Do not invent colors or linetypes. Propose a layer list and ask for approval (see `workflows.md`).

## Open items (ask, do not guess)

1. Where is the full layer list with linetypes, colors and the three additional firewall linetypes?
2. If the minor group is not used, does the item description become the third segment, or is a placeholder used?
3. The manual says names are alphanumeric, but the examples contain spaces ("Type 01"). Are spaces allowed? AutoCAD accepts them.
4. Is there a standard list of major and minor groups beyond DOOR, HARD, JAMB and PAVE (for example for planting, lighting, staking, irrigation)?
