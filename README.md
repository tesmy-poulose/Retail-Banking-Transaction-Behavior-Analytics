# Retail Banking Transaction Behavior Analytics
## 📌 Project Overview

The Retail Banking Transaction Behavior Analytics project focuses on analyzing customer transaction data to understand banking behavior patterns and generate business insights.

The dashboard was developed using Power BI to analyze withdrawals, deposits, transaction frequency, and monthly trends. The project demonstrates end-to-end analytics workflow including data cleaning, transformation, and visualization.

## 🎯 Project Goal

Analyze customer transaction data to:

- Understand customer spending behavior

- Detect anomalies or fraud patterns

- Segment customers based on activity

- Predict future transaction trends

## 🧩 Business Questions Addressed
#### 👤 Customer Behavior

- Who are high-value customers?

- What is average monthly transaction volume per customer?

- Which days or months have highest transaction activity?

- Which customers maintain high balances?

- Which customers are likely to churn (low activity trend)?

## 🛠 Tools & Technologies Used

- Power BI – Dashboard development and visualization

- Google Sheets / Excel – Data cleaning and preprocessing

- DAX – Measures and calculated columns

- GitHub – Version control and project publishing

## 📂 Dataset Information

The dataset contains retail banking transaction records including:

- Account Number

- Transaction Date

- Transaction Details

- Cheque Number

- Withdrawal Amount

- Deposit Amount

- Balance Amount

## 🧹 Phase 1 — Data Cleaning Strategy (Banking Standard)
#### 🎯 Goal

Convert blank transaction values to zero based on banking transaction logic.

✅ Clean Withdrawal Column

`Withdrawal_Clean = IF(F2="",0,F2)`

✅ Clean Deposit Column

```Deposit_Clean = IF(G2="",0,G2)```

✅ Final Transaction Amount Column

```Transaction_Amount = IF(Withdrawal_Clean>0,Withdrawal_Clean,Deposit_Clean)```

✅ Transaction Type Column

```Transaction_Type = IF(Withdrawal_Clean>0,"Debit","Credit")```

#### 🧠 Business Logic Applied

Missing transaction amounts were treated as zero values based on banking logic where each transaction is either debit or credit.

#### 📝 Cheque Number Handling

Cheque numbers were kept as Blank or Null

## 📊 Phase 2 — Customer Transaction Behavior Analysis (Google Sheets)
#### 🎯 Objective

Create customer-level transaction summary including:

- Total Withdrawal

- Total Deposit

- Total Transactions

- Average Transaction Amount

#### ✅ Method Used

Pivot Table Analysis

#### 📌 Pivot Structure

- Rows

  - Account No

- Values

  - Sum of Withdrawal_Clean

  - Sum of Deposit_Clean

  - Transaction Count

#### 📊 Dataset Insight

The dataset contained 10 unique accounts, enabling:

- Customer comparison

- High vs low activity analysis

- Withdrawal-heavy vs deposit-heavy pattern study

- Balance behavior analysis

## 📊 Phase 2B — Power BI Dashboard Development

#### ✅ DAX Measures Created
Total Withdrawal

```Total Withdrawal = SUM(Table[Withdrawal_Clean])```

Total Deposit

```Total Deposit = SUM(Table[Deposit_Clean])```

Transaction Count

```Transaction Count = COUNT(Table[Account No])```

Average Transaction

```Avg Transaction = DIVIDE([Total Withdrawal] + [Total Deposit], [Transaction Count])```

#### 📈 Dashboard Features
##### 💰 Customer Analysis

- Top Customers by Withdrawal Value

- Top Customers by Deposit Value

- Most Active Customers by Transaction Volume

##### 📅 Time Trend Analysis

- Monthly Transaction Trend Line

#### 📊 KPI Metrics

- Total Withdrawal Amount

- Total Deposit Amount

- Total Transaction Count

#### 🎛 Interactive Filters

- Month

- Transaction Type (Debit / Credit)

- Account Number

## 💡 Key Business Insights

- Identified high-value banking customers

- Detected transaction seasonality trends

- Segmented customers based on transaction frequency

- Analyzed debit vs credit distribution behavior

## 📸 Dashboard Preview

(Add your screenshot file in repo and use below)

![Dashboard Screenshot](dashboard_screenshot.png)
