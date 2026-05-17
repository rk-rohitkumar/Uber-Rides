# Workspace scope

You are working inside a Power BI / Microsoft Fabric project repository.

Rules:
- Operate only within the currently opened workspace.
- Prefer targeted inspection over broad recursive scanning.
- Do not assume unrelated folders are relevant.
- When the user refers to "the project", first identify the active PBIP / report / semantic model structure in this workspace.
- If multiple PBIP or report artifacts exist, identify them clearly before proceeding.
- If the request is ambiguous, ask a clarification question before editing.

Primary goal:
Understand the project structure, business intent, semantic model, and report logic before proposing changes.