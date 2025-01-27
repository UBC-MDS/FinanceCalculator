# **FinanceCalculator**

------------------------------------------------------------------------
[![Documentation Status](https://readthedocs.org/projects/financecalculator/badge/?version=latest)](https://financecalculator.readthedocs.io/en/latest/?badge=latest)
[![codecov](https://codecov.io/gh/UBC-MDS/FinanceCalculator/graph/badge.svg?token=n9iRr2joRS)](https://codecov.io/gh/UBC-MDS/FinanceCalculator)

<img src="https://github.com/UBC-MDS/FinanceCalculator/blob/main/img/finance-calculator-200px.png?raw=true">

## Project Summary

**`FinanceCalculator`** is a Python package for calculating financial metrics specifically designed for loans or investment scenarios.\
This package serves as a convenient tool for managing personal finances, offering functionalities such as Contribution, Future Value, Present Value, and Number of Periods Calculations

------------------------------------------------------------------------

## Contributors

-   Chaoyu Ou [Shell-human](https://github.com/Shell-human)
-   Meagan Gardner [meagangardner](https://github.com/meagangardner)
-   Ziming Fang [ethanfang08](https://github.com/ethanfang08)
-   Zoe Ren [sgdkd](https://github.com/sgdkd)

------------------------------------------------------------------------

## Installation

``` bash
$ pip install financecalculator
```

------------------------------------------------------------------------

## Package Content

This package offers four key functions:

### **Functions:**

1.  **`calculate_contribution`:** Calculates the periodic payment (contribution) required to pay off a loan or reach a specified future value over a given number of periods.
2.  **`future_value`:** Calculates the future value of an investment or loan, factoring in optional periodic contributions.
3.  **`present_value`:** Calculates the present value of an investment or loan, considering optional monthly contributions.
4.  **`n_periods`:** Calculates the number of periods (in months) required to reach a specified future value, given an initial principal, an annual interest rate, and optional monthly contributions.

------------------------------------------------------------------------

### **Common Parameters:**

-   **`principal`** *(float)*:\
    The initial investment or loan amount (also known as Present Value in financial terms).

-   **`future_value`** *(float)*:\
    The desired amount at the end of the calculation period (e.g., remaining loan balance or target savings).

-   **`annual_rate`** *(float)*:\
    Annual interest rate expressed as a percentage (e.g., 5 for 5%).

-   **`n_periods`** *(int)*:\
    Total number of periods (typically in months) over which the calculation will be performed.

-   **`contribution`** *(float, optional)*:\
    The amount paid or contributed per period (e.g., monthly contributions). Defaults to 0 if not provided.

------------------------------------------------------------------------

## Python Ecosystem

The `FinanceCalculator` package situates itself within the Python ecosystem as a learning-oriented initiative aimed at developing practical skills in financial computation and programming. While the Python ecosystem already includes robust packages and applications like [Loan Calculator](https://github.com/yanomateus/loan-calculator) and [Financial Calculator App](https://github.com/dilumdesilva/Financial-Calculator-App), this project differentiates itself by offering an accessible, user-friendly tools that simplifies core financial concepts. With intuitive function names like calculate_contribution, future_value, and present_value, it allows users — especially beginners and students — to quickly grasp the essentials without needing to understand complex financial formulas. This project also serves as a hands-on exercise for those eager to deepen their understanding of both finance and Python programming, making it a valuable resource for anyone looking to deepen their understanding of financial concepts and Python development.

------------------------------------------------------------------------

## Developer Note
1. Clone this repository and navigate to the project root directory.

2. Create a new virtual environment in terminal and activate it:
```
conda create --name financecalculator python=3.11.0
conda activate financecalculator
```

3. To install the needed packages via poetry, run the following command. If poetry hasn't been set up yet, please following [this link](https://python-poetry.org/docs/) for installtion.
```
poetry install
```
4. To test the package and check coverage, run the following command
```
pytest tests/
pytest tests/ --cov=financecalculator
```
5. The set up is done! You can now use the `FinanceCalculator` package! Please click on the function documentation at the top of this README on how to use the package.


## Usage

The `FinanceCalculator` package allows users to perform essential financial calculations conveniently. Below is a quick start example of how to use this package:

```
import pandas as pd

import financecalculator
from financecalculator.present_value import present_value
from financecalculator.future_value import future_value
from financecalculator.contribution import calculate_contribution
from financecalculator.n_periods import n_periods
```

**Calculate periodic payments for a loan:**
```
payment = calculate_contribution(principal=20000, future_value=0, annual_rate=5, n_periods=24)
```

**Calculate future value of an investment:**
```
fv = future_value(principal=5000, annual_rate=7, n_periods=36, contribution=200)
```

**Calculate present value for a target amount**
```
pv = present_value(principal=0, annual_rate=4, n_periods=12, contribution=500)
```

**Calculate the number of months to reach a goal**
```
months = n_periods(principal=10000, annual_rate=6, future_value=50000, contribution=300)
```

------------------------------------------------------------------------

## Contributing

Interested in contributing? Check out the contributing guidelines. Please note that this project is released with a Code of Conduct. By contributing to this project, you agree to abide by its terms.

------------------------------------------------------------------------

## License

`FinanceCalculator` was created by Meagan Gardner, Zoe Ren, Ziming Fang, and Chaoyu Ou. It is licensed under the terms of the MIT license.

------------------------------------------------------------------------

## Credits

`FinanceCalculator` was created with [`cookiecutter`](https://cookiecutter.readthedocs.io/en/latest/) and the `py-pkgs-cookiecutter` [template](https://github.com/py-pkgs/py-pkgs-cookiecutter).
