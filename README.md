# 🏦 Banking Loan Analysis Using Power BI

### 👤 Author
**Mohammed Ilyas Siddiqui**

---

## 📌 Project Overview
The Banking Loan Analysis Project is a complete Business Intelligence solution built using Microsoft Power BI to analyze a bank’s loan portfolio. This solution demonstrates how structured banking data can be transformed into interactive dashboards and actionable insights.

The project focuses on:
- 📊 **Loan Portfolio Performance**
- ⚠ **Default Risk Analysis**
- 👥 **Customer Behavior Insights**
- 👨‍💼 **Employee Performance Evaluation**
- 💰 **Profitability & Loss Monitoring**

---

## 👨‍🎓 Project Information

| Detail | Information |
| :--- | :--- |
| **👤 Presented By** | Mohammed Ilyas Siddiqui |
| **📅 Academic Year** | 2025 – 2026 |
| **🎓 Course** | DPBA |
| **🏫 Institution** | Anudip Foundation |
| **🛠 Tool Used** | Microsoft Power BI Desktop |
| **📦 Dataset Size** | 10,000+ Records |

---

## 🎯 Business Objectives
- Analyze total loan portfolio exposure.
- Identify high-risk customers and loan products.
- Calculate financial loss due to defaults.
- Measure employee productivity and loan quality.
- Evaluate profitability by region and loan type.
- Enable data-driven banking decisions.

---

## 🧱 Data Model Architecture
This project follows a **Star Schema Model** for optimal performance and scalability.

### ⭐ Schema Structure
- **Fact Table:** `Loan_Fact`
- **Dimension Tables:**
  - `Customer_Dim`
  - `Employee_Dim`
  - `Date_Dim`

### 🔗 Relationships
- `Customer_Dim` → `Loan_Fact` (One-to-Many)
- `Employee_Dim` → `Loan_Fact` (One-to-Many)
- `Date_Dim` → `Loan_Fact` (One-to-Many)
- **Direction:** Single Direction Filtering
- **Optimization:** Optimized for DAX Performance

---

## 📊 Dashboard Modules

### 1️⃣ Executive Overview
- Total Loan Amount
- Outstanding Balance
- Net Profit
- Default Rate %
- Loan Portfolio Trend
- Loan Status Distribution

### 2️⃣ Risk & Default Analysis
- Default Rate by Loan Type
- Default Rate by Region
- Risk Heatmap (Matrix)
- High-Risk Customer Identification

### 3️⃣ Customer Insights
- Income vs Loan Amount (Scatter)
- Credit Score Distribution
- Employment Type Risk
- Customer Risk Summary

### 4️⃣ Employee Performance
- Loans Processed per Employee
- Default Rate by Employee
- Top Loan Officers
- Branch-Level Analysis

### 5️⃣ Profitability Analysis
- Interest Income
- Default Loss
- Net Profit
- Profit Trend Over Time
- Region × Loan Type Profit Matrix

---

## 🧮 Key DAX Measures

```dax
-- Total Loan Amount
Total Loan Amount = SUM(Loan_Fact[Loan_Amount])

-- Outstanding Amount
Outstanding Amount = SUM(Loan_Fact[Outstanding_Amount])

-- Interest Income Calculation
Interest Income =
SUMX(
    Loan_Fact,
    Loan_Fact[Loan_Amount] * Loan_Fact[Interest_Rate] / 100
)

-- Financial Loss due to Defaults
Default Loss =
CALCULATE(
    SUM(Loan_Fact[Outstanding_Amount]),
    Loan_Fact[Default_Flag] = 1
)

-- Net Profit Calculation
Net Profit = [Interest Income] - [Default Loss]

-- Default Rate Percentage
Default Rate % =
DIVIDE(
    CALCULATE(COUNT(Loan_Fact[Loan_ID]), Loan_Fact[Default_Flag] = 1),
    COUNT(Loan_Fact[Loan_ID])
)
```

---

## 🛠 Implementation Workflow
1. Designed structured dataset in Excel.
2. Imported data into Power BI.
3. Built Star Schema relationships.
4. Created reusable DAX measures.
5. Designed interactive dashboards.
6. Applied slicers & conditional formatting.
7. Validated KPIs and insights.

---

## 🔍 Key Insights Generated
- Personal loans show comparatively higher default rates.
- Certain regions contribute significantly to default loss.
- Low credit score customers have higher risk probability.
- Experienced employees sanction lower-risk loans.
- Profitability varies significantly across loan categories.

---

## 🚀 Future Enhancements
- Machine Learning-based Default Prediction.
- Row Level Security (RLS).
- What-If Parameter Simulation.
- Real-Time Banking Data Integration.

---

## 📂 Repository Structure

```text
Banking-Loan-Analysis/
│
├── Dataset/
│   ├── Loan_Fact.xlsx
│   ├── Customer_Dim.xlsx
│   ├── Employee_Dim.xlsx
│   └── Date_Dim.xlsx
│
├── PowerBI_File/
│   └── Banking_Loan_Analysis.pbix
│
└── README.md
```

---

## 📈 Skills Demonstrated
- **Data Modeling:** Star Schema design.
- **Advanced DAX:** Calculations for financial metrics and ratios.
- **KPI Design:** Defining and tracking key performance indicators.
- **Risk Analysis:** Identifying and visualizing risk factors.
- **Financial Analytics:** Profit/Loss and interest calculations.
- **Dashboard UX/UI:** Creating user-friendly, interactive reports.
- **Business Insight Communication:** Translating data into actionable business strategies.

---

## 🏁 Conclusion
This project showcases a complete end-to-end banking analytics solution using Power BI. It demonstrates the ability to transform structured financial data into meaningful business intelligence dashboards for strategic decision-making.

---
