# Semantic Model Measure Reference

This file serves as the definitive reference for all calculated measures used in the Power BI report, derived from the semantic model definition (`_Calculations.tmdl`).

## Core Transactional Metrics (Volume & Value)

| Measure Name | Formula | Business Definition | Purpose/Notes |
| :--- | :--- | :--- | :--- |
| **Total Bookings** | `DISTINCTCOUNT(Rides[Booking ID])` | The distinct count of all booking IDs recorded in the dataset. | Primary measure for tracking volume regardless of completion status. |
| **Total Booking Value** | `SUM('Rides'[Booking Value])` | The sum of the monetary value of all bookings. | Represents total gross revenue potential. |
| **Completed Bookings** | `CALCULATE([Total Bookings], 'Rides'[Booking Status] = "Completed")` | Count of bookings successfully completed by the user. | Core metric for measuring fulfilled demand. |
| **Non-Completed Bookings** | `CALCULATE([Total Bookings], 'Rides'[Booking Status] <> "Completed")` | Count of bookings that did not reach a 'Completed' status (e.g., cancelled, abandoned). | Used to quantify booking failure rate. |
| **Completed Bookings Value** | `CALCULATE([Total Booking Value], 'Rides'[Booking Status] = "Completed")` | The total revenue generated exclusively from completed trips. | Core metric for measuring realized revenue. |

## Efficiency & Rate KPIs (Calculated Ratios)

These measures provide insights into service efficiency and customer behavior:

| Measure Name | Formula | Business Definition | Purpose/Notes |
| :--- | :--- | :--- | :--- |
| **Completion Rate** | `DIVIDE([Completed Bookings], [Total Bookings])` | Percentage of total bookings that were successfully completed. | Key KPI for overall service reliability and demand fulfillment. |
| **Non-Completion Rate** | `DIVIDE([Non-Completed Bookings], [Total Bookings])` | Percentage of total bookings that failed to complete. | Measures the proportion of lost or incomplete trips. |
| **Average Revenue per Completed Booking** | `DIVIDE([Total Booking Value], ([Total Bookings] - [Non-Completed Bookings]))` | The average revenue generated *per* trip counted as completed (or non-cancelled). | Provides a true picture of realized value, filtering out failed bookings. |
| **Avg Trips per Customer** | `DIVIDE([Total Bookings], CALCULATE(DISTINCTCOUNT('Rides'[Customer ID]), 'Rides'[Booking Status] = "Completed"))` | The average number of total bookings per unique customer who completed at least one trip. | Measures customer engagement frequency. |

## Financial Risk & Loss Metrics (Monetized Impact)

These measures quantify the monetary impact of non-completion:

| Measure Name | Formula | Business Definition | Purpose/Notes |
| :--- | :--- | :--- | :--- |
| **Potential Revenue Lost (Cancelled)** | `CALCULATE(SUM('Rides'[Booking Value]), 'Rides'[Booking Status] <> "Completed")` | Total monetary value of bookings that were cancelled or abandoned. | Measures the total gross revenue potentially lost due to poor experience or cancellation. |
| **Revenue Loss Ratio** | `DIVIDE([Potential Revenue Lost (Cancelled)], [Total Booking Value])` | The ratio of lost potential revenue against total booking value. | Critical KPI showing the percentage of revenue at risk. |

## Distance & Location Analysis

| Measure Name | Formula | Business Definition | Purpose/Notes |
| :--- | :--- | :--- | :--- |
| **Total Ride Distance (KM)** | `SUM(Rides[Ride Distance])` | The total accumulated distance of all recorded rides. | Basic volume metric for operational scale. |
| **Avg of Vehicle-Type Avg Ride Distance** | `AVERAGEX(SUMMARIZE(Rides, Rides[Vehicle Type]), CALCULATE(AVERAGE(Rides[Ride Distance])) )` | Calculates the average *of* the individual ride distance averages calculated for each unique vehicle type present in the data. | Measures typical operational scale segmented by service class. Requires careful interpretation due to nested averaging. |
| **Total Booking value by pick up location** | `CALCULATE([Total Booking Value], USERELATIONSHIP(Locations[LocationKey], Rides[Pickup.LocationKey]))` | Total booking revenue calculated specifically for trips starting at a designated pickup location. | Allows filtering and analysis based on the initial trip start point, respecting complex relationship filters. |

## Top N/Title Measures (Contextual KPIs)

| Measure Name | Formula | Business Definition | Purpose/Notes |
| :--- | :--- | :--- | :--- |
| **Top Region by booking value** | `TopByValue( Locations[Region], [Total Booking Value] )` | Identifies and returns the name of the region contributing the highest total booking value. | A dynamic title KPI for geographic performance tracking. |
| **title revenue loss ratio** | `FORMAT([Revenue Loss Ratio], "#0.0%") & " revenue lost due to cancellations"` | Formats the Revenue Loss Ratio into a user-friendly text string and appends descriptive context. | Used as a display measure (card/title) rather than a core calculation input. |

