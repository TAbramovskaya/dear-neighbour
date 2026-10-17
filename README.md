# Dear Neighbour — Retail Sales Analysis

## Project Overview

An annual performance review of **Dear Neighbour**, a grocery retail chain in Russia, comparing sales performance in 2025 with the previous year.

The project uses two complete consecutive years of data (2024 and 2025) to evaluate business performance, identify potential areas of concern, and explore opportunities for improvement.

## Dataset

The dataset covers 22,790 transactions across stores in nine Russian cities over two full calendar years. Transaction records contain detailed product-level information, including quantities sold, selling prices, discounts, and payment methods. Products are organized into 14 categories. Approximately 45% of receipts do not contain a customer ID, as these purchases were made without a loyalty card.

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

1. **Data preparation and translation:** Python was used to inspect, prepare, and translate the source data into English. The code and workflow are available in the [Jupyter notebook](python/data_overview.ipynb).
2. **Metric development:** Key performance indicators were calculated in Power BI using DAX.
3. **Dashboard development:** An interactive Power BI report was created to compare annual performance, investigate changes across product categories and cities, and explore customer and loyalty program behavior.

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

The comparison of 2025 with 2024 shows an overall positive sales trend, with growth across the main business indicators. However, several potential areas of concern emerged from the analysis.

- Gross margin declined from Q2 onward. The decline appears across the remaining quarters, although its magnitude varies.
- Monthly gross profit follows a pattern similar to the previous year but trends downward toward year-end. The decline is particularly noticeable in the final months of the year.
- Several of the highest-gross-profit products show relatively weak growth in units sold. This highlights a potential area for further investigation into product-level performance.

### Potential Drivers of Margin Decline

The high-margin categories are not consistently leading volume growth, which may contribute to the overall margin decline if lower-margin categories are gaining a larger share of sales. The highest-margin category ranks 11th out of 14 in unit sales change (+6.44%), while the other top-margin categories rank between 4th and 10th.

## Limitations

First, the dataset appears to be synthetic and insufficiently realistic. All loyalty program registrations occurred no later than the end of 2023, and no newly registered loyalty members made purchases during the two-year period under review (2024–2025). In addition, the average daily number of customer visits per store is fewer than two. 

Second, product purchase costs are provided in the product table rather than as historical transaction-level costs. As a result, COGS for 2024 and 2025 must be calculated using the same available cost values. At the same time, the average selling prices of individual products appear to fluctuate only slightly throughout two year period. This provides some context for interpreting the sales trends, but it does not resolve the limitation related to historical purchase costs.

The observed decline in gross margin is relatively small (approximately 0.11 percentage points on average). Given the limited fluctuations in selling prices and sales volumes, as well as the limitations of the synthetic dataset, this change may reflect random variation in the generated data rather than a meaningful underlying business trend.