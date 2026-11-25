# Schaduf AutoCAD Automation

An AI-assisted AutoCAD workflow designed to help the team understand and apply SITES CAD standards, automate landscape drawing workflows, and improve drawing consistency.

## Project Overview

This repository brings together two main components:

**1. SITES AutoCAD Standards Skill**

Provides Claude with project-specific CAD standards, including:
- Drawing naming conventions.
- Layer naming and organization.
- Xref requirements.
- Blocks and annotation standards.
- Pen-table and plotting references.
- Drawing organization and cleanup guidelines.

**2. AutoCAD MCP Server**

Connects Claude Desktop to AutoCAD, allowing Claude to inspect drawings and perform supported CAD operations through MCP tools.

The project references the original AutoCAD MCP Pro package rather than maintaining a separate copy of its source code.

## Architecture

```text
Team Member
    |
    v
Claude Desktop
    |
    +----------------------+
    |                      |
    v                      v
SITES Standards Skill   AutoCAD MCP
    |                      |
    v                      v
CAD Rules & Guidance    AutoCAD Operations
    |                      |
    +----------+-----------+
               |
               v
       AutoCAD Drawings
```

## Repository Structure

```text
Schaduf-AutoCAD-automation/
│
├── skills/
│   └── sites-autocad-standards-plugin/
│       ├── .claude-plugin/
│       ├── skills/
│       │   └── sites-autocad-standards/
│       │       ├── SKILL.md
│       │       └── references/
│       └── README.md
│
├── mcp/
│   ├── claude_desktop_config.example.json
│   └── installation-guide.md
│
├── prompts/
│   ├── stage-01-render-to-cad.md
│   ├── stage-02-package-mapping.md
│   └── stage-03-discipline-xrefs.md
│
├── tests/
│   └── test-checklist.md
│
└── README.md
```

## Workflow Stages

### Stage 01 — Landscape Render to AutoCAD 2D

Convert landscape renders into editable 2D AutoCAD drawings while following documented CAD standards.

Prompt: `prompts/stage-01-render-to-cad.md`

### Stage 02 — Design Package Mapping

Analyze complete design packages and map sheets, disciplines, Xrefs, naming conventions, and folder structures.

Prompt: `prompts/stage-02-package-mapping.md`

### Stage 03 — Discipline Xrefs and Standards Validation

Inspect discipline drawings, validate layers, blocks, colors, lineweights, labels, levels, and Xref relationships.

Prompt: `prompts/stage-03-discipline-xrefs.md`

## Getting Started

### Prerequisites

- Windows
- AutoCAD installed
- Claude Desktop
- Git
- uv / uvx
- Access to this private repository

### Setup

1. Clone this repository.
2. Review the SITES Standards Skill package.
3. Follow `mcp/installation-guide.md`.
4. Configure Claude Desktop using `mcp/claude_desktop_config.example.json`.
5. Open AutoCAD and verify the MCP connection.
6. Use the appropriate workflow prompt for your task.

## Testing

Use `tests/test-checklist.md` to validate:

- MCP connectivity.
- Skill loading and standards understanding.
- Render-to-CAD workflow.
- Design package mapping.
- Discipline Xref validation.
- Drawing quality and deliverables.

A test should only be marked as passed after reviewing actual results and evidence.

## Team Collaboration

This is a private team repository.

Each team member should:
- Have GitHub access.
- Clone the repository.
- Configure Claude Desktop and AutoCAD MCP locally.
- Use the shared Skill and workflow prompts.
- Keep personal credentials and local configuration files private.

## Important Notes

- Official SITES standards must take priority over assumptions.
- Undocumented requirements must be identified rather than invented.
- Estimated dimensions must not be presented as verified measurements.
- Original drawings must be preserved.
- Production changes require appropriate review and approval.

## Original MCP Project

AutoCAD MCP Pro:

https://github.com/U-C4N/Autocad-MCP

---

**Project:** Schaduf AutoCAD Automation  
**Purpose:** AI-assisted CAD standardization and landscape drawing workflows.