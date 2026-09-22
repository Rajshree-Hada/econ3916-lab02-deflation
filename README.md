# econ3916-lab02-deflation
Lab 02 submission

**Deflating Economic Data — Nominal vs. Real**

Objective

This project quantifies the gap between nominal and inflation-adjusted (real) economic indicators by deflating average hourly earnings and Big Mac prices using CPI data pulled directly from the Federal Reserve Economic Data (FRED) API.

Methodology
* Retrieved Consumer Price Index (CPI) and average hourly earnings series from FRED's public API (no credential required for read access)
* Implemented a custom deflate_series() function to convert nominal dollar values into constant, base-year-adjusted dollars
* Applied the deflation methodology to two independent series: average hourly wages and the U.S. Big Mac price, to test consistency of the nominal/real divergence across different goods
* Aligned irregularly-spaced Big Mac observations with monthly CPI data using an as-of (last-known-value) join
* Built an interactive exploration tool (ipywidgets + matplotlib) allowing dynamic base-year selection, series toggling, and nominal/real comparison with live percentage-change readouts
  
Key Findings
* Average hourly earnings: nominal wages rose from $2.50 to $32.53, while real (inflation-adjusted) wages moved from $20.92 to $25.20 (2020 dollars) over the same period — demonstrating that a substantial share of apparent wage growth reflects inflation rather than genuine gains in purchasing power
* Big Mac price (U.S.): nominal price rose +178%, compared to +43% in real terms, against CPI growth of +95% over the same dates — reinforcing the same nominal/real divergence pattern observed in wage data
* Across both series, the compounding identity (1 + real) × (1 + CPI) = (1 + nominal) held, confirming that nominal growth reflects the product, not the sum, of real growth and inflation
* The interactive explorer demonstrates that while changing the deflation base year shifts the real series' dollar level, it leaves percentage growth rates unchanged — isolating base-year choice as a presentational parameter, not a substantive one
