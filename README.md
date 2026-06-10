# Canadian Bank Stock & Financial Performance Analysis (2022–2024)

## Project Overview
This project conducts an equity research-style analysis of six major Canadian banks 
(RBC, TD, BMO, CIBC, Scotiabank, National Bank) across the Bank of Canada rate hiking 
cycle from 2022 to 2024. The core question: given near-identical systematic risk profiles, 
why did three-year returns diverge from -13% (TD) to +60% (NA)?

The analysis moves from fundamental metrics → stock performance → CAPM risk decomposition 
→ valuation, building toward an investment thesis on each bank.

## Tools & Technologies
- **Python** (yfinance, pandas, matplotlib, scipy) — data collection, analysis, visualization
- **SQL** (SQLite, window functions) — fundamental data storage and querying
- **Excel** — BVPS manually compiled from each bank's Annual Reports

## Data Sources
- Stock prices: Yahoo Finance via yfinance API (2022–2024)
- Fundamental metrics (ROE, NIM, CET1, PCL ratio): Manually sourced from each bank's 
  Annual Report via SEDAR+ / Investor Relations pages
- Book Value per Share: Calculated from Consolidated Balance Sheets (common shareholders' 
  equity ÷ common shares outstanding, end of period), fiscal year ending October 31

## Analytical Framework

### 1. Fundamental Baseline
Four metrics tracked across 2022–2024: ROE (profitability), NIM (margin), 
CET1 (capital strength), PCL ratio (credit risk). Establishes which banks entered 
the period strong and which carried structural vulnerabilities.

### 2. Stock Performance & Return Drivers
Normalized price index (base=100) shows divergence over time.
Scatter analysis reveals ROE is positively correlated with returns — 
market rewarded profitability. PCL scatter shows CIBC as a clear outlier: 
highest credit stress but strong price recovery, consistent with a 2024 re-rating.

### 3. CAPM Risk Decomposition
Beta range: 0.815–1.023 — six banks carry near-identical systematic risk.
Jensen's Alpha isolates idiosyncratic performance:
- NA: +9.25% | CM: +8.11% | RY: +7.32% | BMO: +0.09% | BNS: -3.92% | TD: -8.41%

Beta cannot explain the return spread. Alpha can.

### 4. Valuation — Price-to-Book
P/B ratio tracked annually against book value (fiscal year-end).
2023 saw BMO, CIBC, and BNS trade below book (P/B < 1.0) — 
market pricing in asset quality concerns. By 2024, full sector re-rating occurred.
TD remains the only bank whose P/B declined across the period (1.35 → 1.21), 
reflecting persistent AML regulatory overhang.

## Key Investment Conclusions
- **National Bank**: Highest Alpha (+9.25%) + highest 2024 P/B (1.92). 
  Dominant Quebec franchise, superior ROE sustainability, lowest credit deterioration. 
  Premium valuation appears justified by fundamentals.
- **RBC**: Strong Alpha (+7.32%), P/B recovered to 1.92. 
  Consistent execution with no major idiosyncratic risk events.
- **CIBC**: Largest P/B re-rating (0.85 → 1.44). Market had priced in peak credit stress 
  in 2023; 2024 recovery suggests worst-case scenario did not materialize.
- **TD**: Negative Alpha (-8.41%), flat P/B (1.21). AML penalty quantifiably cost 
  shareholders ~8% annualized above what CAPM would predict. 
  Asset growth restrictions limit near-term recovery.
- **BMO**: Near-zero Alpha (+0.09%). Bank of the West acquisition weighed on ROE (18% → 6%) 
  and CET1 (16.7% → 12.5%) in 2023. Execution risk from U.S. integration remains.
- **Scotiabank**: Negative Alpha (-3.92%), only bank that failed to recover 2022 price levels. 
  Latin American portfolio continues to pressure credit metrics.

## Visualizations
![Stock Performance](output/bank_performance.png)
![Financial Metrics](output/financial_metrics.png)
![Return vs ROE and PCL](output/return_drivers.png)
![Alpha Beta Analysis](output/alpha_beta.png)
![Price-to-Book Ratio](output/pb_ratio.png)

## Repository Structure
```
canadian-bank-analysis/
├── README.md
├── data/
│   ├── financials.xlsx
│   └── bvps.xlsx
├── notebooks/
│   └── analysis.ipynb
├── output/
│   ├── bank_performance.png
│   ├── financial_metrics.png
│   ├── return_drivers.png
│   ├── alpha_beta.png
│   └── pb_ratio.png
└── database/
└── canadian_banks.db
```

## How to Run
1. Clone this repository
2. Install dependencies: `pip install yfinance pandas matplotlib seaborn scipy openpyxl`
3. Open `notebooks/analysis.ipynb`
4. Run all cells sequentially

## Notes on Data
- All metrics use reported (non-adjusted) figures for cross-bank comparability
- National Bank's NIM excluded from comparative analysis due to non-standard disclosure format
- BVPS verified directly from Annual Reports; not sourced from third-party aggregators
- Canadian bank fiscal year ends October 31; all year-end prices taken accordingly
