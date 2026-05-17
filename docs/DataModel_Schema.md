
## Fact Tables
- **Rides:** Contains all transactional ride data.
  - Key Columns: `Booking ID` (Primary Key), `Booking Value`, `Booking Status`.

## Dimension Tables
- **Locations:** Contains geographical information.
  - Key Columns: `Location ID` (Primary Key), `Latitude`, `Longitude`.

## Relationships
- The model is linked via the relationship between `Rides[Location ID]` and `Locations[Location ID]`.

## Key Measures & Report Logic
The report relies on measures defined within the semantic model, which are directly linked to the following calculations:
- **Total Bookings:** `DISTINCTCOUNT(Rides[Booking ID])`
- **Booking Value:** `SUM('Rides'[Booking Value])`
- **Top Region Name:** Calculated measure identifying the region with the highest total booking value across all records.
- **Completion Rate:** Calculated based on status filtering within the Fact table.
- **Hourly Analysis:** The model now supports hourly segmentation, allowing analysis of peak times and performance by time of day using the newly available `Hour` column.

## Business Rules & Constraints