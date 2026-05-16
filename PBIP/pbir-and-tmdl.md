# PBIR and TMDL Formats

PBIR (enhanced report format) and TMDL (Tabular Model Definition Language) are the source‑control‑friendly formats recommended for PBIP projects.[file:137]

## PBIR – Enhanced report format

PBIR replaces monolithic `report.json` with a folder structure of small JSON files for each report object.[file:137]

### Key PBIR characteristics

- Every page, visual, bookmark, etc. has its own file or folder under a PBIR `definition/` folder.[file:137]
- PBIR JSON files declare public schemas that editors like VS Code can use for validation and IntelliSense.[file:137]
- PBIR improves diff quality, merge conflict resolution, and batch operations (copy pages, visuals, bookmarks) across reports.[file:137]

### Enabling and upgrading PBIR

- PBIR is a preview feature enabled via **Store reports using enhanced metadata format (PBIR)** in Desktop preview settings.[file:137]
- When saving as PBIP with PBIR enabled, the report is stored in a PBIR folder under the report item.[file:137]
- Upgrading from PBIR‑Legacy to PBIR replaces `report.json` with the PBIR folder and is effectively one‑way from the UI; a backup is created but rollback is limited.[file:137]
- New reports in the Service are created in PBIR by default, and edited legacy reports are automatically upgraded.[file:137]

## TMDL – Enhanced semantic model format

TMDL is a folder-based representation of the semantic model that splits tables, roles, cultures, etc. into separate text files.[file:137]

### Key TMDL characteristics

- Replaces the single `model.bim` file with a TMDL `definition/` folder.[file:137]
- Designed to be easy to read and edit in any text editor, improving Git diffs and merge handling.[file:137]
- Works best with the official TMDL VS Code extension for syntax highlighting and validation.[file:137]

### Enabling and upgrading TMDL

- TMDL is enabled via **Store semantic model using TMDL format** in Desktop preview settings.[file:137]
- When enabled, saving the project stores the semantic model as TMDL instead of a single BIM file.[file:137]
- Upgrading from TMSL to TMDL is one‑way; you cannot revert in the UI, so save a copy of PBIP files first if you might need TMSL.[file:137]
- Invalid TMDL edits surface as errors when opening in Desktop, with pointers to the problematic file and location.[file:137]

## Guidance for tools and agents

- Prefer PBIR-aware logic when the report uses PBIR, and TMDL-aware logic when the semantic model uses TMDL.[file:137]
- Inspect `definition.pbir` and `definition.pbism` version properties to infer available formats.[file:137]
- Keep changes small and schema-valid, especially when working with preview formats.[file:137]