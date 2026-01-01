
# Transaction And Customer Concentration Analysis For Risk‑Aware Decision Making
This project analyzes e-commerce transaction and customer data to identify where revenue and activity are concentrated across customers, products, and time. By identifying high-impact segments, the business can prioritize monitoring, optimize risk controls, and make data-driven decisions to protect revenue and ensure operational resilience.

&nbsp;
&nbsp;

## Data & ETL Process

The project follows a structured Extract-Transform-Load (ETL) pipeline to turn raw sales, customer, and product data into reliable insights.

### Extract
- Sales Data: Loaded sales_data.csv (3,294 rows) containing user-product interactions (purchase, view, like) and timestamps.
- Customer Details: Loaded customer_details.csv (3,900 rows) including demographics, purchase history, and payment methods.
- Product Details: Loaded product_details.csv (10,002 rows) including pricing, brand names, and categories.
### Transform
1. Data Cleaning:
- Removed an unnecessary Unnamed: 4 column and eliminated empty trailing rows.
- Dropped 128 rows with missing Interaction type to ensure all analyzed activity was valid.

2. Date Parsing: Converted the Time stamp column to a proper datetime format, covering a range from December 2022 to December 2023.

3. Feature Engineering:
- Time-Based Features: Extracted year, month, day of the week, and hour for time-based concentration analysis.
- Customer Segmentation: Used pd.qcut to group customers into four spending tiers based on their purchase amounts: Low, Medium, High, and VIP.
- Age Grouping: Categorized users into brackets (e.g., 18-25, 35-50, 50-65) to identify demographic activity clusters.

### Load
All processed data was consolidated into a cleaned sales_df (2,871 valid interactions) which serves as the primary source for all visualizations and risk metrics.

&nbsp;
&nbsp;

## Key Findings
1. **Customer Concentration:** 
- Revenue at a Glance: The total analyzed revenue is $233,081.00.
- VIP Segment: High-impact customers are those in the "VIP" segment, spending between $82.00 and $100.00.
- Demographic Risk: The 35-50 and 50-65 age groups represent the largest portions of the customer base (over 1,100 customers each), indicating where marketing and risk monitoring should be most active.


2. **Product & Operational Insights:** 
- Subscription Activity: Only 1,053 of the 3,900 customers are active subscribers, highlighting a significant opportunity for loyalty-driven risk mitigation.
- Time Concentration: Patterns were identified across days of the week and hours of the day to pinpoint "peak risk" windows where transaction volumes are highest.

&nbsp;
&nbsp;

# Conclusion
By focusing on high-impact customer segments (VIPs and core age demographics) and identifying critical time periods, this project provides a roadmap for Risk-Aware Decision Making. Focusing monitoring and controls on these concentrated segments helps the business protect its most valuable revenue streams while ensuring operational efficiency.

