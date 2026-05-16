# PBIP Overview

Power BI Desktop projects (PBIP) let you save a report and its semantic model as a *project* made of folders and text files instead of a single PBIX file.[file:137]

## Why PBIP exists

- Enable Git-based version control and code review on report and model definitions.[file:137]
- Make folder structure and artifacts transparent (separate report and semantic model folders).[file:137]
- Allow external tools like VS Code, Tabular Editor, or scripts to generate and edit metadata.[file:137]
- Support CI/CD workflows that act directly on project files instead of opaque PBIX artifacts.[file:137]

## PBIP is in preview

- PBIP is currently a **preview feature** in Power BI Desktop.[file:137]
- It must be enabled under **File ▸ Options and settings ▸ Options ▸ Preview features ▸ Power BI Project (.pbip) save option**.[file:137]
- Because it is preview, schemas and behaviors can still change, so adopt carefully for production workloads.[file:137]

## High‑level project structure

When you save as PBIP, Desktop creates something like:

- `MyProject.pbip` – pointer that opens a report and semantic model together.[file:137]
- `MyProject.Report/` – report definition folder.[file:137]
- `MyProject.SemanticModel/` – semantic model definition folder.[file:137]
- `.gitignore` – default ignore rules for cache and local settings files.[file:137]

Opening the `.pbip` file, or a `definition.pbir` inside a report folder, opens the report for editing and, if referenced by path, the associated semantic model.[file:137]

## Key benefits

- Text editor support with JSON schemas for many files.[file:137]
- Easier reuse of report pages and semantic model tables across projects.[file:137]
- Source-control‑ready by design, with Git and Azure DevOps examples in the docs.[file:137]
- Programmatic generation and bulk editing of definitions (measures, visuals, pages, etc.).[file:137]