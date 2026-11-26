# E-Commerce Sales Analysis – Power BI

## Project Overview
This project involves transforming, merging, aggregating, and modeling e-commerce sales data using Power BI. Power Query Editor was used to clean and prepare the datasets, create calculated columns, and generate aggregated tables for analysis.

## Tools Used
- Power BI Desktop
- Power Query Editor

## Dataset
Three CSV files were used:
- **List of Orders:** Customer information, order IDs, order dates, city, and state.
- **Order Details:** Order IDs, product categories, sub-categories, quantity, amount, and profit.
- **Sales Target:** Monthly sales targets for different product categories.

## Tasks Performed

### 1. Data Transformation

Used Power Query Editor to perform the following transformations:

- **Row Filtering:** Restricted the List of Orders table to the first 500 rows using Keep Top Rows.
- **Date Formatting:** Changed the Order Date column to Date data type using Change Type with Locale to ensure correct date interpretation.
- **Numeric Formatting:** Converted Amount and Target columns to Fixed Decimal Number.
- **Text Formatting:** Applied Proper Case transformation to the CustomerName column to standardize capitalization.
- **Column Merging:** Selected State and City columns and used Merge Columns with a comma and space separator to create a new Location column in the format City, State.
- **Custom Column:** Created Profit Margin using the Custom Column feature by dividing Profit by Amount.
- **Conditional Column:** Created Profit Status using conditional rules:
  - Profit less than 0 → Loss
  - Profit equal to 0 → Break-Even
  - Profit greater than 0 → Profit

### 2. Data Merging

Used Merge Queries to combine List of Orders and Order Details:

- Selected Order ID as the matching column in both tables.
- Used a Left Outer join to retain all records from List of Orders and match corresponding records from Order Details.
- Expanded the required columns from the merged table.
- Named the resulting table Orders Data.

### 3. Missing and Duplicate Data

- Checked the datasets for missing values using Power Query's column quality and data profiling features. No missing values were found.

### 4. Sorting and Filtering

- Sorted Order Date in descending order to bring the most recent orders to the top.
- Used column filters to focus on specific states, such as Tamil Nadu, for regional analysis.

### 5. Grouping and Aggregation

Used Reference to create new queries from the original tables. Applied Group By in Power Query to perform the required aggregations.

| Referenced Table | Grouping and Aggregation |
|---|---|
| Avg_profit_per_Category | Grouped by Category and calculated the average of Profit as Average_profit. |
| Count_of_Orders_per_id | Grouped by Order ID and calculated the row count as Count. |
| TotalAmount_by_subcat | Grouped by Sub-Category and calculated the sum of Amount as Total_Amount. |
| TargetByMonth | Grouped by Month of Order Date and calculated the sum of Target as TotalTargetAmountByMonth. |

### 6. Data Modeling

Created relationships between the original tables in Model View:

- Connected List of Orders and Order Details using Order ID, establishing a One-to-Many relationship.
- Connected Order Details and Sales target using Category, selecting the cardinality based on the uniqueness of category values.
- Ensured the relationships were active.

## Final Tables

The completed model contains eight tables:

1. List of Orders
2. Order Details
3. Sales target
4. Orders Data
5. Avg_profit_per_Category
6. Count_of_Orders_per_id
7. TotalAmount_by_subcat
8. TargetByMonth

## Key Concepts Practiced
- Power Query data transformation
- Data type conversion and text standardization
- Custom and conditional columns
- Merge Queries and joins
- Reference Queries
- Grouping and aggregation
- Sorting and filtering
- Data modeling and relationships

## Outcome

Prepared structured e-commerce datasets through Power Query transformations, combined related data using joins, generated summary tables through grouping and aggregation, and established relationships between the original datasets in Power BI.
