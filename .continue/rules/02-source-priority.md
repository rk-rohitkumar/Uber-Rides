# Source priority

Use sources in this order of authority:

1. PBIP / PBIR / report / semantic model files in the repository
2. Repository documentation under docs/
3. Root README and project markdown files
4. Existing comments, annotations, and naming conventions in model/report files
5. User instructions in the current chat

Rules:
- Prefer repository facts over assumptions.
- If documentation conflicts with PBIP or semantic model files, treat the files as the current implementation and flag the documentation for update.
- If documentation is missing, infer cautiously from the actual project files and explicitly label the inference.
- Do not invent business rules that are not supported by the repo contents or the user.