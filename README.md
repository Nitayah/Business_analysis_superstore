# Business_analysis_superstore

## Project Overview
This project explores the Superstore dataset to identify sales temporal and geographical patterns, loss drivers, and opportunities for improvement. Using Tableau, I created interactive dashboards that highlight trends across time, product categories, and geographies. The analysis is supported by data validation and calculated fields designed to surface actionable business insights.

## Main Insights
- Consumer-driven sales: Sales are primarily driven by the Consumer segment and strongly correlate with discount patterns. Targeted discount campaigns can help recover sales during low-activity periods.

- Losses from discounts: Several mid-performing states generate significant losses due to aggressive discounting. Chain-level intervention is required to enforce responsible discount policies.

- Unprofitable products: Specific sub-categories (e.g., Tables) contain products that are consistently unprofitable. These items should either be discounted more carefully or removed from the inventory.

## Data Cleaning
The dataset was reviewed to ensure reliable analysis. All columns had correct data types, and no missing or invalid values were identified.
Checks for negative or zero values in Sales and Quantity returned none. Potential data-entry errors were investigated by recalculating the True Price (see below) and reviewing extreme values by product; no anomalies were found. The dataset was therefore used as provided, with additional calculated fields created for analysis.

## Calculated Fields
True Price – product price before discount: [Sales] / (1 – [Discount])
Product Price Tier – classifies products as:
Commodity if True Price < $50
Premium if True Price > $200
Standard otherwise
is_profitable – flags transactions as profitable if [Profit] > 0, else unprofitable
State Focus – highlights highly profitable or unprofitable states where ABS([Profit]) exceeds a threshold defined by the Profit Threshold parameter
