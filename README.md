# Company Sales & Customer Analytics Dashboard | Power BI

An interactive Power BI business intelligence project built to analyze company sales, revenue, profit, orders, product performance, returns, territories and customer behaviour across 2020 to June 2022.

The report is built around a sales dataset and supporting lookup tables. It includes an executive dashboard, geographic sales view, product drill-through page, customer insights page and a hidden custom tooltip page.

## Project objectives

- Monitor overall business performance through revenue, profit, orders and return KPIs.
- Analyze sales trends over time.
- Compare product categories and product-level performance.
- Explore sales distribution across countries, regions and continents.
- Understand customer value and customer segments.
- Track performance against revenue, order and profit targets.
- Enable interactive filtering, drill-through and tooltip-based exploration.

## Technology and Power BI features

- **Business Intelligence:** Microsoft Power BI Desktop
- **Data preparation:** Power Query / data transformation
- **Data modeling:** Relational model using sales facts and lookup dimensions
- **Calculations:** DAX measures and time-based calculations
- **Visualizations:** KPI cards, line chart, clustered bar chart, matrix/pivot-style table, map, area chart, gauges, donut charts and tables
- **Interactivity:** Slicers, drill-through, bookmarks, custom tooltips, field/metric selection and visual interactions

## Data sources

The uploaded source files contain the following datasets:

| File | Rows | Purpose |
|---|---:|---|
| `Company Sales Data 2020.csv` | 2,630 | 2020 sales transactions |
| `Company Sales Data 2021.csv` | 23,935 | 2021 sales transactions |
| `Company Sales Data 2022.csv` | 29,481 | 2022 sales transactions through June 30 |
| `Company Returns Data.csv` | 1,809 | Product returns by return date, territory and product |
| `Company Customer Lookup.csv` | 18,154 | Customer demographic and profile attributes |
| `Company Product Lookup.csv` | 293 | Product details, costs and prices |
| `Company Product Subcategories Lookup.csv` | 37 | Product subcategories and category keys |
| `Company Product Categories Lookup.csv` | 4 | Product category names |
| `Company Territory Lookup.csv` | 10 | Region, country and continent mapping |
| `Company Calendar Lookup.csv` | 912 | Calendar date dimension |
| `Product Category Sales (Unpivot Demo) (1).csv` | 20 | Separate category-by-region dataset suitable for demonstrating unpivot transformation |

The three annual sales files contain **56,046 transaction rows** in total, with **84,174 units** and **25,164 distinct order numbers** across the combined files. The sales period runs from January 1, 2020 to June 30, 2022. The returns file contains 1,809 rows and 1,828 returned units.

The customer and product lookup files include some missing values. Data-quality checks and appropriate treatment of missing values should be considered when refreshing or extending the model.

## Report pages and functionality

### 1. Executive Dashboard (`Exec Dash`)

The executive page provides a high-level overview of business performance, including:

- KPI cards for Total Revenue, Total Profit, Total Orders and Return Rate.
- Revenue trend over time with year, quarter, month and week date hierarchy fields.
- Orders by product category.
- Product-level comparison table showing Total Revenue, Total Orders and Total Profit.
- KPI visuals comparing current revenue, orders and returns with previous-month values.
- Top product subcategory by return rate.
- Year and continent slicers.
- Bookmark-driven slicer panel controls.

### 2. Geographic Sales (`Map`)

- Map visualization showing Total Orders by Country.
- Continent slicer for geographic filtering.

### 3. Product Details (`Product Details`)

This page is configured as a product drill-through page, with Product Name as the drill-through field.

It includes:

- Selected product context.
- Order trend over time.
- Revenue gauge against a revenue target.
- Orders gauge against an order target.
- Profit gauge against a profit target.
- Product metric selection control.

### 4. Customer Details (`Customer Details`)

The customer page supports customer-level analysis and includes:

- Total Customers.
- Average Revenue Per Customer.
- Customer revenue trend over time.
- Orders by income level.
- Orders by occupation.
- Customer table with Customer Key, Full Name, Total Orders and Total Revenue.
- Customer-level detail cards.
- Year slicer and customer metric selection.
- Customer-focused interactions and filter controls.

### 5. Custom Tooltip (`Custom ToolTip`)

