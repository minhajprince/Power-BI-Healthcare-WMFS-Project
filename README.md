# 🚒 West Midlands Fire Service (WMFS) Incident Dashboard

**A Power BI dashboard that turns three years of West Midlands Fire Service incident records into clear answers about what happened, when, and where.**

## Dashboard Preview

![Incident Summary](dashboard%20summary%20image.png)

![Incident Summary by Location](dashboard%20image%202.png)

![Tooltip Page](dashboard%20tooltip%20data%20image.png)

## Project Overview

This project analyses incidents attended by the West Midlands Fire Service (WMFS) across seven districts: Birmingham, Coventry, Dudley, Sandwell, Solihull, Walsall, and Wolverhampton.

The dashboard helps a user quickly answer questions like:

- How many incidents happen each year, and which types are most common?
- Which months, hours, and weekdays are the busiest?
- Which districts and wards see the most incidents?
- Are incidents going up or down compared to last year?

## Key Insights

Based on **73,430 incidents from 2016 to 2018**:

| Metric | Result |
|---|---|
| Incidents per year | **24,856** (2016), **26,221** (2017), **22,353** (2018) |
| Change vs previous year | **+5.5%** in 2017, **-14.8%** in 2018 |
| Top incident type | **Outdoor Fire**, 18,202 (about 25%) |
| False alarms (all 3 kinds) | **25,303**, about **34%** of all incidents |
| Other big types | Property or Vehicle Fires (11,592), Special Service Calls (11,081), Road Traffic Collisions (7,159) |
| Busiest time | Summer afternoons and evenings (July peak on the time-of-day heatmap) |

> Note: 2018 is lower than 2016 and 2017 on the dashboard. Check that the 2018 file covers the same period as the other years before treating the -14.8% drop as a real decline.

## From Data to Dashboard

1. **Extract:** Downloaded the yearly incident CSV files from the [Birmingham City Observatory](https://www.cityobservatory.birmingham.gov.uk/explore/assets/wmfs-revised_incident_types/view/) public data portal.
2. **Combine:** Loaded the CSV files from one folder into Power BI and merged them into a single table (`WMF`) using Power Query's *Combine Files* (folder source + sample file function).
3. **Clean up in Power Query:**
   - Promoted headers and set the correct data type for all 33 columns (dates, whole numbers, text).
   - Filtered out the 2014 and 2018 rows from the combined folder table, since 2018 is loaded separately from its own file.
   - Replaced short codes with readable names, for example `CD` → *Chimney Fire in a Dwelling*, `FAE` → *False Alarm Equipment*, `SSC` → *Special Service Call*.
4. **Model:** Added relationships between the yearly incident tables and the `uk mapping` ward lookup (ward names with latitude and longitude), so one filter controls every chart.
5. **Measures with DAX:** Created measures for incident count, percentage of total, year-over-year change (variance), and average injuries and fatalities.
6. **Design:** Picked the theme colors from the WMFS logo, and used bookmark-style navigation icons from [icons8.com](https://icons8.com).

### Source Data

The combined data has 33 columns, including incident date and time, district, ward, incident type, property type, injuries, fatalities, fire cause, and place where the fire started.

![Data Source](dashboard%20data%20source%20image.png)

## Dashboard Features

The report has 3 pages:

| Page | What it shows |
|---|---|
| **Summary of Incident** | Incidents by year, monthly trend, incident types treemap, time-of-day heatmap, weekday curve, and a year-by-year variance table |
| **Incident category-Wise** | Slicers (incident type, district, ward, property type, place fire started), injury and fatality gauges, ward table with variance, and a district map |
| **ToolTip** | Hover page that shows incident counts by type for 2016, 2017, 2018, and total |

## Theme Colors

Colors come from the WMFS logo (red and green) and are listed in `wmf dashboard color codes.txt`.

| Use | Color |
|---|---|
| Main red | `#8B0F04` |
| Main green | `#004812` |
| Yellow accent | `#C7BA51` |
| Light green | `#9DFF64` |
| Gray | `#CCCCCC` |

## Files Included

| File | Description |
|---|---|
| `WMFS dashboard.pbix` | Completed Power BI dashboard |
| `wmfs-incidents-2017-2018-19.xlsx` | Combined incident data (49,169 rows) converted from CSV to Excel |
| `WMFS dashboard logo.png` | Logo used on the dashboard |
| `wmf dashboard color codes.txt` | Theme color codes |
| `dashboard summary image.png`, `dashboard image 2.png`, `dashboard tooltip data image.png`, `dashboard data source image.png` | Dashboard and data previews |
| `README.md` | Project information |

## How to Use

1. Download `WMFS dashboard.pbix`.
2. Open it with Power BI Desktop.
3. Use the slicers, the district map, and the left icons to explore the pages.

## Tools and Skills

- Power BI Desktop
- Power Query (combine files, data cleaning, type changes, value replacement)
- Data modelling and relationships
- DAX measures
- Dashboard design and branding
- Data storytelling

## Data Source

West Midlands Fire Service open data, published on the Birmingham City Observatory portal.

## Author

**Minhaj Khan**
Data Analyst | SQL · Power BI · Excel · Python · UI/UX designer

[LinkedIn](https://www.linkedin.com/in/minhaj-khan/) · [Portfolio](https://github.com/minhajprince)
