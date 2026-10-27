# Dear Neighbour — Retail Sales Analysis

## Project Overview

An annual performance review of **Dear Neighbour**, a grocery retail chain in Russia, comparing sales performance in 2025 with the previous year.

Using two complete consecutive years of data (2024 and 2025), the project evaluates business performance, identifies potential areas of concern, and investigates the factors behind changes in sales and profitability.

## Dataset

The source data was provided in XLSX format, with column names and values in Russian. Python was used to inspect, prepare, and translate the data into English. The translation process is documented in the [translation notebook](python/translate_workbook.ipynb). No additional data cleaning or transformation was required. The [data overview notebook](python/data_overview.ipynb) documents the initial examination of the dataset, including its structure, contents, and key characteristics.

The [dataset](data/dear_neighbour.xlsx) covers 22,790 transactions (unique receipts) across stores in nine Russian cities over two full calendar years. Approximately 45% of receipts do not contain a customer ID, as these purchases were made without a loyalty card. Products are organized into a two-level hierarchy of 14 categories and 49 subcategories.

<details>
<summary>View dataset details</summary>

The dataset consists of five tables:

- **Sales transactions (`fact_sales`):** transaction IDs, transaction dates and times, store, product and customer IDs, quantities sold, unit prices, discount percentages, line totals, and payment methods.
- **Products (`dim_products`):** product IDs, names, brands, categories, subcategories, purchase and retail prices in RUB, and supplier IDs.
- **Stores (`dim_stores`):** store IDs, names, formats, cities, regions, floor areas in square meters, and opening dates.
- **Customers (`dim_customers`):** customer IDs, names, gender, age, age groups, residential regions, and loyalty card registration dates.
- **Suppliers (`dim_suppliers`):** supplier IDs, names, cities, and supply profiles.

</details>

### Business Objectives

The objective was to assess how the business performed in 2025 compared with 2024.

Since no business targets or budgets were provided, the analysis focuses on descriptive performance comparisons rather than target achievement. The goal is to identify emerging trends, potential weaknesses, and areas that may require further investigation.

### Metrics and Initial Findings

Key performance indicators were calculated in Power BI using DAX.

The initial analysis revealed an important contrast: overall sales and other key business metrics increased in 2025, while the gross margin declined. This raised two main questions: what was driving the growth in sales, and what was causing profitability to decline despite the positive overall performance?

### Limitations

**Synthetic data and customer activity.** The dataset appears to be synthetic and insufficiently realistic. All loyalty program registrations occurred no later than the end of 2023, and no newly registered loyalty members made purchases during the two-year period under review (2024–2025). In addition, the average daily number of customer visits per store is fewer than two. 

**Historical product costs.** Product purchase costs are provided in the product table rather than as historical transaction-level costs. As a result, COGS for 2024 and 2025 must be calculated using the same available cost values. At the same time, the average selling prices of individual products appear to fluctuate only slightly throughout two year period. However, this does not tell us whether purchase costs also remained stable.

**Interpreting the gross margin decline.** Annual gross margin remains above 26%, and the year-over-year decline of approximately 0.11 percentage points is small in comparison. Given the synthetic nature of the dataset, this change is more likely to reflect random variation in the generated data than a meaningful underlying business trend. Nevertheless, it is still worth investigating where the decline originates within the available data, particularly whether it is associated with changes in the sales mix or in margins within individual product categories.

### Exploratory Analysis

To investigate these questions in greater detail, additional analyses were conducted in Python.

- [Sales drivers analysis](python/sales_drivers.ipynb) explores year-over-year changes in sales performance, profitability, pricing, discounting, product mix, and customer purchasing patterns to identify the main drivers of sales growth.
- [Margin decline analysis](python/margin_decline_analysis.ipynb) examines whether the decline in gross margin is primarily associated with changes in the sales mix or with changes in margins within individual product categories.

### Key Findings

**Sales growth was accompanied by more transactions and units sold.** Revenue, gross profit, transaction count, and units sold all increased in 2025 compared with 2024. Year-on-year growth across product subcategories was generally positive for revenue, transaction count, and units sold, while changes in revenue per unit and average subcategory value per receipt remained relatively small. Overall, the results suggest that sales growth was associated with higher transaction volume and more units sold, rather than substantial increases in revenue per unit or average spending on products from individual subcategories.

**The gross margin decline was small, with sales mix playing the larger role in most categories.** Annual gross margin decreased slightly, from 26.37% in 2024 to 26.26% in 2025 — a decline of 0.11 percentage points. The category-level decomposition suggests that changes in sales mix had a greater effect on the overall margin change than changes in gross margin within individual categories for most categories. These findings should be interpreted in the context of the synthetic dataset and its limitations, particularly the use of the same available product cost values for both years.

### Dashboard Development

The findings were brought together in an [interactive Power BI dashboard](https://github.com/TAbramovskaya/dear-neighbour/blob/main/viz/Dear%20Neighbour%20Sales.pbix) designed to present the overall business performance while highlighting the less obvious patterns uncovered during the analysis.


I divided the dashboard into two pages, each focusing on a different aspect of the business.

**Sales Overview** provides a high-level view of key performance indicators and overall trends, with a closer look at changes in gross margin. 

![](https://github.com/TAbramovskaya/dear-neighbour/blob/main/viz/dashboard_sales_overview.png)

It also allows users to explore performance by city, which is useful because growth in 2025 was limited in some locations and the overall figures do not tell the whole story.

**Products and Discounts** focuses on monthly changes in average transaction value and transaction volume, as well as differences in gross profit and discount levels across product subcategories. 

![](https://github.com/TAbramovskaya/dear-neighbour/blob/main/viz/dashboard_products_and_discounts.png)

The bar charts show the 15 subcategories with the highest gross profit, ranked in descending order, alongside the share of gross profit accounted for by discounts. Keeping the subcategories in the same order makes it easier to compare their gross profit with the relative scale of discounts.
