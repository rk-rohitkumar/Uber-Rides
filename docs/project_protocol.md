# Project Analysis and Documentation Protocol

This protocol defines the required methodology for analyzing, documenting, and maintaining a Power BI semantic model project within the repository. Adherence to these steps ensures traceability and consistency.

## 🎯 PHASE I: Discovery & Mapping (The 'What' is there?)
1. **Inventory:** Use file listing tools (`ls`, `file_glob_search`) to map all key assets: Data Sources (CSV), Model Definitions (.tmdl), Report Visuals (.json), and Business Rules (docs/).
2. **Structural Mapping:** Immediately create a definitive schema document (e.g., `DataModel_Schema.md`). This must explicitly define the primary keys, foreign keys, and relationships between all Fact and Dimension tables.
3. **Measure Extraction:** Consolidate all measures into one canonical file (e.g., `Measures_Reference.md`), listing both the technical DAX formula AND the clear business definition for every KPI.

## 🔄 PHASE II: Validation & Cross-Referencing (The 'How' does it work?)
1. **Traceability Check:** Verify that every measure in `Measures_Reference.md` can be traced back to a specific column calculation defined within the respective `.tmdl` file (using the `Model_TMDL_Index.md`).
2. **Rule Enforcement Audit:** Cross-reference all proposed changes and current report visuals against the established business rules in `docs/business-rules.md`. Flag any deviation immediately.
3. **Data Flow Diagramming:** Create a master document (e.g., `Project_Protocol.md`) that maps the path: **Raw Source $\rightarrow$ Transformation Logic $\rightarrow$ Semantic Table $\rightarrow$ Final KPI.**

## 📄 PHASE III: Documentation & Optimization (The 'How do we write about it?')
1. **Visual Dictionary:** Create a `Visual_Dictionary.md` to centralize all reports visuals, linking the JSON file path to the business objective and the exact measures used.
2. **Protocol Summary Update:** The `README.md` must be updated last, serving as the high-level summary that points the end-user to the Protocol, Schema Map, Measure Reference, and Visual Dictionary. It should never contain low-level technical details itself.
3. **Review Cycle:** When proposing changes, always ask: 'Does this change affect the Single-Page Consolidation rule or any established data relationship?' This keeps the focus on constraints first.
