# Agent Instructions for PBIP Repositories

Use this document as the operational guide when working on PBIP projects with local models.[file:137]

## Scope and priorities

- Work only inside the current workspace/repository, not arbitrary folders on the machine.
- Treat `docs/pbip/*` and `docs/project/*` as higher-priority truth than internal model knowledge.
- Analyze first, propose a plan, then apply edits only after user approval.

## Reading order for PBIP tasks

When asked to understand or modify a PBIP project:

1. Read `docs/pbip/*` to learn PBIP, PBIR, TMDL, and safety rules.[file:137]
2. Read `docs/project/*` for project-specific architecture, naming, and business rules.
3. Inspect the `.pbip` file to locate the primary report and semantic model.[file:137]
4. Read the report’s `definition.pbir` to understand dataset references and formats.[file:137]
5. Read the semantic model’s `definition.pbism` and TMSL/TMDL structure.[file:137]
6. Drill into PBIR and TMDL folders only as needed for the requested change.

## Editing behavior

- Prefer editing PBIR and TMDL content over legacy monolithic files like `report.json` and `model.bim` when PBIR/TMDL are available.[file:137]
- Do **not** externally edit preview-unsupported files such as `report.json`, `mobileState.json`, diagram layout JSON files, or undocumented semantic model JSON files.[file:137]
- If `unappliedChanges.json` exists, warn that applying pending changes in Desktop can overwrite external query edits.[file:137]
- After suggesting or applying changes, remind the user that Desktop must be restarted to load the new project state.[file:137]

## Safety rules

- Ask for explicit confirmation before destructive actions (delete, move, bulk rename, large-scale search/replace).
- Keep changes minimal, Git-friendly, and easy to review in pull requests.
- If a requested change risks breaking JSON schemas or preventing Desktop from opening the project, stop and explain the risk instead of blindly applying it.