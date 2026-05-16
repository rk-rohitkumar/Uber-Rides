# PBIP Folder Structure

This document summarizes the key PBIP folders and files so tools and agents can navigate a project safely.[file:137]

## Root

Typical items in the PBIP root:

- `*.pbip` – project pointer file.[file:137]
- `*.Report/` – report item definition folder.[file:137]
- `*.SemanticModel/` – semantic model item definition folder.[file:137]
- `.gitignore` – excludes cache and local settings such as `cache.abf` and `localSettings.json`.[file:137]

The `.pbip` file usually points to one report folder, but you can have multiple reports and semantic models in the same project folder.[file:137]

## Semantic model folder (`<name>.SemanticModel`)

Important files and subfolders:[file:137]

- `definition.pbism` – overall semantic model definition and core settings, including supported definition formats via the `version` property.[file:137]
- `model.bim` – Tabular Model Scripting Language (TMSL) database object when the model uses TMSL.[file:137]
- `definition/` – Tabular Model Definition Language (TMDL) folder when the model uses TMDL.[file:137]
- `diagramLayout.json` / `semanticModelDiagramLayout.json` – diagram metadata; not supported for external editing during preview.[file:137]
- `DAXQueries/` – one `.dax` file per saved DAX query view tab, plus editor settings.[file:137]
- `TMDLScripts/` – one `.tmdl` file per TMDL script tab, plus editor settings.[file:137]
- `unappliedChanges.json` – pending Power Query changes that Desktop may apply later to overwrite existing queries.[file:137]
- `cache.abf` – Analysis Services backup file containing cached data and model; should be ignored in source control.[file:137]
- `.platform` – Fabric Git integration file for connecting the item to a workspace/repo.[file:137]

## Report folder (`<name>.Report`)

Important files and subfolders:[file:137]

- `definition.pbir` – overall report definition and dataset reference; indicates PBIR vs PBIR‑Legacy support via the `version` property.[file:137]
- `report.json` – PBIR‑Legacy report metadata; not supported for external editing during preview.[file:137]
- `definition/` – PBIR folder structure for enhanced report format.[file:137]
- `mobileState.json` – mobile layout configuration; not supported for external editing during preview.[file:137]
- `CustomVisuals/` – private custom visuals packaged as `.pbiviz`.[file:137]
- `RegisteredResources/` – user-managed resources such as themes, images, and custom visual packages.[file:137]
- `.platform` – Fabric Git integration file for the report item.[file:137]

## Programmatic traversal pattern

When building tools or scripts:

1. Locate the `.pbip` file to find the primary report.[file:137]
2. Follow the pointer into the corresponding `<name>.Report` folder.[file:137]
3. Read `definition.pbir` to find the dataset reference (`byPath` or `byConnection`).[file:137]
4. If `byPath`, resolve the relative path into the `<name>.SemanticModel` folder and then to `definition.pbism` or the TMDL `definition/` folder.[file:137]