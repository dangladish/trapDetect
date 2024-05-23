
<!-- README.md is generated from README.Rmd. Please edit that file -->

# trapDetect

<!-- badges: start -->

[![R-CMD-check](https://github.com/dangladish/trapDetect/actions/workflows/R-CMD-check.yaml/badge.svg)](https://github.com/dangladish/trapDetect/actions/workflows/R-CMD-check.yaml)
<!-- badges: end -->

The goal of trapDetect is to provide the functionality to simulate the
spread of individuals over a given area (such as an orchard or block),
and provide the tools to determine the probability of detecting a pest
using various detection functions.

## Installation

You can install trapDetect from [GitHub](https://github.com/) with:

``` r
# install.packages("devtools")
devtools::install_github("dangladish/trapDetect")
```

Please note that `trapDetect` is in development.

## The main function: `calc_escape_prob()`

The main function is `calc_escape_prob()` which simulates the spread of
a population of individuals using the `sim_spread()` function if not
provided, and then determines the probability of detecting an individual
for a given trap configuration using `p_detect_one()`. There are a
number of optional arguments in `calc_escape_prob()` which the user can
set for their own purposes. A basic example can be run using the
following code:

``` r
library(trapDetect)
calc_escape_prob()
#> [1] "Warning: generating survey and raster..."
#> [1] "No initial data detected, generating random simulations"
#> $mean_prob
#>  [1] 0.008025985 0.022811375 0.025216805 0.026701872 0.027208147 0.028407272
#>  [7] 0.028718021 0.028982756 0.029556890 0.029745062 0.030297559
#> 
#> $probs
#>             [,1]       [,2]        [,3]        [,4]        [,5]        [,6]
#> [1,] 0.002963116 0.00395469 0.004432051 0.005065513 0.005220681 0.005389026
#> [2,] 0.013088855 0.04166806 0.046001558 0.048338230 0.049195613 0.051425518
#>             [,7]        [,8]        [,9]       [,10]       [,11]
#> [1,] 0.005492172 0.005706086 0.006495641 0.006742153 0.007640417
#> [2,] 0.051943869 0.052259426 0.052618140 0.052747970 0.052954702
```

## Simulate Capture: `sim_capture()`

The `sim_capture()` focuses on trap catch counts rather than probability
of capture. This function acts in a similar manner as `sim_spread()` but
needs information about detection devices. This can be in the form of
trap locations or number of traps in the space. If number of traps is
specified, traps are arranged in a grid covering the block as much as
possible.

## Contact

For all inquires regarding the `trapDetect` R package, please contact:
Dan Gladish (<Dan.Gladish@data61.csiro.au>).
