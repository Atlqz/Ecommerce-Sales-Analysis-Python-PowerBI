## Data Dictionary

# Data Dictionary: Superstore E-Commerce Dataset

| Column Name | Data Type | Description |
|-------------|-----------|-------------|
| `Row ID` | int | Unique row identifier |
| `Order ID` | string | Unique order identifier |
| `Order Date` | date | Date the order was placed |
| `Ship Date` | date | Date the order was shipped |
| `Ship Mode` | string | Shipping service level (Same Day, First Class, etc.) |
| `Customer ID` | string | Unique customer identifier |
| `Customer Name` | string | Full name of customer |
| `Segment` | string | Customer segment (Consumer, Corporate, Home Office) |
| `Country` | string | Country of sale (all United States) |
| `City` | string | City of delivery address |
| `State` | string | State of delivery address |
| `Postal Code` | int | ZIP / postal code |
| `Region` | string | Geographic region (West, East, Central, South) |
| `Product ID` | string | Unique product identifier |
| `Category` | string | Product category (Technology, Furniture, Office Supplies) |
| `Sub-Category` | string | Product sub-category (Phones, Chairs, Binders, etc.) |
| `Product Name` | string | Full product description |
| `Sales` | float | Revenue from the line item (USD) |

## Added Columns (Feature Engineering)

| Column Name | Data Type | Description |
|-------------|-----------|-------------|
| `Year` | int | Year extracted from Order Date |
| `Month` | int | Month number (1-12) |
| `Month Name` | string | Month name (January, February, etc.) |
| `Shipping Days` | int | Days between Order Date and Ship Date |
