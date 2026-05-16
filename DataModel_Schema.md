
This document defines the structure of the Power BI semantic model, linking Fact and Dimension tables.

## Fact Tables
- **Rides:** Contains all transactional ride data.
  - Key Columns: `Booking ID` (Primary Key), `Booking Value`, `Booking Status`.

## Dimension Tables
- **Locations:** Contains geographical information.
  - Key Columns: `Location ID` (Primary Key), `Latitude`, `Longitude`.

## Relationships
- The model is linked via the relationship between `Rides[Location ID]` and `Locations[Location ID]`.
