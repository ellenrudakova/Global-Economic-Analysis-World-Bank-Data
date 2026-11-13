# Global-Economic-Analysis-World-Bank-Data
##  Project Overview
This project investigates whether income levels across global economies have converged over time (1990–2022). Using GDP per capita adjusted for purchasing power parity (PPP), the analysis evaluates cross-economy income dispersion ($\sigma$-convergence), growth patterns ($\beta$-convergence), and relative income mobility compared to the United States.

##  Research Questions
1. Did the dispersion of log GDP per capita decrease between 1990 and 2022 ($\sigma$-convergence)?
2. Did economies with lower initial GDP per capita grow faster between 1990 and 2021 ($\beta$-convergence)?
3. How did economies' relative income positions shift between 1990 and 2022 compared to the United States?

## Data & Methodology
* **Source:** World Bank, World Development Indicators (WDI) — Indicator `NY.GDP.PCAP.PP.KD` (GDP per capita, PPP, constant 2021 international dollars).
* **Sample:** Global economies and territories tracked by the World Bank (1990–2022).
* **Methods:**
  * Data retrieval and cleaning via `world_bank_data` and `Pandas`.
  * Natural-log transformation of GDP per capita.
  * Cross-sectional variance comparison ($\sigma$-convergence) and OLS regression of average growth rates on initial income ($\beta$-convergence).
  * Quartile-based income grouping and transition matrix analysis relative to the US benchmark.

## Key Findings
* **$\sigma$-Convergence:** The cross-sectional variance of log GDP per capita decreased slightly from **1.4005** (1990) to **1.3347** (2022), though the classical $F$-test ($p = 0.7386$) indicates this reduction in overall dispersion is not statistically significant.
* **$\beta$-Convergence:** The OLS regression yields a statistically significant negative slope ($\beta \approx -0.0042$, $p < 0.001$), providing empirical evidence of unconditional $\beta$-convergence (lower-income economies grew faster on average).

## Tech Stack
`Python` • `Pandas` • `NumPy` • `SciPy` • `Statsmodels` • `Matplotlib` • `Seaborn`

## How to Run
1. Clone this repository or open the `.ipynb` file in **Google Colab** or **Jupyter Notebook**.
2. Run all cells sequentially from top to bottom to fetch the latest WDI data and reproduce the visualizations.

##  Methodological Notes & Future Improvements
* **Sample Consistency:** Ensuring a strictly balanced panel of economies across both 1990 and 2022 for dispersion comparisons.
* **Statistical Testing:** Supplementing the classical variance $F$-test with paired-sample dispersion tests and reporting heteroskedasticity-robust standard errors (HC3) for growth regressions.
