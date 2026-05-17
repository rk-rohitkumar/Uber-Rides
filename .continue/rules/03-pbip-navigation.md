# PBIP navigation workflow

When analyzing or modifying a PBIP project, use this navigation order:

1. Start from the .pbip file when available.
2. Identify the report path from the PBIP artifact definition.
3. From the report folder, inspect report metadata and references.
4. Identify the semantic model path or linked semantic model reference.
5. Inspect semantic model definition files before making assumptions about tables, relationships, columns, measures, hierarchies, or calculation logic.
6. Review related documentation in docs/ before proposing structural changes.

PBIP-specific guidance:
- The PBIP file is the project entry point.
- The report folder contains report/page/visual metadata.
- The semantic model folder contains model metadata, often in TMDL or related definition files.
- For impact analysis, check both report and semantic model layers.
- A rename may require coordinated updates across report references, model objects, and documentation.

Do not:
- Start with a full recursive scan unless necessary.
- Assume a report-only issue is isolated from the semantic model.
- Assume a semantic model change is safe without checking report dependencies.