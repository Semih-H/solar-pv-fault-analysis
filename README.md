# Solar PV Inverter Fault Detection & Yield Loss Analysis

## Project Overview
This project analyzes solar photovoltaic (PV) generation and weather sensor data to automatically detect inverter outages (zero-generation faults) during daylight hours. It quantifies the resulting energy loss and visualizes the hardware failures to assist Operations & Maintenance (O&M) teams in prioritizing repairs.

## Methodology
1. **Data Ingestion & Cleaning:** Merged generation logs with weather sensor data using an inner join to ensure synchronized timestamps. Resolved frequency mismatches and localized date formats.
2. **Fault Detection Logic:** Engineered a boolean flag to isolate intervals where solar irradiance was sufficient (> 0.1 kW/m²) but AC power output was exactly 0W.
3. **Yield Loss Quantification:** Calculated a dynamic baseline using the average production of healthy inverters at the exact fault timestamp. Converted lost wattage into kilowatt-hours (kWh).
4. **Visualization:** Built a Power BI dashboard utilizing custom DAX measures, conditional formatting (heatmaps), and rank-ordered bar charts to pinpoint the most problematic inverters.

## Key Findings
* Identified 9 specific inverters experiencing daylight zero-generation faults over a 34-day period.
* Total uncaptured energy yield due to these specific faults amounted to 15.62 kWh (scaled data).
* Simultaneous failures across multiple inverters (e.g., on June 14th) suggest broader string-level or grid overvoltage issues rather than isolated hardware degradation.

## Tech Stack
* **Python:** Pandas (Data manipulation), Matplotlib (Time-series visualization)
* **Power BI:** Power Query (Transformations), DAX (Measure calculation), Dashboard Design
