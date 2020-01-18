
<!-- README.md is generated from README.Rmd. Please edit that file -->

# SimHelpers

<!-- badges: start -->

<!-- badges: end -->

Simulations are experiments to study performance of statistical methods
under known data-generating conditions (Morris, White and Crowther,
2018). Methodologists examine questions like: (1) how does ordinary
least squares (OLS) regression perform if errors are heteroskedastic?
(2) how does the presence of missing data affect treatment effect
estimates from a propensity score analysis? To answer such questions, we
conduct experiments by simulating thousands of datasets from
pseudo-random sampling (Morris et al., 2018). We generate datasets under
known conditions. For example, we can generate data where the errors are
heteroskedastic or there is missing data present following Missing at
Random (MAR) mechanism. Then, we apply statistical methods, like OLS, to
each of the datasets and extract measures like mean difference,
regression coefficients, p values, and confidence intervals. We then
analyze the methods using performance criteria measures like bias, Type
1 error rate etc.

When examining performance measures, we need to also consider the error
in the estimate of the performance measures due to the fact that we
generate a finite number of samples. The error is quantified in the form
of Monte Carlo standard error (MCSE).

The goal of `SimHelpers` is to assist in running simulation studies.
This package provides a set of functions that calculates various
performance measures and associated MCSE. The functions are divided into
broad four categories: absolute criteria, relative criteria, rejection
rate and confidence interval coverage. The functions are:

  - `calc_abs` : Absolute criteria (bias, variance, mse, rmse)
  - `calc_relative`: Relative criteria (relative bias, relative mse)
  - `calc_rr`: Rejection rate (Type 1 error rate, power)
  - `calc_coverage`: Confidence interval coverage (coverage, width)

The functions are created to work with `tidyeval` practice using
packages like `dplyr`. The package
[vignette](https://github.com/meghapsimatrix/SimHelpers/blob/master/vignettes/MCSE.Rmd)
covers details about MCSE and the formulas used to calculate them. The
vignette also includes examples on how to use the functions with `dplyr`
workflow.

In addition to the set of functions that calculates performance measures
and MCSE, the package also includes a function, `create_skeleton`, that
generates a skeleton outline of a simulation study that can be applied
when designing one. Another function, `evaluate_by_row` runs the
simulation for each combination of conditions row by row. Lastly, the
`start_parallel` function sets up parallel processing.

The package also contains several datasets that contain results from
example simulation studies. The code used to generate the data is
available
[here](https://github.com/meghapsimatrix/SimHelpers/tree/master/data-raw).

The package is still under development. We will be updating and adding
functions in the near future.

## Installation

You can install the development version from
[GitHub](https://github.com/) with:

``` r
# install.packages("devtools")
devtools::install_github("meghapsimatrix/SimHelpers")
```
