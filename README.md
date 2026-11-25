# 🛒 E-Commerce Sales Data Analysis Using Python

## 📌 1. Project Introduction

This project focuses on analyzing E-Commerce Sales Data using Python. The main purpose is to explore the dataset, understand sales performance, identify trends and patterns, and generate meaningful business insights through data analysis and visualization.

## 🎯 2. Project Objectives

- Understand the E-Commerce sales dataset.
- Perform preliminary data analysis.
- Identify numerical and categorical columns.
- Clean and prepare the dataset.
- Perform Exploratory Data Analysis (EDA).
- Analyze sales trends and patterns.
- Create charts and visualizations.
- Extract meaningful analytical findings.

## 📂 3. Dataset Information

The dataset used in this project contains E-Commerce sales-related information.
| Item | Details |
|---|---|
| Dataset filename referenced in notebook | `ecommerce_sales_sample_5190.csv` |
| File format | CSV |
| Records in notebook output | 25 |
| Original columns | 12 |
| Date coverage shown in monthly output | January–September 2026 |
| Cleaned records | 25 |
| Cleaned columns | 12 original columns, plus derived `order_month` |

### Dataset columns
| Column | Description |
|---|---|
| `order_id` | Identifier assigned to an order |
| `order_date` | Date on which the order was placed |
| `customer_id` | Identifier assigned to a customer |
| `product_id` | Identifier assigned to a product |
| `quantity` | Quantity recorded for the order |
| `unit_price` | Unit price recorded for the product |
| `discount` | Discount value recorded for the order |
| `sales` | Sales amount recorded in the dataset |
| `profit` | Profit amount recorded in the dataset |
| `payment_method` | Payment-method category/code |
| `ship_mode` | Shipping-mode category/code |
| `order_status` | Order-status category/code |

Data interpretation caution: The categorical values shown in the notebook include generated-looking labels such as payment_method_58, ship_mode_23, and order_status_84. Their real-world meanings are not provided. Treat them as category identifiers unless a data dictionary explains them.

### 📋 Dataset Features

[Add the actual column names and their descriptions after checking the dataset.]

## 🛠️ 4. Tools & Technologies

| Tool / Technology | Purpose |
|---|---|
| Python | Programming language |
| Jupyter Notebook | Code development and execution |
| Pandas | Data manipulation and cleaning |
| NumPy | Numerical operations |
| Matplotlib | Data visualization |
| Seaborn | Statistical visualization |
| GitHub | Project hosting and documentation |

## ⚙️ 5. Installation & Requirements

### Prerequisites

- Python 3.x
- Jupyter Notebook
- Required Python libraries

### Install Required Libraries

```bash
pip install pandas numpy matplotlib seaborn notebook
```

### Launch Jupyter Notebook

```bash
jupyter notebook
```

### Install Using requirements.txt

Create a file named `requirements.txt` and add:

```text
pandas
numpy
matplotlib
seaborn
plotly
notebook
```

Install all dependencies using:

```bash
pip install -r requirements.txt
```

## 📁 6. Project Structure

```text
E-Commerce-Sales-Analysis/
│
├── Dataset/
│   └── ecommerce_sales_sample_5190.csv
│
├── Notebook/
│   └── E-commerce sales analysis.ipynb
│
├── Visualizations/
│   ├── sales_distribution.png
│   ├── profit_distribution.png
│   ├── sales_by_product.png
│   ├── profit_by_product.png
│   ├── sales_by_payment_method.png
│   ├── sales_by_shipping_mode.png
│   ├── order_status_distribution.png
│   ├── monthly_sales_profit_trend.png
│   └── correlation_heatmap.png
│
├── Output/
│   ├── ecommerce_sales_cleaned.csv
│   ├── ecommerce_products.csv
│   ├── ecommerce_sales_table.csv
│   └── ecommerce_sales.db
│
├── README.md
└── requirements.txt
```

*Note: Update the folder and file names to match the actual GitHub repository.*

## 🔄 7. Project Workflow

 

## 🧹 8. Data Cleaning

Data cleaning is an important step in preparing the dataset for analysis.

The actual cleaning operations performed in this project will be documented here, such as:

- Create a working copy
- standardize column name
- check missing values
- handle missing values
- Remove duplicate records
- Convert numerical columns
- convert dates and extract month

The notebook checks negative values in quantity, unit_price, and sales, and uses the IQR method to identify potential outliers in numerical columns. Its saved output reports no negative values in those three checks and zero IQR outliers in the numerical columns.
| Check | Result in notebook |
|---|---:|
| Original shape | 25 × 12 |
| Cleaned shape | 25 × 12 |
| Missing values after cleaning | 0 |
| Duplicate records after cleaning | 0 |
| Negative quantity values | 0 |
| Negative unit-price values | 0 |
| Negative sales values | 0 |
| IQR outliers reported | 0 in each numeric column |

