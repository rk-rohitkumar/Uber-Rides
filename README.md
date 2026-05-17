# Project Overview

## Purpose
This Power BI report shows analysis of UBER rides in Delhi NCR region during the year 2024, adhering to strict data integrity and single-page consolidation rules.

## Data Sources & Pipeline
1. **Raw Data:** Extracted from CSV files located in `DataSource/` (e.g., `ncr_ride_bookings.csv`, Location data).
2. **Semantic Model:** The report is built upon the structured semantic model found in `PBIP/Uber Rides.SemanticModel/`. This model links Fact tables (`Rides`) to Dimension tables (`Locations`).
3. **Report Visuals:** Visualizations are defined by JSON files located in `PBIP/Uber Rides.Report/definition/pages/*/visuals/`.

## Data Model Details
- **Fact Table:** `Rides` (Transactional data).
- **Dimension Table:** `Locations` (Geographical details).

## Key Measures & Report Logic
The report relies on measures defined within the semantic model, which are directly linked to the following calculations:
- **Total Bookings:** `DISTINCTCOUNT(Rides[Booking ID])`
- **Booking Value:** `SUM('Rides'[Booking Value])`
- **Top Region Name:** Calculated measure identifying the region with the highest total booking value across all records.
- **Completion Rate:** Calculated based on status filtering within the Fact table.

## Business Rules & Constraints
