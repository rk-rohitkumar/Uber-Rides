# Safe editing rules

Before editing:
- First summarize the current understanding of the request and impacted files.
- If the task is broad or potentially destructive, propose a plan before editing.
- Prefer minimal, precise edits over wide refactors.
- Preserve file structure, formatting style, and naming patterns unless the task explicitly requires a standardization pass.

Editing constraints:
- Do not rename files, folders, tables, columns, measures, or visuals unless required by the task.
- Do not overwrite large sections when a targeted patch is sufficient.
- Do not remove documentation content unless it is clearly obsolete and replaced with better content.
- If a tool output is truncated, narrow the search instead of guessing.

After editing:
- Summarize what changed.
- Identify any follow-up validation required in Power BI Desktop / Fabric / Git review.
- If the change affects behavior, documentation, naming, or dependencies, update the relevant docs/ files.