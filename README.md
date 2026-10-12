# High Clouds Airlines – Data Analysis Dashboard

## Project Overview
The **High Clouds Airlines** project analyzes airline operations and passenger demand using flight data. The goal is to prepare the data, calculate key date and operational metrics, and build an interactive dashboard that helps explore passenger load factor, carrier preferences, popular routes, weekday/weekend activity, and flight distance groups.

## Project Objectives
- Prepare a usable date field from the year, month, and day columns.
- Create calendar and financial date attributes for time-based analysis.
- Calculate passenger **Load Factor (%)** over time and by carrier.
- Identify the top 10 carriers based on transported passengers.
- Find the busiest routes based on the number of flights.
- Compare load factor on weekdays versus weekends.
- Analyze the number of flights by distance group.
- Present the findings in an interactive dashboard.

## Files Included
- `Questinaires high Clouds (1).xlsx` – Project brief/questionnaire describing the analysis requirements.
- `airline_maindata (1).sql` – MySQL SQL dump containing the `maindata` table structure and data statements.
- `HighClouds.zip` – Supporting data package, including the main data workbook and lookup/dimension files such as airlines, carrier groups, aircraft types/groups, distance groups, flight types, and airport market information.

> File names may retain their original spelling from the supplied project archive.

## Tools and Technologies
- **Microsoft Excel** – Data review and lookup/reference tables.
- **MySQL** – Database storage and SQL-based data access (optional workflow).
- **Power BI** – Data transformation, calculations, visualizations, and dashboard development.

## Key Metrics
### Load Factor
Load Factor measures how much of the available passenger seating capacity was used.

`Load Factor (%) = (Transported Passengers / Available Seats) × 100`

Use appropriate aggregation for the selected reporting level. For example, calculate the ratio of total transported passengers to total available seats rather than taking an unweighted average of row-level percentages.

### Flight Count
Count flight records or use the appropriate flight/departure measure consistently. For operational analysis, confirm whether the report should use scheduled departures or performed departures.

### Passenger Preference by Carrier
Rank carrier names by total transported passengers and display the top 10.

## Date Table / Date Attributes
Create a date from the `Year`, `Month (#)`, and `Day` fields, then derive:
- Year
- Month number
- Month name
- Quarter (Q1–Q4)
- Year-Month (YYYY-MMM)
- Weekday number
- Weekday name
- Financial month
- Financial quarter

**Note:** Confirm the financial-year start month expected by the project or organization before calculating financial month and financial quarter. If using an April–March financial year, document that assumption in the report.

## Suggested Dashboard Pages and Visuals
1. **Overview**
   - Total transported passengers
   - Total available seats
   - Total flights/departures
   - Overall load factor
2. **Time Analysis**
   - Monthly and quarterly load factor
   - Year-wise performance
3. **Carrier Analysis**
   - Top 10 carriers by transported passengers
   - Load factor by carrier
4. **Route Analysis**
   - Top routes by flight count, using From–To City
5. **Weekday vs Weekend**
   - Flight activity and load factor comparison
6. **Distance Analysis**
   - Flight count by distance group

Add slicers where useful, such as year, month, carrier, origin city, destination city, and distance group.

## Suggested Workflow
1. Extract the supplied ZIP archive.
2. Review the project questionnaire and source data files.
3. Load the main airline dataset into Excel or Power BI. Alternatively, import the SQL dump into MySQL if you want to use a database workflow.
4. Use the supplied dimension/lookup files to enrich the main dataset where relevant.
5. Set correct data types and handle blanks or invalid values.
6. Create the date field and the required calendar/financial attributes.
7. Build measures for transported passengers, available seats, flight count, and load factor.
8. Create the report visuals and validate the figures against the source data.
9. Publish or export the completed dashboard according to your portfolio requirements.

## Example Power BI Measures
Adjust table and column names to match the model in your Power BI file.

```DAX
Total Passengers =
SUM ( 'maindata'[# Transported Passengers] )

Available Seats =
SUM ( 'maindata'[# Available Seats] )

Load Factor % =
DIVIDE ( [Total Passengers], [Available Seats], 0 )
```

For a date table, create a proper relationship between the date column in the main table and the date table. Use the date table fields for time-based visuals.

## Data Notes
- The source includes carrier, airport/city, country/state, aircraft, distance, date, passenger, seat, and departure-related fields.
- Use the relevant lookup tables when adding descriptive labels to coded fields.
- Validate missing values, duplicate records, and the meaning of departure-related columns before interpreting results.
- Load factor can exceed 100% in some source datasets because of data quality, reporting conventions, or mismatched aggregation; investigate such cases rather than assuming they are correct.
- The supplied archive contains source data and a project brief. Include your completed `.pbix` file, screenshots, or exported report in the repository only if you have created them and are permitted to share them.

## Repository Structure
A suggested GitHub layout is:

```text
HighClouds-Airlines-Analysis/
├── README.md
├── data/
│   ├── main-data-file
│   └── dimension-and-lookup-files
├── sql/
│   └── airline_maindata.sql
├── report/
│   └── HighClouds_Dashboard.pbix
└── screenshots/
    └── dashboard-preview.png
```

This is a suggested structure; organize the files according to what you actually upload. Avoid uploading duplicate archives or very large raw datasets if repository size, licensing, or data-sharing rules prohibit it.

## How to Use
1. Clone or download this repository.
2. Extract the source files if they are stored in ZIP archives.
3. Open the Excel files or import the SQL dump into a compatible MySQL environment.
4. Open the Power BI report, if the completed `.pbix` file is included.
5. Refresh the data sources and review the dashboard filters and metrics.

## Project Status
**Source files and project requirements included.** Update this section once data preparation, analysis, and the dashboard are completed.

## Author
**Shashidhar Itha**

Data Analytics Project | Excel • SQL • Power BI
