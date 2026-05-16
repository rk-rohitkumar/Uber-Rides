# Project Overview

## Purpose
This Power BI report shows analysis of UBER rides in Delhi NCR region during the year 2024.

## Data Sources
- Source 1 – Uber ride data downloaded from the internet.
- Source 2 – location details downloaded from the internet.

## Report Pages
- Main – Main page to view all analysis.


## Model Notes
- Fact table - Rides.
- Dimension - Locations
- Main Measures - 
    - '# Total Bookings = DISTINCTCOUNT(Rides[Booking ID])'
    - '$ Booking value = 

	SUM('Rides'[Booking Value])'
    - '# Bookings not Completed = 
CALCULATE(
	[# Total Bookings],
	'Rides'[Booking Status] <>  "Completed" 
)'
    - 'Average revenue for completed rides'  

