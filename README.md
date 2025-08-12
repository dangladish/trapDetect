
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
#>  [1] 0.01152833 0.03978443 0.18930905 0.20907187 0.21449004 0.22445540
#>  [7] 0.24817596 0.27109780 0.27547246 0.28281291 0.28511016
#> 
#> $probs
#>              [,1]         [,2]        [,3]        [,4]        [,5]        [,6]
#> [1,] 0.0003720342 0.0006133695 0.001590724 0.001811953 0.001912382 0.002095057
#> [2,] 0.0226846321 0.0789554859 0.377027376 0.416331785 0.427067698 0.446815745
#>             [,7]        [,8]        [,9]       [,10]       [,11]
#> [1,] 0.002672586 0.003568729 0.004298199 0.005563935 0.006909465
#> [2,] 0.493679340 0.538626875 0.546646722 0.560061880 0.563310865
```

## Simulate Capture: `sim_capture()`

The `sim_capture()` focuses on trap catch counts rather than probability
of capture. This function acts in a similar manner as `sim_spread()` but
needs information about detection devices. This can be in the form of
trap locations or number of traps in the space. If number of traps is
specified, traps are arranged in a grid covering the block as much as
possible. It is recommended to run `sim_capture()` multiple times for
uncertainty estimates.

## Contact

For all inquires regarding the `trapDetect` R package, please contact:
Dan Gladish (<Dan.Gladish@data61.csiro.au>).
