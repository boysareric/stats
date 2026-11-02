# Validation

All 10 scripts were executed successfully with Python 3.12.14. Plotting practicals were run with `--save` and the Agg backend. The three generated PNGs were checked visually.

Practical 7 was checked using the illustrative observations `248 249 250 251 252`; its 95% interval was checked against the t critical value for four degrees of freedom. Interval nesting, constant observations, and rejection of missing, insufficient and non-finite observations were also checked. The original weight dataset is missing, so the manual's Practical 7 intervals remain unverified.

## Comparison with printed outputs

The scripts retain the supplied observations and methods. The checked-in `output.txt` files contain actual execution results.

| Practical | Manual | Executed result |
| --- | --- | --- |
| 3 | Variance 82.18; SD 9.07 | Sample Variance: 82.18; Sample Std Dev: 9.07 |
| 6 | n=10: 501.2/159.9; n=30: 495.1/92.8; n=100: 500.1/49.6 (mean/SD) | Sample Size n = 10: Mean=501.2, SD=159.9; Sample Size n = 30: Mean=495.1, SD=92.8; Sample Size n = 100: Mean=500.1, SD=49.6 |
| 8 | t=-0.577; p=0.5818 | t-statistic: -0.577; p-value: 0.5818 |
| 9 | t=-2.490; p=0.0471 | t-statistic: -3.030; p-value: 0.0231 |
| 10 | Intercept 68.00; slope 0.84; R-squared 0.9955 | Intercept (beta_0): 68.00; Slope (beta_1): 0.84; R-squared: 0.9955 |

Practical 9 differs from the printed answer: the supplied shift observations produce t=-3.030 and p=0.0231 with the equal-variance two-sided test. Simulation results may vary with library versions. No missing observations were inferred from the printed answers.

## Environment

- numpy 2.5.4
- pandas 3.1.0
- scipy 1.18.1
- matplotlib 3.11.2
- statsmodels 0.15.0

