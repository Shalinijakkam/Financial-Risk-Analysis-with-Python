# Financial Risk Analysis with Python 🏦

## Project Overview
An end-to-end financial risk analysis pipeline built in Python to analyze Morgan Stanley banking transaction data. The project covers data cleaning, customer profiling, risk identification, anomaly detection, and hypothesis testing.

## Business Problem
Banks need to monitor customer accounts for financial risk — identifying suspicious transactions, dormant accounts, high-risk customers, and volatile account behavior before they become serious problems.

## Tools & Technologies
- **Python** — Pandas, NumPy, Matplotlib
- **Jupyter Notebook**
- **Dataset** — Morgan Stanley banking transaction data (CSV)

---

## Project Workflow

### Task 1: Data Cleaning & Formatting
- Checked for null values and special characters using `isnull()` and `info()`
- Validated TransactionAmount and AccountBalance as numeric
- Converted TransactionDate to proper datetime format for time-based analysis
- Standardized AccountType and TransactionType columns for consistency

### Task 2: Descriptive Transactional Analysis
- Calculated monthly and yearly summaries of total credits and debits
- Classified deposits as credits and withdrawals/payments/transfers as debits
- Computed net transaction volume (credits minus debits) per account
- **Finding:** Debits are higher than credits in most months — customers are spending more than they are earning

### Task 3: Customer Profile Building
- Segmented accounts by transaction frequency:
  - High activity: more than 15 transactions
  - Medium activity: 5 to 15 transactions
  - Low activity: fewer than 5 transactions
- Segmented customers by average account balance and average transaction volume using percentile-based thresholds
- Flagged dormant accounts with transaction gaps of 2 months or more
- Identified top performing accounts (highest net inflow) and bottom performing accounts (highest negative net inflow)

### Task 4: Financial Risk Identification
- Flagged accounts with frequent large withdrawals using percentile-based threshold
- Identified overdraft accounts with zero or negative balances
- Calculated balance volatility using Standard Deviation and Coefficient of Variation
- **Finding:** 142 customers flagged as having irregular or suspicious transaction behavior based on withdrawal patterns, overdraft risk, and balance volatility

### Task 5: Anomaly Detection
- Applied IQR (Interquartile Range) method to detect anomalous transactions
- Flagged transactions falling outside 1.5 times the IQR as abnormal
- These transactions indicate rare but potentially high-risk financial activity

### Task 6: Hypothesis Testing
- **Test 1:** Independent t-test comparing average balances of high-volume vs low-volume accounts → p = 0.69 (no significant difference — higher transaction volume does not mean higher balance)
- **Test 2:** Independent t-test comparing balance volatility between medium and low activity segments → p = 0.85 (account activity level does not significantly impact balance volatility)

---

## Key Findings
| Finding | Detail |
|---|---|
| Spending Pattern | Debits exceed credits in most months |
| Dormant Accounts | Accounts with 2+ month transaction gaps flagged |
| High Risk Customers | 142 customers flagged for suspicious behavior |
| Top Performer | Accounts with highest net positive inflow identified |
| Anomalies | Unusual transactions detected using IQR method |

---

## Visualizations
- Line chart: Monthly trend of total credits vs debits
- Bar chart: Credit vs Debit transaction counts
- Histogram: Distribution of transaction amounts
- Histogram: Distribution of account balances
- Bar chart: Dormant vs Active accounts
- Bar chart: Suspicious vs Normal customers
- Bar chart: Account activity levels

---

## Project Structure
```
Financial-Risk-Analysis-with-Python/
│
├── morgan_py.ipynb          # Main Jupyter Notebook
├── morgan_stanely.csv       # Dataset
└── financial risk analysis.pdf  # Project report
```

---

## How to Run
1. Clone the repository
2. Open `morgan_py.ipynb` in Jupyter Notebook
3. Install required libraries: `pip install pandas numpy matplotlib`
4. Run all cells in order

---

## Author
**Shalini Jakkam**
- LinkedIn: https://www.linkedin.com/in/shalini-jakkam-815046308/
- GitHub: https://github.com/Shalinijakkam

