# Semantic Model Measure Reference

This file serves as the definitive reference for all calculated measures used in the Power BI report.

## Core Metrics (Derived from TMDL Definitions)
- **Total Bookings:** `DISTINCTCOUNT(Rides[Booking ID])`
- **Total Booking Value:** `SUM('Rides'[Booking Value])`
- **Non-Completed Bookings:** `CALCULATE([Total Bookings], 'Rides'[Booking Status] <> "Completed")`
- **Non-Completion Rate:** `DIVIDE([Non-Completed Bookings], [Total Bookings])`
- **Completed Bookings:** `CALCULATE([Total Bookings], 'Rides'[Booking Status] = "Completed")`
- **Completion Rate:** `DIVIDE([Completed Bookings], [Total Bookings])`
- **Completed Booking Value:** `CALCULATE([Total Booking Value], 'Rides'[Booking Status] = "Completed")`
- **Avg Revenue per Completed Booking:** `DIVIDE([Total Booking Value], ([Total Bookings] - [Non-Completed Bookings]))`
- **Total Ride Distance (KM):** `SUM(Rides[Ride Distance])`
- **Avg of Vehicle-Type Avg Ride Distance:** `AVERAGEX(SUMMARIZE(Rides, Rides[Vehicle Type]), CALCULATE(AVERAGE(Rides[Ride Distance])))`
- **Total Booking value by pick up location:** `CALCULATE([Total Booking Value], USERELATIONSHIP(Locations[LocationKey], Rides[Pickup.LocationKey]))`

## Top Region Name (Global KPI)

**Business Definition:** Calculates the name of the single region that generated the highest cumulative booking value across all historical records in the dataset, regardless of any filters applied to the report page.

**DAX Formula:**
