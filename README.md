# Walmart Sales Data Analysis (SQL Project)

Exploratory analysis of Walmart sales transactions using **MySQL**, aimed at understanding top-performing branches, products, sales trends, and customer behaviour to help improve sales strategy.

## 📊 About the Dataset

The dataset is sourced from the **Kaggle Walmart Sales Forecasting Competition**. It contains transactions from three Walmart branches located in **Mandalay, Yangon, and Naypyitaw**.

- **Rows:** 1,000
- **Columns:** 17

| Column | Description |
|---|---|
| Invoice ID | Unique invoice number of the sale |
| Branch | Branch where the sale occurred (A, B, C) |
| City | City of the branch |
| Customer type | Member or Normal |
| Gender | Gender of the customer |
| Product line | Product category |
| Unit price | Price per unit ($) |
| Quantity | Number of units purchased |
| Tax 5% | 5% tax on the transaction |
| Total | Total price including tax |
| Date | Date of purchase |
| Time | Time of purchase |
| Payment | Payment method (Cash, Credit card, Ewallet) |
| cogs | Cost of goods sold |
| gross margin percentage | Gross margin % |
| gross income | Gross income earned |
| Rating | Customer's rating of the shopping experience (1–10) |

## 🎯 Project Purpose

To gain insight into Walmart's sales data and understand the factors that affect sales performance across branches, and use those insights to improve and optimize sales strategy.

## 🔍 Analysis Areas

1. **Product Analysis** — Understand product line performance and identify which lines need improvement.
2. **Sales Analysis** — Study sales trends to measure the effectiveness of sales strategies.
3. **Customer Analysis** — Uncover customer segments, purchase patterns, and segment profitability.

## 🛠️ Approach

1. **Data Wrangling** — Build the database, create the table, load the CSV, and check for null values (columns set to `NOT NULL`, so no nulls exist).
2. **Feature Engineering** — Derive new columns from existing data:
   - `time_of_day` — Morning / Afternoon / Evening, from the `Time` column
   - `day_name` — Day of the week (Mon–Sun), from the `Date` column
   - `month_name` — Month name, from the `Date` column
3. **Exploratory Data Analysis (EDA)** — Run SQL queries to answer the business questions below.

## 💰 Revenue & Profit Formulas

```
COGS         = Unit Price × Quantity
VAT (Tax 5%) = 5% × COGS
Total        = VAT + COGS
Gross Income = Total − COGS
Gross Margin % = Gross Income / Total
```

## ❓ Business Questions Answered

**General**
- How many unique cities are in the data, and which branch is in which city?

**Product**
- How many unique product lines are there?
- What's the most common payment method?
- What's the best-selling product line?
- What's the total revenue and COGS by month?
- Which product line earns the most revenue and pays the most tax?
- Which city generates the largest revenue?
- Which branch sells more units than the average?
- What's the most common product line by gender, and the average rating per product line?

**Sales**
- How many sales happen in each part of the day, per weekday?
- Which customer type brings in the most revenue?
- Which city has the highest average tax percentage?
- Which customer type pays the most tax?

**Customer**
- How many unique customer types and payment methods are there?
- What's the most common customer type, and the gender split overall and per branch?
- Which time of day and day of the week get the best ratings, overall and per branch?

## 🗄️ Tech Stack

- **MySQL** — data storage and querying
- **Jupyter Notebook** — documenting the workflow, queries, and findings

## 📁 Repository Structure

```
├── walmartsalesdata.csv                    # Raw dataset
├── 1-Walmart-sales-SQL-Project.ipynb       # SQL queries + explanations
├── Walmart_Sales_Project_Report.docx       # Full project report
└── README.md
```

## 🚀 How to Run

1. Create a new database in MySQL.
2. Import `walmartsalesdata.csv` into a table (enable **"first row contains column names"** during import).
3. Run the feature engineering queries first (`time_of_day`, `day_name`, `month_name` columns) — these are used by later queries.
4. Run the analysis queries from the notebook in order to reproduce the findings.

## 📌 Key Findings (Summary)

- **Naypyitaw** generates the highest total revenue among the three cities.
- **Food and beverages** is the top revenue- and tax-generating product line.
- **Fashion accessories** and **Food and beverages** are the best-selling product lines by quantity.
- **Ewallet** and **Cash** are the most common payment methods.
- **Branch A** sells more units than the branch average.
- **Member** customers bring in more revenue than **Normal** customers.
- **January** had the highest revenue and COGS among the months in the data.

---
*Dataset credit: Kaggle — Walmart Sales Forecasting Competition.*
