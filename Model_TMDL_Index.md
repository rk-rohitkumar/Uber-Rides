# Uber Rides Semantic Model Index

This index maps the semantic model definitions (TMDL files) to their corresponding report metrics and visuals.

## Fact & Dimension Definitions
- **Rides Table:** Mapped to `PBIP/Uber Rides.SemanticModel/definition/tables/Rides.tmdl`
  - Derives core facts like Total Bookings, Booking Value.
- **Locations Table:** Mapped to `PBIP/Uber Rides.SemanticModel/definition/tables/Locations.tmdl`
  - Provides geographical context for ride analysis.

## Derived Measures Reference
See **_Calculations.tmdl**  `PBIP/Uber Rides.SemanticModel/definition/tables/_Calculations.tmdl` for the full list of calculated KPIs and their exact DAX definitions.

## Report Visual Mapping
Visuals are linked to specific JSON files found in the report definition path (e.g., `PBIP/Uber Rides.Report/definition/pages/*/visuals/*visual.json`).
