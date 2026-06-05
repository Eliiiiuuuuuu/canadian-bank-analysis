# Canadian Bank Stock & Financial Performance Analysis (2022–2024)

## Project Overview
This project analyzes the stock performance and financial health of six major Canadian banks 
(RBC, TD, BMO, CIBC, Scotiabank, National Bank) during the Bank of Canada rate hiking cycle 
from 2022 to 2024. The analysis examines how divergent business strategies and risk exposures 
led to significantly different outcomes despite similar systematic risk profiles.

## Tools & Technologies
- **Python** (yfinance, pandas, matplotlib, seaborn) — data collection and analysis
- **SQL** (SQLite) — data storage and querying
- **Power BI** — interactive dashboard
- **Excel** — financial data compilation from annual reports

## Data Sources
- Stock price data: Yahoo Finance via yfinance API
- Financial metrics (ROE, NIM, CET1, PCL ratio): Annual reports sourced directly from each 
  bank's Investor Relations page (SEDAR+ / official websites)

## Key Findings
- All six banks showed similar Beta values (0.815–1.023) against TSX Composite, yet 
  three-year cumulative returns ranged from -13% (TD) to +60% (NA), indicating that 
  idiosyncratic Alpha — not systematic risk — drove performance divergence
- **National Bank** delivered the strongest risk-adjusted performance: highest ROE 
  (18.8% in 2022) and lowest PCL ratio throughout the period, supported by its 
  dominant Quebec franchise
- **TD Bank** suffered the sharpest ROE decline (18% → 8.2%) due to a USD $3B+ AML 
  compliance penalty in the U.S., with asset growth restrictions further limiting recovery
- **Scotiabank** was the only bank that failed to recover to its 2022 baseline by end of 
  2024, reflecting structural headwinds from its Latin American credit portfolio
- **CIBC** exhibited a PCL ratio up to 10x higher than peers in 2022, driven by 
  concentrated Canadian real estate exposure and conservative IFRS 9 provisioning strategy
- **BMO's** ROE collapsed to 6% in 2023 following the Bank of the West acquisition, 
  with CET1 declining from 16.7% to 12.5% as capital was deployed for U.S. expansion

## Repository Structure
```
canadian-bank-analysis/
├── README.md
├── data/
│   └── financials.xlsx
├── notebooks/
│   └── analysis.ipynb
├── output/
│   ├── bank_performance.png
│   ├── correlation_matrix.png
│   └── financial_metrics.png
└── database/
    └── canadian_banks.db
```

## How to Run
1. Clone this repository
2. Install dependencies: pip install yfinance pandas matplotlib seaborn openpyxl
3. Open notebooks/analysis.ipynb
4. Run all cells sequentially

## Notes on Data
- All financial metrics use reported (non-adjusted) figures for cross-bank comparability
- National Bank's NIM is excluded from comparative analysis due to non-standard 
  disclosure format (non-trading adjusted basis)
- Financial data collected manually from each bank's 2022, 2023, and 2024 Annual Reports
