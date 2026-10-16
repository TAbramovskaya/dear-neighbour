# Dear Neighbour — Retail Sales Analysis

## Project Overview

An annual performance review of **Dear Neighbour**, a grocery retail chain in Russia, comparing sales performance in 2025 with the previous year.

The project uses two complete consecutive years of data (2024 and 2025) to evaluate business performance, identify potential areas of concern, and explore opportunities for improvement.

## Dataset

The dataset covers 22,790 transactions across stores in nine Russian cities over two full calendar years. Transaction records contain detailed product-level information, including quantities sold, selling prices, discounts, and payment methods. Products are organized into 14 categories. Approximately ??% of receipts do not contain a customer ID, as these purchases were made without a loyalty card.

<details>
<summary>View dataset details</summary>

The project includes the following datasets:

- **Sales transactions:** transaction dates, stores, products, customers, quantities, prices, discounts, and sales amounts.
- **Products:** product names, brands, categories, subcategories, purchase costs, retail prices, and suppliers.
- **Stores:** store names, formats, cities, regions, floor areas, and opening dates.
- **Customers:** customer demographics, age groups, and loyalty card registration dates.
- **Suppliers:** supplier names, locations, and supply profiles.

</details>

## Analysis Process

The source data was provided in XLSX format, with column names and values in Russian.

1. **Data preparation and translation:** Python was used to inspect, prepare, and translate the source data into English. The code and workflow are available in the [Jupyter notebook](data/data_overview.ipynb).
2**Metric development:** Key performance indicators were calculated in Power BI using DAX, including revenue, gross profit, gross margin, transaction count, and units sold.
3**Dashboard development:** An interactive Power BI report was created to compare annual performance, investigate changes across product categories and cities, and explore customer and loyalty program behavior.

## Business Objectives

The objective was to assess how the business performed in 2025 compared with 2024.

Since no business targets or budgets were provided, the analysis focuses on descriptive performance comparisons rather than target achievement. The goal is to identify emerging trends, potential weaknesses, and areas that may require further investigation.

Key questions include:

- How did revenue, gross profit, transaction count, and units sold change year over year?
- Which product categories and cities contributed most to the observed changes?
- How do purchasing patterns differ between loyalty and non-loyalty customers?
- What potential opportunities exist to improve profitability and loyalty program performance?

## Key Findings

### Overall Business Performance

The comparison of 2025 with 2024 shows an overall positive sales trend, with growth across the main business indicators.

However, gross margin declined slightly, despite the overall positive performance. The average margin change across the comparisons examined was approximately −0.11 percentage points.

### Potential Drivers of Margin Decline

The analysis suggests that changes in the product sales mix may be one possible explanation for the margin decline. If lower-margin categories account for a growing share of revenue, overall gross margin can decrease even when total revenue and gross profit increase.

This remains a hypothesis to validate through a more detailed breakdown of category-level margins, revenue shares, discounts, and purchase costs.

### Business Implications

The findings highlight the importance of monitoring profitability alongside sales growth. Further investigation into category performance and product mix could help identify opportunities to improve margins without compromising revenue growth or customer retention.

## Dashboard

The Power BI report contains two pages:

- **Sales Overview:** annual performance, monthly trends, product category comparisons, profitability, and city-level margin changes.
- **Customers & Loyalty:** customer behavior, loyalty versus non-loyalty purchasing patterns, and loyalty program indicators.

## Limitations

- The analysis covers only 2024 and 2025; longer-term trends cannot be established from these two years alone.
- No budgets, sales targets, or external benchmarks were provided.
- Customer-level analysis is limited by purchases made without loyalty cards.
- Gross profit and gross margin estimates depend on the available product purchase costs. If these are current costs rather than historical costs, the results may not reflect actual cost changes between 2024 and 2025.
- Observed relationships between product mix and margin changes do not, on their own, establish causation.

## Conclusion

The project provides an interactive overview of Dear Neighbour's retail performance in 2025 compared with 2024. While the overall sales trend is positive, the slight decline in gross margin highlights an area for further investigation.

The dashboard is designed to help stakeholders move beyond headline sales growth and examine the factors that may influence profitability, product performance, and customer loyalty.
