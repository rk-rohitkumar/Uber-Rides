# PBIP structure

## Purpose

This document explains how the PBIP project is physically organized in the repository.

## Entry point

- PBIP / PBIR file path: `TODO`
- Main report path: `TODO`
- Main semantic model path: `TODO`

## Folder map

```text
TODO: paste a concise folder tree here
```

## Report layer

Document:
- report folder purpose
- page definitions
- visual metadata locations
- theme / resources / custom visual references
- important report configuration files

## Semantic model layer

Document:
- semantic model folder purpose
- where tables, measures, relationships, roles, perspectives, calculation items, or annotations live
- whether the model is stored as TMDL, TMSL-style JSON, or mixed project metadata

## Navigation workflow for contributors

Recommended order for inspecting the project:
1. Open PBIP / PBIR
2. Identify report folder
3. Identify semantic model
4. Review docs/
5. Inspect only the files relevant to the task

## Change impact notes

Document examples such as:
- renaming a measure may require report updates
- column renames may affect model and report references
- visual label changes may require report metadata updates