## Cleaning summary

These checks are useful, but business rules should still be used to decide whether a value is genuinely invalid.
## 🗄️ 10. SQLite Database Design
The notebook creates two related tables:
Products table
- product_id is the primary key.
Sales table
- record_id is the primary key.
- product_id is a foreign key referencing Products(product_id).
The notebook enables SQLite foreign-key enforcement and runs:
```text
pd.read_sql_query("PRAGMA foreign_key_check", conn)
```
The saved result is an empty DataFrame, meaning the check found no foreign-key violations.

Relationship-design note: The notebook output shows 25 unique product IDs across 25 sales records. This is valid for the current sample, but it does not demonstrate repeated sales for the same product. A larger dataset with repeated product IDs would better demonstrate a one-to-many product-to-sales relationship.

## 📊 9. Key Performance Indicators (KPIs)
The notebook calculates the following metrics:
| KPI | Result |
|---|---:|
| Total Sales | 2,250.00 |
| Total Profit | 2,325.00 |
| Total Quantity | 41,100 |
| Average Sales | 90.00 |
| Average Profit | 93.00 |
| Profit Margin as calculated in notebook | 103.33% |
| Maximum Sales | 166.00 |
| Minimum Sales | 18.50 |
| Maximum Profit | 156.50 |
| Minimum Profit | 25.50 |
| Average Discount | 95.00 |
| Maximum Discount | 154.00 |


The notebook calculates profit margin as:
```text
profit_margin = (total_profit / total_sales) * 100
```
Important validation: Since the recorded profit is greater than recorded sales, verify the definitions, units, and calculation of these fields with the dataset source. Do not describe the 103.33% result as a conventional profit margin until it is validated.
## 🔍 10. Exploratory Data Analysis (EDA)

Exploratory Data Analysis is performed to understand the dataset and discover meaningful patterns.

The analysis includes:

- Sales and profit distributions.
- Total sales and profit by product.
- Product quantity.
- Sales by payment-method category.
- Sales by shipping-mode category.
- Order-status frequency.
- Monthly sales and profit trends.
- Correlations between numerical variables.

## Product analysis
The notebook identifies:
- Highest-sales product: PRO-1020
- Highest-profit product: PRO-1019
- Lowest-profit product: PRO-1005

## Payment and shipping analysis
- Highest-sales payment-method category: payment_method_58
- Highest-sales shipping-mode category: ship_mode_23
These are category codes in the notebook, not descriptive names.

## Order-status analysis
The notebook reports 25 order-status categories, each occurring once. Therefore, there is no meaningful repeated or dominant status in this sample. The code's idxmax() returns the first tied category, not a genuinely most common status.


##  📈 10. Data Visualization
Data visualization helps present analytical results through charts and graphs.
| Visualization | Business / analytical purpose |
|---|---|
| Sales distribution histogram | Understand the spread of sales values |
| Profit distribution histogram | Understand the spread of profit values |
| Top products by sales | Compare product sales performance |
| Top products by profit | Identify products contributing the most recorded profit |
| Sales by payment method | Compare payment category totals |
| Sales by shipping mode | Compare shipping category totals |
| Order-status pie chart | Show the frequency of order-status categories |
| Monthly sales and profit line chart | Understand changes over time |
| Correlation heatmap | Examine relationships between numerical variables |

### 📈 1 – [sales distributon]

![Visualization 1]

**Observation:** [Add the actual observation from this chart.]

### 📊 Visualization 2 – [Actual Chart Title]

![Visualization 2](Visualizations/actual_chart_2.png)

**Observation:** [Add the actual observation from this chart.]

### 📉 Visualization 3 – [Actual Chart Title]

![Visualization 3](Visualizations/actual_chart_3.png)

**Observation:** [Add the actual observation from this chart.]

*Replace the sample image paths and titles with the actual chart files generated in the project.*

## 💡 11. Key Analytical Findings

The key findings will be documented based on the actual analysis and visualizations.

- [Add actual finding 1]
- [Add actual finding 2]
- [Add actual finding 3]

## 📝 12. Conclusion

This project demonstrates the use of Python for E-Commerce sales data analysis. Through data cleaning, exploratory data analysis, and visualization, the project aims to identify useful patterns and generate meaningful business insights.

## 👨‍💻 13. Author

**Sreerag PS**
