# Business Rules and Constraints

**Core Rule:** The primary constraint for the final report design is **Single-Page Consolidation**.

1.  **Page Limit:** The entire dashboard must fit on a single scrollable page.
2.  **KPI Focus:** Only essential KPIs (e.g., Total Bookings, Average Revenue, Completion Rate) are permitted on this primary view.
3.  **Visual Density:** Visualizations must be highly dense and information-rich to maximize space efficiency.
4.  **Data Source Integrity:** All metrics must be derived directly from the defined Fact and Dimension tables in the data model.

**Semantic Model Integrity Rules:**
To maintain data integrity, the following rules apply to the semantic model:
1. **Fact/Dimension Linking:** All relationships between the `Rides` Fact table and the `Locations` Dimension table must be correctly established (One-to-Many).
2. **Metric Source Traceability:** Every measure defined in the semantic model (`.../definition/*.tmdl`) must trace its calculation back directly to an explicit column aggregation within the Fact or Dimension tables.
3. **Data Derivation:** No complex cross-table calculations should be performed outside of the defined relationships unless explicitly documented in a dedicated Data Profile.

**Report Visual Integrity:**
Visualizations (defined in `PBIP/Uber Rides.Report/definition/pages/*/visuals/*.json`) must only utilize measures derived from the core semantic model to ensure consistency.