A hidden tooltip page provides contextual KPI cards and an order trend visual for use as a report tooltip.

## Data model

The report references these model entities in its visuals:

- Sales transaction data (2020, 2021 and 2022)
- Returns Data
- Customer Lookup
- Product Lookup
- Product Subcategories Lookup
- Product Categories Lookup
- Territory Lookup
- Calendar Lookup
- Table Measure
- Product Metric Selection
- Customer Metric Solution

The report uses customer, product, category, territory and calendar attributes to analyze sales and returns. The exact relationship cardinalities, filter directions and DAX formula definitions should be verified in Model view and the measure editor in Power BI Desktop before documenting them in detail.

## Key measures visible in the report

The report references the following measures:

- Total Revenue
- Total Profit
- Total Orders
- Total Returns
- Return Rate
- Previous Month Revenue
- Previous Month Orders
- Previous Month Returns
- Target Revenue
- Revenue Target Gap
- Order Target
- Order Target Gap
- Profit Target
- Profit Target Gap
- Average Revenue Per Customer
- Total Customers
- Customer detail measures

The PBIX report also references metric-selection fields for product and customer analysis. The measure names above are taken from the report visuals; their exact DAX definitions are not reproduced here.

## Suggested repository structure

```text
company-sales-customer-analytics/
│
├── PowerBI/
│   └── AkshayMor_Assignment9.pbix
│
├── Data/
│   ├── Company Sales Data 2020.csv
│   ├── Company Sales Data 2021.csv
│   ├── Company Sales Data 2022.csv
│   ├── Company Returns Data.csv
│   ├── Company Customer Lookup.csv
│   ├── Company Product Lookup.csv
│   ├── Company Product Subcategories Lookup.csv
│   ├── Company Product Categories Lookup.csv
│   ├── Company Territory Lookup.csv
│   ├── Company Calendar Lookup.csv
│   └── Product Category Sales (Unpivot Demo) (1).csv
│
├── Screenshots/
└── README.md
```

Adjust the folder and file names to match the repository you actually publish. Check data licensing and privacy before uploading source datasets. Do not publish confidential customer information or personal data unless you have permission and an appropriate legal basis. If the data is not cleared for public sharing, provide a small sanitized sample or describe how to obtain it.

## How to use

1. Install Microsoft Power BI Desktop.
2. Clone or download this repository.
3. Open `PowerBI/AkshayMor_Assignment9.pbix` in Power BI Desktop.
4. If Power BI requests data sources, update the file paths in **Transform data → Data source settings** or in Power Query to point to the local `Data` folder.
5. Refresh the data.
6. Explore the report pages and use slicers, drill-through, bookmarks and metric selectors.

## Business questions explored

- How are revenue, profit, order volume and returns changing over time?
- Which product categories and products contribute most to sales?
- Which products or subcategories have higher return rates?
- How are orders distributed across countries and continents?
- How does revenue vary across customers and customer segments?
- How does performance compare with defined revenue, order and profit targets?

## Limitations and validation notes

- The sales data for 2022 ends on June 30, 2022; it is a partial year and should not be compared with full years without accounting for the different periods.
- The PBIX file shows report-level visuals and measure names. Exact DAX formulas and relationship settings should be checked in Power BI Desktop before describing their implementation.
- The separate `Product Category Sales (Unpivot Demo) (1).csv` file is not evidenced as a source for the main report visuals; treat it as a transformation practice dataset unless confirmed in Power Query.
- Customer Lookup has missing values and two duplicate rows in the supplied CSV. Product Lookup has missing values in ProductColor. Validate the treatment of these records in Power Query.
- Return Rate and target calculations should be validated against their DAX definitions and business rules before presenting numerical conclusions.

## Resume-ready project summary

Built an interactive Power BI sales and customer analytics dashboard using multi-year sales, returns and lookup datasets. Developed executive KPIs, time-based trends, product and geographic analysis, customer segmentation, target gauges, drill-through navigation, bookmarks and custom tooltips to support business performance monitoring.

## Disclaimer

This is a portfolio/business intelligence project based on the supplied datasets. Insights and metrics depend on the data quality, model relationships, DAX definitions and business assumptions used in the PBIX file.
