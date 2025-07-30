# USA Regional Sales Analysis - Acme Co. (2014–2018)

## Project Overview
This project involves an Exploratory Data Analysis (EDA) of Acme Co.'s sales data from 2014 to 2018, focusing on revenue and profit drivers across products, channels, and regions. The analysis uncovers seasonal trends, outliers, and performance against budgets to inform pricing, promotion, and market expansion strategies. The insights derived are intended to support the development of a Power BI dashboard for strategic decision-making and sustainable growth.

---

## Problem Statement
The goal is to analyze Acme Co.’s 2014–2018 sales data to:
- Identify key revenue and profit drivers across products, channels, and regions.
- Uncover seasonal trends and anomalies for optimized planning.
- Detect pricing and margin risks from outlier transactions.
- Provide actionable insights for pricing, promotions, and market expansion to reduce concentration risk and drive sustainable growth.

---

## Objectives
- **Identify Top Performers:** Highlight top-performing products, channels, and regions driving revenue and profit.
- **Uncover Trends:** Detect seasonal patterns and anomalies to optimize planning.
- **Spot Risks:** Identify pricing and margin risks from outlier transactions.
- **Strategic Guidance:** Inform pricing, promotion, and market expansion strategies.
- **Dashboard Preparation:** Provide insights and aggregated data for a Power BI dashboard to support decision-making.

---

## Dataset Description
The dataset is sourced from an Excel workbook (`Regional Sales Summary.xlsx`) containing six sheets:
1. **Sales Orders** (`df_sales`): 64,104 rows, 12 columns (e.g., OrderNumber, OrderDate, Customer Name Index, Channel, Unit Price, Line Total).
2. **Customers** (`df_customers`): 175 rows, 2 columns (customer details).
3. **Products** (`df_products`): 30 rows, 2 columns (product details).
4. **Regions** (`df_regions`): 994 rows, 15 columns (regional details, including coordinates).
5. **State Regions** (`df_state_reg`): 49 rows, 3 columns (state-to-region mappings).
6. **2017 Budgets** (`df_budgets`): 30 rows, 2 columns (budget data for 2017).

The analysis merges these datasets to create a comprehensive DataFrame for deeper insights, exported as `Sales_data(EDA Exported).csv`.

---

## Methodology
The EDA was conducted using Python in a Jupyter Notebook (`EDA_Regional_Sales_Analysis.ipynb`) with the following steps:
1. **Data Ingestion & Cleaning**:
   - Loaded all sheets from the Excel file using pandas.
   - Verified schema, handled missing budget values, and corrected data types.
   - Merged datasets to create a unified DataFrame with additional derived columns (e.g., profit, profit margin, month, year-month).
2. **Univariate & Bivariate Analysis**:
   - Analyzed distributions of revenue, profit margins, and unit prices.
   - Examined sales by product, channel, region, and customer segments.
3. **Trend & Seasonality Analysis**:
   - Charted monthly and yearly sales patterns to identify recurring surges and dips.
4. **Outlier Detection**:
   - Identified extreme transactions in revenue and unit prices using statistical methods.
5. **Correlation & Segmentation**:
   - Assessed relationships between key metrics (e.g., revenue vs. profit margin).
   - Clustered customers based on revenue and profit margin.

Libraries used: `pandas`, `numpy`, `matplotlib`, `seaborn`.

---

## Key Findings

### 1. Revenue Trends
- **Stability with Anomalies**: Monthly revenue is stable between $23M and $26.5M from 2014 to 2017, with a notable dip to $21.2M in early 2017, suggesting a one-time disruption (e.g., supply chain issues or market event) that warrants further investigation.
- **No Consistent Seasonality**: While slight volume increases occur in May–June, no strong monthly seasonal pattern is evident.

### 2. Channel Performance
- **Channel Mix**:
  - **Wholesale**: 54% of total revenue, the dominant channel.
  - **Distributors**: 31% of revenue, indicating a strong domestic presence.
  - **Exports**: 15% of revenue, suggesting untapped potential for international expansion.

### 3. Product Performance
- **Top Products by Revenue**:
  - **Product 26**: $118M
  - **Product 25**: $110M
  - **Product 13**: $78M
- **Mid-Tier Products**: Generate $68M–$75M.
- **Low-Tier Products**: Generate $52M–$57M, indicating potential for pricing or cost optimization.
- **Profit Margins**: Vary widely from 18% to 60%, with no strong correlation to unit price, suggesting standardized pricing tiers.

