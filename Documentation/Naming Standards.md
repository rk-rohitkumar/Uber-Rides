# Power BI Naming Standard

## Purpose
This document defines a consistent naming standard for measures and other semantic model elements in Power BI. The goal is to improve readability, maintainability, self-service usability, and alignment across reports and datasets.

## Core principles
- Use business-friendly names visible to report authors and consumers.
- Use Title Case for all exposed model objects.
- Prefer clear business terms over technical abbreviations unless the abbreviation is widely understood, such as KPI, ID, or YTD.
- Put units in parentheses when needed, for example `(KM)`, `(Minutes)`, `(INR)`.
- Make the aggregation explicit when it improves clarity, for example `Total`, `Avg`, `Min`, `Max`, or `Distinct`.
- Use names that describe the business meaning, not just the DAX implementation.
- Keep naming consistent across facts, dimensions, measures, hierarchies, and display folders.

## Measures
### Standard pattern
Use one of these patterns depending on the measure type:
- `Total <Business Term>`
- `Avg <Business Term>`
- `<Business Term> %`
- `<Business Term> Rate`
- `<Business Term> Count`
- `<Business Term> per <Entity>`
- `<Business Term> (Unit)`

### Measure rules
- Count measures: prefer `Total Bookings`, `Customer Count`, `Active Riders`.
- Distinct count measures: use `Distinct` only when needed, for example `Distinct Customers`.
- Amount measures: use `Total Revenue`, `Total Booking Value`, `Avg Fare`.
- Percentage measures: place `%` at the end, for example `Non-Completed Bookings %`.
- Rates: use `Rate` only for ratios with business meaning, for example `Non-Completion Rate`.
- Time intelligence: use suffixes such as `YTD`, `MTD`, `QTD`, `PY`, `YoY %` consistently, for example `Total Revenue YTD`.
- Units: append units in parentheses only when the unit is not obvious from the business term.
- Avoid ambiguous adjectives such as `Current`, `Final`, `Value`, or `Number` unless they have a well-defined business meaning.


## Columns
### Column rules
- Use Title Case and business-friendly terms.
- Keep column names singular where possible, for example `Booking ID`, `Vehicle Type`, `Ride Distance`.
- Do not repeat the table name in the column name unless required for business clarity.
- Use `Date`, `Year`, `Month`, `Quarter`, `Month Number` consistently in date tables.
- Use IDs only for technical or relationship fields, not for report labels.
- Boolean columns should read clearly as Yes/No or true/false concepts, for example `Is Completed`, `Is Cancelled`, `Is Active`.

## Tables
### Table rules
- Fact tables: use business nouns in plural if they store transactions, for example `Rides`, `Bookings`, `Payments`.
- Dimension tables: use singular business nouns or a `Dim` prefix if that standard is already used, for example `Customer` or `Dim Customer`.
- Bridge tables: use `Bridge` or a clear business name, for example `Bridge Customer Region`.
- Measure tables: use a clear presentation name such as `Measures` or a domain-specific name like `Ride KPIs`; avoid technical names with leading underscores unless they are intentionally hidden from users.
- Staging or technical tables should be hidden and clearly marked if they remain in the model.

## Hierarchies
### Hierarchy rules
- Name hierarchies by navigation path, for example `Date Hierarchy`, `Geography Hierarchy`, `Vehicle Hierarchy`.
- Avoid generic names such as `Hierarchy 1`.
- Use consistent level names inside hierarchies, for example `Year > Quarter > Month > Date`.

## Display folders
### Folder rules
- Group measures by business domain, not by DAX function.
- Good examples: `Bookings`, `Revenue`, `Operations`, `Customer`, `Time Intelligence`.
- Avoid folders such as `Calculated`, `Misc`, or `New Folder`.
- Use a maximum of one or two folder levels to keep navigation simple.

## KPIs and calculation items
### KPI rules
- KPI base measure and KPI rate should be clearly linked, for example `Total Revenue` and `Revenue Growth %`.
- Status or target measures should include their role, for example `Revenue Target`, `Revenue Variance`, `Revenue Variance %`.

### Calculation group items
- Use concise business labels, for example `Current Period`, `Previous Year`, `YTD`, `YoY %`.
- Keep naming parallel across all calculation items in a group.

## Formatting alignment
- Naming and formatting should support each other.
- Currency measures should not rely on `$` in the name when model formatting already defines the currency.
- Percentage measures should use a percentage name and percentage format string.
- Unit-based measures should use both a clear name and the correct numeric format.

