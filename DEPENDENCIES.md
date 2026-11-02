# Dependencies and installation

The supplied **Statistics Lab manual-1_organized.pdf** contains 10 Python practicals. Its code imports five third-party packages: **NumPy, pandas, SciPy, Matplotlib and statsmodels**. Python 3.12 is the tested interpreter; pip installs the packages.

The PDF does not specify package versions. The versions in [requirements.txt](requirements.txt) are pinned to the environment used to execute the repository's scripts, as recorded in [VALIDATION.md](VALIDATION.md).

## What each package does

| Install name | Import used | Purpose | Practicals in this repository |
| --- | --- | --- | --- |
| `numpy` | `import numpy as np` | Numerical arrays, random sampling and sample means | 4, 5, 6, 7, 8, 9 |
| `pandas` | `import pandas as pd` | Student DataFrame, sales statistics and regression input table | 1, 2, 3, 10 |
| `scipy` | `import scipy.stats as stats` or `from scipy import stats` | Binomial/Poisson PMFs, t critical values and t-tests | 4, 5, 7, 8, 9 |
| `matplotlib` | `import matplotlib.pyplot as plt` | Bar charts and histograms | 4, 5, 6 |
| `statsmodels` | `import statsmodels.api as sm` | OLS regression intercept, slope and R-squared | 10 |

`scipy.stats`, `matplotlib.pyplot` and `statsmodels.api` are modules within these packages; install the names in the first column.

## Practical-by-practical analysis of the PDF

| No. | Topic | PDF pages | Packages imported by the PDF | Packages needed by the repository script |
| --- | --- | --- | --- | --- |
| 1 | Student-score DataFrame | 4 | pandas | pandas |
| 2 | Mean, median and mode | 5 | pandas | pandas |
| 3 | Sample variance and standard deviation | 6 | pandas | pandas |
| 4 | Binomial PMF | 7 | numpy, scipy, matplotlib | numpy, scipy, matplotlib |
| 5 | Poisson PMF | 8 | numpy, scipy, matplotlib | numpy, scipy, matplotlib |
| 6 | Central Limit Theorem simulation | 9 | numpy, matplotlib | numpy, matplotlib |
| 7 | t confidence intervals | 10-11 | pandas (duplicated, incorrect code) | numpy, scipy (corrected implementation) |
| 8 | One-sample t-test | 12 | numpy, scipy | numpy, scipy |
| 9 | Independent two-sample t-test | 13-14 | numpy, scipy | numpy, scipy |
| 10 | OLS regression | 15-16 | numpy, pandas, statsmodels | pandas, statsmodels |

Practical 7's stated aim needs confidence intervals, but the PDF repeats Practical 2's sales code and omits the weight observations. The corrected script uses NumPy and SciPy and requires weight values as command-line arguments. Its example data are illustrative. Practical 10's unused NumPy import is omitted in the repository.

## Install on Windows PowerShell

Install Python 3.12 with pip first. From the repository root:

```powershell
python -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
```

These commands use the virtual environment directly, so activation is optional. Use the same interpreter to run practicals:

```powershell
.\.venv\Scripts\python.exe practical_01_student_scores/main.py
.\.venv\Scripts\python.exe practical_04_binomial_distribution/main.py --save
.\.venv\Scripts\python.exe practical_07_confidence_intervals/main.py 248 249 250 251 252
```

The final command uses illustrative weight observations, not data from the PDF. Replace them with your actual observations.

## Install on macOS or Linux

With Python 3.12 and its venv/pip support installed, run from the repository root:

```bash
python3.12 -m venv .venv
.venv/bin/python -m pip install -r requirements.txt
.venv/bin/python practical_01_student_scores/main.py
```

## Check the installation

On Windows:

```powershell
.\.venv\Scripts\python.exe -m pip check
.\.venv\Scripts\python.exe -c "import numpy, pandas, scipy.stats, matplotlib.pyplot, statsmodels.api; print('All dependencies imported successfully')"
```

On macOS/Linux, replace `.\.venv\Scripts\python.exe` with `.venv/bin/python`.

Pip automatically installs the packages' own dependencies. The scripts' `argparse` and `pathlib` imports are included with Python. All supplied datasets are written directly in the scripts, except Practical 7's missing weight data. Running the scripts does not require reading the PDF or installing PDF-processing software.

Practicals 4-6 open chart windows by default. Use `--save` in a terminal without a graphical display to write `chart.png` in the practical's folder.
