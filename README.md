📊 Sales Data Analysis Project (Excel)
📌 Project Overview

This project demonstrates end-to-end data analysis using Microsoft Excel, including data cleaning, preparation, scenario modeling (What-If analysis), and dashboard storytelling. The analysis focuses on revenue, profitability, service levels, pricing compliance, and performance across regions, products, channels, and salespersons.

📁 Dataset Description

The dataset contains transactional sales records with fields such as:

OrderDate, RequiredDate

Region, Country, City

ProductCategory, SKU

Salesperson, Channel

UnitPrice, UnitCost, Quantity, DiscountPct

⚠️ Data Issues Identified

During initial data exploration, the following data quality issues were found:

Duplicate records: Exact duplicate rows existed for some orders.

Missing values: City, Salesperson, and Channel fields had null values.

Incorrect data types: Date fields were stored as text; numeric fields contained text values.

Suspicious values:

Negative UnitPrice values.

DiscountPct values exceeding reasonable business limits (>30%).

Date inconsistencies: Some RequiredDate values were earlier than OrderDate.

🧹 Data Cleaning Rules Applied

To address the issues above, the following cleaning rules were implemented:

Duplicate removal:
Exact duplicates were removed using a composite key of OrderID + SKU + OrderDate + Quantity.

Data type correction:

Date fields converted to proper Date format.

Numeric fields converted to number format.

Missing value handling:

City → filled with "Unknown City"

Salesperson → filled with "Unassigned"

Channel → filled with "Unknown Channel"

Suspicious value treatment:

Negative UnitPrice values were flagged and set to blank for review.

DiscountPct values above 30% were capped at 30%.

Date correction rule:
If RequiredDate < OrderDate, RequiredDate was adjusted to:
OrderDate + 7 days.

Derived fields added:

LeadTimeDays = RequiredDate − OrderDate

GrossRevenue, CostOfGoods, GrossProfit, MarginPct

Month, Quarter, and PriceBand dimensions

All cleaning steps were documented and applied in a dedicated Staging Table.

📐 Key Assumptions

The following assumptions were made to support analysis consistency:

Missing City, Salesperson, or Channel values indicate incomplete capture, not missing transactions.

A maximum discount of 30% represents acceptable business practice.

A 7-day lead time is considered the service level target.

Quantity uplift, cost inflation, and discount caps used in scenario modeling are hypothetical and used for decision simulation only.

GrossRevenue is calculated after applying discounts.

MarginPct is set to zero where revenue is zero to avoid division errors.

🔄 Scenario Modeling (What-If)

A What-If control panel was created to simulate:

Global Discount Cap (0%–25%)

Unit Cost Inflation (0%–15%)

Quantity Uplift (0%–20%)

Scenario-adjusted revenue and profit metrics were recalculated dynamically and compared against baseline values.

📊 Outputs

Cleaned and enriched Staging Table

Cohort analysis, ABC classification, and productivity analysis

Scenario modeling and comparison metrics

Interactive Excel dashboard with slicers and KPIs

Business insights derived from dashboard analysis

🛠 Tools Used

Microsoft Excel (PivotTables, formulas, What-If analysis)

GitHub (version control and documentation)

✍️ Author

Joy Langat
Aspiring Data Analyst | Business Intelligence & Analytics
📌 GitHub portfolio project
