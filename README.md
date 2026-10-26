Modelling Dynamic and Predictive Relationships Among Indian Macro-Financial Indicators: A VAR Approach

A Vector Autoregression (VAR) study of the short-run interdependence between real GDP growth, inflation (CPI) and the BSE Sensex in India, using quarterly data from 2013 Q2 to 2025 Q2.

The project tests who predicts whom (Granger causality), how shocks propagate (impulse response functions) and how much of each variable's uncertainty comes from the others (forecast error variance decomposition).

Key Findings
Question	Result
Does inflation predict the Sensex?	Yes. CPI change Granger-causes the Sensex (p = 0.0049). The reverse is not significant.
Does the Sensex or GDP predict inflation?	No (p = 0.63 and 0.21). Inflation behaves as largely exogenous in this system.
Does the Sensex predict GDP?	Only borderline (p = 0.109), not significant at 5%.
How does the Sensex respond to an inflation shock?	Sharp fall, trough about one quarter after the shock, then slow decay back towards zero over roughly 8-10 quarters.
How much of Sensex variance is explained by inflation?	Rises from about 1.4% at impact to about 20% at longer horizons. GDP explains about 13-15%.
How persistent are the series?	GDP (coef. 0.34, p = 0.022) and Sensex (coef. 0.72, p < 0.001) both show strong own-lag persistence.

Takeaway: inflation is the main external macro driver of the Indian equity market in this sample, while GDP growth is persistent but has limited short-run influence on market movements. The results suggest the market adjusts gradually to inflation news rather than fully anticipating it.

Data
Variable	Definition	Source
GDP	Real GDP, year-on-year growth (quarterly)	CEIC Data
CPI	Consumer Price Index, year-on-year growth, monthly values averaged to quarterly	CEIC Data
SENSEX	BSE Sensex 30 closing price, monthly values averaged to quarterly	Investing.com

Sample: 2013 Q2 - 2025 Q2 (quarterly).

Methodology
Stationarity (ADF test). GDP and Sensex are stationary at levels, I(0). CPI is non-stationary at levels (p = 0.081) and stationary after first differencing, I(1). The model therefore uses CPI_diff, GDP and SENSEX.
Lag selection. AIC, BIC, FPE and HQIC were compared. BIC and HQIC select lag 1, so a VAR(1) is estimated.
Estimation. Equation-by-equation OLS.
Diagnostics.
Stability: all eigenvalues lie inside the unit circle (largest is about 0.72).
Residual autocorrelation: Portmanteau test (lag 12), p = 0.123, so residuals are consistent with white noise.
ARCH-LM: p = 0.57 (CPI_diff), 0.26 (GDP), 0.31 (Sensex), so no ARCH effects detected.
Dynamic analysis. Granger causality, impulse response functions (IRF) and forecast error variance decomposition (FEVD).
Model
CPI_diff(t) = c + a1*CPI_diff(t-1) + a2*GDP(t-1) + a3*SENSEX(t-1) + e1(t)
GDP(t)      = c + b1*CPI_diff(t-1) + b2*GDP(t-1) + b3*SENSEX(t-1) + e2(t)
SENSEX(t)   = c + d1*CPI_diff(t-1) + d2*GDP(t-1) + d3*SENSEX(t-1) + e3(t)
Results in Detail
Estimated coefficients (VAR(1))
Equation	L1.CPI_diff	L1.GDP	L1.SENSEX
CPI_diff	-0.050 (p = 0.735)	-0.034 (p = 0.210)	0.007 (p = 0.628)
GDP	-0.387 (p = 0.635)	0.345 (p = 0.022)	0.121 (p = 0.107)
SENSEX	-3.473 (p = 0.004)	-0.048 (p = 0.829)	0.718 (p < 0.001)
Granger causality
Target	Cause	p-value	Result
CPI_diff	GDP	0.2123	No
CPI_diff	SENSEX	0.6287	No
GDP	CPI_diff	0.6361	No
GDP	SENSEX	0.1094	No
SENSEX	CPI_diff	0.0049	Yes
SENSEX	GDP	0.8297	No
Impulse response

An unexpected rise in inflation produces an immediate negative response in the Sensex, reaching its trough about one quarter after the shock, followed by a gradual recovery that is nearly complete by period 10.

Forecast error variance decomposition (period 9)
Variable	Own shocks	CPI_diff	GDP	SENSEX
CPI_diff	96.7%	n/a	3.0%	0.3%
GDP	89.4%	3.4%	n/a	7.2%
SENSEX	66.6%	19.9%	13.5%	n/a
Limitations
Small sample (about 49 quarterly observations), so estimates and especially impulse-response bands are imprecise.
Quarterly averaging of monthly CPI and Sensex data smooths short-run dynamics.
A VAR(1) was chosen by BIC/HQIC; AIC and FPE favour longer lags.
Results describe predictive (Granger) relationships, not structural causality.
The sample spans the COVID-19 period, which may distort GDP growth dynamics.
Long-run (cointegration/VECM) relationships are not modelled.
Repository Structure
.
├── README.md
├── report/
│   └── Modelling_Dynamic_and_Predictive_Relationships_VAR.pdf   # Full project report
├── data/                                                         # Quarterly dataset (if shared)
└── notebooks/                                                    # Analysis code (if shared)

Adjust this section to match the files you actually upload.

Tools

Python (statsmodels, pandas, numpy, matplotlib) for ADF tests, VAR estimation, Granger causality, IRF and FEVD.

References
Sims, C. A. (1980). Macroeconomics and reality. Econometrica, 48(1), 1-48.
Fama, E. F. (1981). Stock returns, real activity, inflation, and money. American Economic Review, 71(4), 545-565.
Chen, N. F., Roll, R., & Ross, S. A. (1986). Economic forces and the stock market. Journal of Business, 59(3), 383-403.
Johansen, S., & Juselius, K. (1990). Maximum likelihood estimation and inference on cointegration. Oxford Bulletin of Economics and Statistics, 52(2), 169-210.
Stock, J. H., & Watson, M. W. (2001). Vector autoregressions. Journal of Economic Perspectives, 15(4), 101-115.
Narwal, K., & Mittal, R. (2011). Impact of macroeconomic indicators on Indian capital markets. The Journal of Risk Finance, 12(2), 84-97.
Rao, V., & Jyotreddy, K. (2022). Causal analysis of stock prices and macroeconomic variables: Evidence from Indian stock market. Asian Economic and Financial Review, 12(7), 459-472.
Chauhan, S. S., et al. (2024). A causality investigation into stock prices and macroeconomic indicators in the Indian stock market. F1000Research, 13(1299).

Full reference list is in the report.

Author

Akanchha MA Financial Economics, University of Hyderabad

Feel free to open an issue or reach out via GitHub for questions or feedback.
