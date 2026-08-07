# Banking Client Analytics Dashboard

An interactive **Power BI dashboard** for analyzing client banking data, including deposits, loans, credit exposure, and customer engagement. The project provides insights into customer financial behavior through interactive visualizations, custom DAX measures, and exploratory data analysis performed using Python.

---

## 📌 Project Overview

Banks generate large volumes of customer financial data across multiple products such as loans, deposits, savings accounts, and credit cards. This project transforms raw banking data into an interactive analytics dashboard that helps monitor key business metrics, identify customer trends, and support data-driven lending decisions.

---

## 📂 Dataset

The project uses a relational banking dataset consisting of multiple linked tables:

- **Clients - Banking** – Client-level financial information including loans, deposits, savings, checking accounts, business lending, credit cards, income, and engagement details.
- **Banking Relationship** – Customer relationship/account type.
- **Gender** – Customer gender information.
- **Investment Advisor** – Assigned financial advisor.
- **Period** – Time dimension used for filtering and reporting.

The tables are connected using primary and foreign keys to support relational analysis.

---

## ⚙️ Data Preparation

Data transformation was performed using **DAX calculated columns** in Power BI Desktop (Data view), not Power Query — new fields were added directly to the `Clients - Banking` table using DAX formulas such as `SWITCH()` and `DATEDIFF()`.

### Feature Engineering

- Created **Engagement Days** using `DATEDIFF()` from customer joining date.
- Built **Engagement Timeframe** by grouping customers based on tenure:
  - Less than 1 Year
  - Less than 5 Years
  - Less than 10 Years
  - Less than 20 Years
  - More than 20 Years
- Created **Income Band** categories:
  - Low
  - Mid
  - High
- Derived **Processing Fees** based on customer fee structure.

---

## 📊 Key DAX Measures

The dashboard includes several custom DAX measures, including:

- **Total Clients** — Distinct number of banking clients
- **Total Loan** — Bank Loan + Business Lending + Credit Card Balance
- **Bank Loan** — Total loan amount issued by the bank
- **Business Lending** — Total business lending amount
- **Credit Card Balance** — Total outstanding credit card balance
- **Total Deposit** — Bank Deposits + Savings Accounts + Checking Accounts + Foreign Currency Accounts
- **Bank Deposit** — Total bank deposits
- **Savings Account Amount**
- **Checking Account Amount**
- **Foreign Currency Amount**
- **Total Fees** — Loan balance × Processing Fee
- **Engagement Length** — Total engagement days across clients

---

## 🐍 Exploratory Data Analysis (Python)

Exploratory analysis was performed using:

- **pandas**
- **matplotlib**
- **seaborn**

The notebook includes:

- Data cleaning and preprocessing
- Univariate analysis
- Bivariate analysis
- Correlation analysis
- Distribution plots
- Correlation heatmap
- Financial variable exploration

---

## 📈 Dashboard Features

### 🏠 Home
- Executive overview of banking KPIs (Total Clients, Total Loan, Total Deposit, Total Fees, Total CC Amount, Saving Account Amount)
- Gender toggle and time-period filters (All Time, Last 30D/90D/3M/6M/12M/24M, calendar month/quarter/year)

### 💰 Loan Analysis
- Filterable by Banking Relationship, Gender, and Investment Advisor
- Bank Loan by Banking Relationship
- Bank Loan by Income Band
- Bank Loan by Nationality
- Total Loan, Bank Loan, Business Lending, and Credit Card Balance by Engagement Timeframe

### 💳 Deposit Analysis
- Filterable by Banking Relationship, Gender, and Investment Advisor
- Bank Deposit by Income Band
- Total Deposit, Bank Deposit, Savings Account, Checking Account, and Foreign Currency Account by Nationality
- Total Deposit by Engagement Timeframe

### 📊 Summary
- Consolidated view of all KPIs (Clients, Loans, Deposits, Fees, Credit Cards, Accounts, Engagement) across the same filter set

---

## ✨ Interactive Features

- Interactive slicers (Banking Relationship, Gender, Investment Advisor, time period)
- Cross-filtering across visuals
- Dynamic KPI cards
- Custom DAX calculations

---

## 📸 Dashboard Preview

### Home Dashboard
<img width="1280" height="720" alt="Home" src="https://github.com/user-attachments/assets/60c3b093-cbf3-485a-a5c6-9ca0786b084b" />

### Loan Analysis
<img width="1280" height="720" alt="Loan Analysis" src="https://github.com/user-attachments/assets/2057dbb1-ead0-4e06-af6f-0fcd6b912215" />

### Deposit Analysis
<img width="1280" height="720" alt="Deposit Analysis" src="https://github.com/user-attachments/assets/d72da5fa-b736-46a0-a5e5-ccacacc6b094" />

### Summary Dashboard
<img width="1280" height="720" alt="Summary" src="https://github.com/user-attachments/assets/7e87061c-cbad-425d-9f35-3572790eb8bf" />


---

## 📌 Dashboard Capabilities

- Monitors total banking KPIs (clients, loans, deposits, fees) from a single executive view
- Breaks down loan and deposit portfolios by banking relationship, income band, nationality, and engagement timeframe
- Enables quick comparison of client segments via interactive filtering

## 🔍 Key Insights

- Deposit balances are strongly positively correlated with checking, savings, and foreign currency account balances (via Python correlation analysis) — clients holding higher balances in one account type tend to hold higher balances across others, pointing to a smaller segment of high-value, multi-product clients.
- Within the Private Bank / Female client segment analyzed, European-nationality clients held the largest share of both loan and deposit balances among the nationality groups shown.

---

## 🛠️ Technologies Used

- **Power BI**
- **DAX**
- **Python**
- **Pandas**
- **Matplotlib**
- **Seaborn**
- **Excel**

---

## 📁 Repository Structure

```text
Banking-Client-Analytics-Dashboard/
│
├── diagrams/
│   ├── Home.png
│   ├── Loan Analysis.png
│   ├── Deposit Analysis.png
│   └── Summary.png
│
├── notebook/
│   └── BankingEDA1.ipynb
│
├── Banking Dashboard.pbix
├── Banking.csv
└── README.md
```

---

## 🚀 Getting Started

1. Clone the repository
```bash
git clone https://github.com/<your-username>/Banking-Client-Analytics.git
```
2. Open `dashboard/Banking_Dashboard.pbix` in **Power BI Desktop**.
3. If required, reconnect the dataset to `data/Banking.csv`.
4. Refresh the report to interact with the latest dashboard.

