# 💳 Credit Card Customer Report – Power BI Dashboard

## 📘 Overview
The **Credit Card Customer Report** is an interactive Power BI dashboard designed to analyze and visualize key insights related to **credit card usage, customer demographics, and financial performance**.  
The dashboard provides a data-driven view for decision-makers to understand spending patterns, customer segmentation, and profitability metrics.

---

## 📊 Objectives
- To analyze **customer demographics** and **geographical distribution**.  
- To monitor **credit card transaction trends** and **usage behavior**.  
- To evaluate **revenue contribution** and **profitability** by customer segments.  
- To support **data-driven marketing** and **customer retention strategies**.

---

## 📂 Data Sources
The report is built using multiple CSV datasets:

| File Name | Description |
|------------|-------------|
| `customer.csv` | Contains demographic details such as age, gender, income, and customer category. |
| `cust_add.csv` | Includes customer address and regional information for location-based analysis. |
| `credit_card.csv` | Holds transactional data including card type, credit limit, spending amount, and payment patterns. |
| `cc_add.csv` | Contains additional attributes such as card activation, tenure, and usage frequency. |

---

## 🧮 Data Model
The Power BI data model is a **star schema** with relationships between fact and dimension tables:

- **Fact Table**: `credit_card.csv`  
- **Dimension Tables**: `customer.csv`, `cust_add.csv`, `cc_add.csv`  
- Relationships established using:
  - `Customer_ID`
  - `Card_ID` (where applicable)

---

## ⚙️ Key Features
- 📈 **KPIs**: Total Transactions, Revenue, Active Customers, Avg. Spend per Customer  
- 👥 **Customer Segmentation**: Based on age group, income level, and region  
- 💸 **Spending Analysis**: Monthly trends, transaction categories, and card types  
- 🌍 **Geographical Insights**: Map visuals for customer and transaction distribution  
- 📊 **Profitability Metrics**: Revenue vs. cost ratio, and top performing customer segments  
- 📅 **Time Intelligence**: Year-over-year and month-over-month performance comparisons  
- 🧠 **Dynamic Filters & Slicers**: For interactive exploration (by region, gender, card type, etc.)

---

## 🧠 DAX Measures Used
Examples of key DAX calculations in the report include:
```DAX
Total Transactions = COUNTROWS('credit_card')

Total Revenue = SUM('credit_card'[Amount])

Average Spend per Customer = 
DIVIDE([Total Revenue], DISTINCTCOUNT('customer'[Customer_ID]))

Active Customers = 
CALCULATE(
    DISTINCTCOUNT('customer'[Customer_ID]), 
    'credit_card'[Status] = "Active"
)

Profit Margin = 
DIVIDE([Total Revenue] - [Total Cost], [Total Revenue])
🧩 Visualizations

The Power BI dashboard includes:

Overview Page – Key KPIs and high-level trends

Customer Insights Page – Age, gender, and income segmentation

Card Performance Page – Usage distribution by card type and credit limit

Geographical Insights Page – Regional breakdown and customer distribution

Profitability Analysis Page – Revenue vs. cost, and top 10 profitable customers

🧰 Tools & Technologies

Power BI Desktop – Data modeling, DAX, and visualization

Microsoft Excel / CSV – Source data preparation

DAX (Data Analysis Expressions) – Advanced calculations and KPIs

🚀 How to Use

Open the Power BI file Credit_card_Report.pbix in Power BI Desktop.

Make sure all CSV files (customer.csv, cust_add.csv, credit_card.csv, cc_add.csv) are in the same folder path.

Refresh the data model to load updated data.

Explore the report through filters, slicers, and interactive visuals.

📈 Insights Example

The majority of active credit card users are in the 30–45 age range.

Gold and Platinum cards contribute to the highest transaction values.

Urban regions show greater transaction volumes compared to rural areas.

Customers with high income levels have a higher average credit utilization.

🏁 Conclusion

This Power BI dashboard empowers business users to make data-informed decisions by providing actionable insights into customer behavior, card performance, and profitability trends.
It enables marketing optimization, customer retention strategies, and financial performance tracking.
