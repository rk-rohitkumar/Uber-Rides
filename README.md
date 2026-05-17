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
The report utilizes a comprehensive set of advanced metrics defined in the semantic model, covering volume, financial performance, efficiency rates, and operational analysis.

Key categories include:
- **Volume & Core Metrics:** Total Bookings, Completed/Non-Completed Booking counts, Unique Customers.
- **Financial Performance:** Total Booking Value, Potential Revenue Lost (Cancelled), Completion Rate, etc.
- **Efficiency Analysis:** Advanced KPIs like Average Revenue per Completed Booking and Avg Trips per Customer.
- **Geographic Insights:** Metrics for identifying top regions by value or volume.

For a detailed breakdown of all calculations, formulas, and business definitions, please refer to `docs/Measures_Reference.md`.

## Business Rules & Constraints
