
# Transaction And Customer Concentration Analysis For Risk‑Aware Decision Making
This project analyzes transaction and customer data to identify where revenue and activity are concentrated across customers, products, and time. The main goal is to help the business or risk team understand which segments, categories, and periods are most important, so they can prioritize monitoring and controls in those areas.

## Data & ETL Process

This project follows a simple ETL (Extract–Transform–Load) flow to turn raw ecommerce interaction data into clean, reliable inputs for concentration analysis.

### Extract
- Loaded the raw sales interaction file (`sales_data.csv`) into Python using **pandas**.
- The source contained user–product interactions (views, likes, purchases) with timestamps and an extra unnamed column from the export.

### Transform
- Inspected shape, column names, and data types to understand the schema and detect issues such as float `user id` and `object` timestamps.
- Parsed the **Time stamp** column from string to proper `datetime` using a fixed format (`%d/%m/%Y %H:%M`) and `errors="coerce"` to safely handle malformed values.
- Identified rows where *all* columns were missing (for example, trailing blank rows) and removed them with `dropna(how="all")` so they do not distort counts or time ranges.
- Verified interaction types (view, like, purchase) and the overall date range to ensure the final dataset covers a consistent period for analysis.

### Load
- Used the cleaned dataframe as the **single** source for:
  - Customer‑level concentration (which users drive most interactions and purchases).
  - Product‑level concentration.
  - Time‑based patterns (days and hours with the highest activity).
- All metrics, tables, and visualizations in the notebooks are built from this cleaned dataset to keep results consistent and reproducible.

## Findings
- **Customer Segments:** Identifying which customer groups bring in the most revenue and are the most active, so they can be closely monitored.
- **Product Categories:** Determining which products generate the highest revenue and are most popular, guiding inventory and marketing strategies.
- **Time Periods:** Revealing when revenue is concentrated (such as certain months, days, or hours), highlighting periods that need extra risk management.
- **Payment Methods and Purchase Patterns:** Showing which payment methods and purchase frequencies contribute the most to revenue, supporting operational decisions.

# Conclusion
By focusing on these high-impact segments and critical periods, the project helps the business protect revenue, manage risks, and ensure resilience. The findings guide targeted marketing, inventory management, and proactive risk mitigation, making the business more effective and secure.

