# Mumbai Monthly Rainfall Forecasting

Time-series analysis and forecasting of Mumbai monthly rainfall using 121 years of data (1,452 monthly values).

## Dataset
- File: `mumbai-monthly-rains.csv` (121 years x 12 months)

## Approach
1. EDA: annual trend, monthly distribution, heatmap, seasonal decomposition
2. Stationarity check with the Augmented Dickey-Fuller (ADF) test
3. Models compared on a hold-out period: Climatology (monthly mean), Seasonal Naive, Holt-Winters (additive and multiplicative), SARIMA, Random Forest, XGBoost
4. SARIMA order search and final forecast

## Key findings
- Rainfall is strongly seasonal; the linear year-on-year trend is small (about 4.8 mm per year, R-squared 0.10).
- ADF statistic -5.59 (p < 0.001): the series is stationary.

## Results (hold-out)
| Model | RMSE (mm) | R-squared |
|---|---|---|
| Seasonal Naive | 283.6 | 0.344 |
| Climatology (monthly mean) | 187.8 | 0.712 |
| Holt-Winters (additive) | 185.4 | 0.720 |
| SARIMA(1,0,1)(1,1,1)[12] | 186.9 | 0.715 |
| Random Forest | 187.6 | 0.713 |
| XGBoost | 197.1 | 0.684 |

Holt-Winters (additive) has the lowest RMSE, but it is only slightly better than the simple monthly-average baseline. Most of the predictable signal in this data is seasonality.

## Tech stack
Python, Pandas, NumPy, Statsmodels, Scikit-Learn, XGBoost, SciPy, Matplotlib, Seaborn

## Author
Swati Tiwari | [GitHub](https://github.com/tiwariswati186-alt) | [LinkedIn](https://www.linkedin.com/in/swati-tiwari-37972317a)