### 4. Regional Performance
- **Top Regions**:
  - **California**: Leads with ~$230M in revenue and over 7,500 orders.
  - **Illinois, Florida, Texas**: Each contribute ~$85M–$110M with 3,500–4,500 orders.
  - **New York, Indiana**: Contribute ~$54M with over 2,000 orders.
- **Geographic Insights**: Revenue is concentrated in key states, with California as a major hub, suggesting strong market penetration in the West.

### 5. Outliers & Risks
- **Extreme Transactions**: Identified outliers in revenue and unit prices, likely due to bulk orders or promotional SKUs. These skew averages and should be excluded or formalized in analyses.
- **Profit Margin Variability**: Wide margin range indicates potential pricing inconsistencies or cost inefficiencies in certain products or channels.

### 6. Customer Segmentation
- Customers were clustered by revenue and profit margin, revealing distinct segments:
  - **High-Revenue, High-Margin**: Key accounts to retain and expand.
  - **Low-Revenue, Low-Margin**: Candidates for cost optimization or strategic review.

---

## Recommendations
Based on the findings, the following strategies are proposed to optimize Acme Co.'s performance:

1. **Outlier Management**:
   - Exclude or formalize bulk-order and promotional SKUs when calculating performance metrics to ensure accurate averages.
   - Investigate extreme transactions to understand their drivers (e.g., discounts, special contracts).

2. **Profit Margin Optimization**:
   - Apply pricing strategies from top-performing products (e.g., Product 26, Product 25) to mid- and low-tier products to boost margins.
   - Conduct a cost analysis on low-margin products to identify cost-cutting opportunities.

3. **Export Market Expansion**:
   - Invest in targeted marketing and partnerships with international distributors to grow the export channel (currently 15% of revenue).
   - Explore high-potential regions based on existing export data.

4. **Seasonal Strategy**:
   - Shift promotional budgets to January to counter the revenue trough and capitalize on the May–June volume uptick.
   - Investigate the early 2017 revenue dip ($21.2M) to identify causes (e.g., operational issues, market conditions) and prevent recurrence.

5. **Power BI Dashboard Development**:
   - Build aggregated tables for:
     - Time series analysis (monthly/yearly revenue and volume).
     - Channel performance (revenue and order counts by channel).
     - Product performance (revenue, margin, and order volume).
     - Regional performance (revenue and orders by state/region).
   - Include filters for time periods, channels, products, and regions to enable dynamic insights.

6. **Concentration Risk Reduction**:
   - Diversify revenue sources by expanding into underperforming regions and scaling the export channel to reduce reliance on Wholesale (54%) and key states like California.

---

## Dashboard Preparation
To support the Power BI dashboard, the following aggregated tables are recommended:
- **Time Series Table**: Monthly and yearly revenue, order volume, and profit margins.
- **Channel Performance Table**: Revenue, order count, and margin by channel (Wholesale, Distributor, Export).
- **Product Performance Table**: Revenue, margin, and order volume by product.
- **Regional Performance Table**: Revenue, order count, and key metrics by state/region.
- **Customer Segmentation Table**: Revenue and margin by customer cluster.

The exported CSV (`Sales_data(EDA Exported).csv`) contains the merged and cleaned dataset, ready for import into Power BI.

---

## Limitations
- **2017 Budget Data**: Limited to one year, restricting budget performance analysis.
- **Early 2017 Dip**: Cause unknown; requires further operational or market data.
- **Outlier Impact**: Bulk orders and promotions skew some metrics, necessitating careful filtering.
- **Geographic Granularity**: State-level data is robust, but finer regional insights (e.g., city-level) are limited.

---

## Future Work
- **Investigate 2017 Dip**: Analyze external factors (e.g., supply chain, competition) or internal issues (e.g., inventory shortages) causing the early 2017 revenue drop.
- **Expand Budget Analysis**: Incorporate budget data for other years to assess performance trends.
- **Customer-Level Insights**: Deepen customer segmentation with additional metrics (e.g., order frequency, lifetime value).
- **Predictive Modeling**: Use machine learning to forecast sales trends and optimize pricing strategies.
- **International Expansion**: Conduct a market analysis to identify high-potential export regions.

---

## Conclusion
The EDA reveals stable revenue with opportunities for growth in the export channel and mid/low-tier products. California dominates regional performance, while Products 26, 25, and 13 drive significant revenue. The lack of strong seasonality suggests flexibility in promotional timing, but the early 2017 dip requires investigation. These insights, combined with the recommended Power BI dashboard, will enable Acme Co. to optimize pricing, expand markets, and reduce concentration risks for sustainable growth.