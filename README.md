<h1>Tata Data Visualization - Empowering Business with Effective Insights</h1>

<h2>Table of Contents</h2>

- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools](#tools)
- [Data Planning and Design](#data-planning-and-design)
- [Data Cleaning and Shaping](#data-cleaning-and-shaping)
- [Data Modelling](#data-modelling)
- [Data Visualization](#data-visualization)
- [Results](#results)
- [Recommendations](#recommendations)

<br />

<h2>Project Overview</h2>

<b>Objective:</b> Develop an interactive Power BI dashboard to provide key insights into an online retail store’s sales and marketing performance. The dashboard will assist the CEO and CMO in strategic decision-making by identifying revenue drivers, highlighting areas of success, and supporting data-driven expansion strategies. This analysis aims to maximize growth opportunities and improve forecasting based on operational and demographic trends.

<br />

Key Areas of Analysis:

✔ Time Series Analysis – Identify revenue trends over time and detect seasonal patterns.

✔ Regional Demand Insights – Visualize product demand across countries and regions.

✔ Customer Segmentation – Identify high-value customers and analyze their purchasing behavior.

✔ Sales Performance Comparison – Compare revenue and quantity sold across top-performing countries.

<br />

KPIs Tracked:

📌 Total Revenue – Overall revenue generated from sales.

📌 Total Customers – Unique customers who made purchases.

📌 Average Order Value (AOV) – Revenue per transaction.

📌 Top Revenue-Generating Countries – Highest contributing markets (excluding the UK).

📌 Top Customers by Revenue – Identification of high-value customers.

<br />

<h2>Data Sources</h2>

<br />

Sales Data:
- File Name: <i>OnlineRetailData.xlsx</i>
- Fields: InvoiceNo, StockCode, Description, Quantity, InvoiceDate, UnitPrice, CustomerID, Country

<br />

<h2>Tools</h2>

- <b>Excel</b> 
- <b>Power Query</b>
- <b>Power BI</b>
<br />

<h2>Data Planning and Design</h2>

<br />
To answer the four main business questions (see Requirements Document), the following visuals have been chosen:
<br />

- Line Charts:
   - Purpose: Display monthly revenue trends for 2011 to highlight seasonal patterns.
   - Data: Date (X-axis) → Monthly, Daily, Hourly vs. Total Revenue (Y-axis).
 
- Clustered Column Charts:
   - Purpose: Compare the Top 10 revenue-generating countries (excluding the United Kingdom) and analyze both the revenue and quantity sold.
   - Data: Country (X-axis) vs. Quantity and Revenue (Y-axis).

- Column Charts:
   - Purpose: Rank the Top 10 customers in descending order by revenue to identify high-value customers.
   - Data: Customers (X-axis) vs. Revenue (Y-axis).

- Map Charts:
   - Purpose: Visualize demand for products across various regions (excluding the United Kingdom) to support expansion strategy.
   - Metrics: Demand indicators (quantity ordered), represented through bubble size.
 
- Filters:
   - Date: Range selection (e.g. monthly, daily, hourly)
   - Region: List of countries
   - Product: List of products by stock code
   - Customer: Drop-down selection of customer ID's

<br />
The mock-ups provided in the following section illustrate the layout and functionality of these visuals, demonstrating how each one will support the strategic decision-making process for the CEO and CMO.
<br />
<br />

Initial Report Layout / Mock-up Sketch: 
<br />

![image](https://github.com/user-attachments/assets/6d70b02d-583e-454f-9867-68b8a5dc09b1)

<br />

After initial feedback, adjustments were made as follows:
- Drill-down capabilities added to line chart to enable additional daily and hourly insights.
- Filters removed (too many fields) and replaced with KPI cards to track trends of key metrics (total revenue, total customers, aveage order value)
<br />

Final Report Layout
<br />

![image](https://github.com/user-attachments/assets/4454cbd2-ced9-425b-86d9-be4c40923439)
<br />
<br />

<h2>Data Cleaning and Shaping</h2>
<br />

<b>A structured data cleaning process was applied to improve data accuracy and consistency:</b>

- Removing Duplicates: N/A
- Handling missing values: N/A
- Handling Anomylous Values:
   - Created a filter to ensure the quantity is not below 1 unit (unit prices which were input in error)
   - Created a filter to ensure the unit price is not below $0 (some returns to the store which are provided in negative quantities)
- Standardizing Data Formats:
   - Ensured all date fields were in  ‘mm/dd/yyyy hh:mm:ss’ format for uniform analysis.
   - Ensured numerical fields, such as 'UnitPrice' and 'Revenue', were correctly formatted as decimal values to maintain consistency in calculations.
- Feature engineering:
   - Extract Day of the Week: A new column was created to extract the day of the week from the ‘InvoiceDate’ to capture daily patterns.
   - Extract Time of the Day: A new column was added to categorize the ‘InvoiceDate’ into ‘Time of day’ to capture time-based patterns.
<br />

<b>Loading Data into Power BI:</b>
<br />

Once cleaned and transformed, the dataset was loaded into Power BI’s data model for further analysis and visualization.
<br />
<br />


<b>Data Quality Checks</b>
To verify data integrity, the following validation steps were performed:
- Record Consistency Check: Compared the total number of records between the source file and the Power BI dataset to ensure no data loss during extraction.
- Aggregate Validation: Cross-checked key metrics, such as total sales revenue and total transaction count in Excel different formulas and functions, to confirm alignment with expected figures.
<br />

This structured ETL process ensured that the dataset was accurate, clean, and ready for meaningful analysis in Power BI.


<br />

<h2>Data Modelling</h2>
<br />

<b>DAX Measures Development</b>
<br />

As part of the data transformation process, key performance indicators (KPIs) were calculated using DAX measures to provide valuable insights for analysis. The following measures were developed:

- <b>Total Sales Revenue:</b> A DAX measure was created to calculate the total revenue generated across all sales transactions. This measure sums up the Revenue, which was calculated as the product of 'UnitPrice' and 'Quantity' ordered. The total sales revenue is a critical metric for understanding overall business performance.

- <b>Average Order Value (AOV):</b> To gain insights into customer purchasing behavior, a DAX measure for Average Order Value (AOV) was developed. This measure divides the Total 'Revenue' by the distinct count of 'InvoiceNo' (representing unique orders). AOV helps evaluate the average spend per transaction and is useful for identifying trends in customer spending.
<br />

<h2>Data Visualization</h2>
<br />

Following the data cleaning and transformation steps, the next phase of the project focuses on creating interactive data visualizations. The goal of these visualizations is to provide a clear and intuitive way to analyze key business metrics, uncover trends, and support data-driven decision-making. Visualizations play a crucial role in conveying complex information in an easily digestible format, enabling stakeholders to quickly identify patterns and insights.
<br />

The following visuals were developed for the report, each tailored to address the specific business questions outlined earlier in the project:

- <b>Time Series Revenue Analysis:</b> To observe trends and seasonal patterns in revenue over time.
- <b>Top Revenue Countries:</b> To compare the highest revenue-generating countries, alongside the quantity of products sold.
- <b>Top Customers by Revenue:</b> To identify high-value customers based on their revenue contribution.
- <b>Regional Demand Insights:</b> To provide a visual representation of demand across different regions, helping to inform potential expansion strategies.
<br />

![image](https://github.com/user-attachments/assets/3bbb7511-38bc-433d-8881-be8bb3067408)
<br />


<h2>Results</h2>
<br />

The following insights were derived from the Power BI dashboard visualizations, focusing on revenue trends, customer behavior, and regional demand patterns.

<b>1. Monthly Revenue Trends</b>
- The monthly revenue trends for the year 2011 reveal significant fluctuations throughout the year, with February representing the lowest revenue month at 0.52 million, and November showing the highest revenue at 1.51 million.
- The data suggests a notable seasonality in revenue, as outlined below:
   - From January to May, the revenue fluctuates between 0.5 million and 0.7 million, with no clear upward or downward trend.
   - From May to August, revenue stabilizes around 0.7 million for four consecutive months.
   - After August, a sharp increase in revenue is observed, with a jump from 0.7 million in August to 1.51 million in November.
   - Following November, revenue declines slightly to approximately 0.6 million in December.
<br />

<b>2. Top 10 Customers by Revenue</b>
<br />

The top 10 customers have been successfully identified based on their revenue contribution, providing clear visibility into the high-value clients. No significant patterns were observed in terms of customer grouping or segmentation, other than the overall contribution to the store's revenue.
<br />
<br />

<b>3. Top 10 Countries by Revenue</b>
<br />

The top 10 countries by revenue have been identified as:

- Netherlands
- EIRE
- Germany
- France
- Australia
- Sweden
- Switzerland
- Spain
- Belgium
- Norway
<br />

The visual shows that while revenue is consistently higher than quantity ordered, a noteworthy observation is the close alignment between revenue and quantity ordered for Sweden. In contrast to countries like Switzerland, where revenue (R56k) is significantly higher than quantity (R30k), Sweden’s quantity (R32k) and revenue (R35k) are very close, suggesting that the products ordered in Sweden may not be of high value. This could indicate that Sweden is placing a high volume of orders, but these orders might consist of lower-priced products compared to countries like Switzerland, where the higher quantity of orders (R30k) leads to a significantly higher revenue (R56k). These insights could inform future marketing or pricing strategies.
<br />
<br />

<b>4. Regional Demand Insights</b>
<br />

The regional demand visual highlights that the highest demand for products is concentrated in Western Europe, with Australia also showing notable demand. 
<br />
<br />

<b>5. Key Performance Indicators (KPIs)</b>
<br />

The KPI cards on the dashboard provide an at-a-glance view of the following metrics:

- Total Revenue: Provides an overall view of the business's performance across the selected period.
- Total Customers: Indicates the customer base size.
- Average Order Value (AOV): Offers insights into the average spending per order, helping to evaluate customer purchasing behavior.

<br />

<h2>Recommendations</h2>
<br />

<b>1. Leverage seasonal trends for strategic planning</b>
<br />

Revenue shows a sharp increase from August to November, likely driven by demand leading up to the festive season. This pattern suggests an opportunity to maximize sales during this peak period:
- Increase marketing efforts ahead of peak months by launching targeted holiday campaigns, promotions, and email marketig to capture  early shoppers.
- Ensure sufficient inventory and opertaional readiness to accomodate higher order volumes and prevent stock shortages.
- Optomize fulfilment and logistics to handle increased demand efficinetly, ensuring timely deliveries during the holiday season.
<br />

<b>2. Strengthen customer retention strategies</b>
<br />

The Top 10 customers contribute significantly to total revenue, making retention a priority:
- Develop loyalty programs or exclusive incentives to maintian engagement and encourage repeat purchases.
- Implement targeted outreach strategies based on purchase history to reinforce brand loyalty and drive additional sales.

Alternatively, diversifying the customer base and exploring :
<br />
<br />

<b>3. Optomize pricing and produt strategy in Sweden</b>
<br />

Sweden exhibits a close alignment between revenue and quantity sold, which differs from other high-performing regions. This suggests a high sales volume but lower-value purchases:
- Assess product mix and pricing strategy to identify opportunities for higher-margin sales.
- Introduce premium product offering or upselling strategies to increase revenue per transaction.
<br />

<b>4. Expand market focus on high-demand regions</b>
<br />

The demand highlights strong sales performance in Western Europe and Australia:
- Consider expanding the product offerings or increasing the marketing budget in these regions, where demand is strong.
- Tailor the customer experience in these regions by offering region-specific customer support, localized payment methods, and regionally relevant products.
- While Western Europe and Australia show strong demand, exploring new high-potential regions could provide new growth opportunities.
<br />
