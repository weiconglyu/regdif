
<!-- README.md is generated from README.Rmd. Please edit that file -->

# Introduction

The goal of `regdif` is to detect differential item functioning (DIF) in
two-parameter logistic (2PL) models.

## Installation

You can install the development version of `regdif` from
[GitHub](https://github.com/) with:

``` r
# install.packages("devtools")
devtools::install_github("weiconglyu/regdif")
```

## Example

This is a basic example which shows you how to apply Gaussian
variational estimation with importance sampling to the simulated data
from the package:

``` r
library(regdif)
result <- with(regDIF_simdata, regDIF_GVEMM(Y, D, X, 'IWGVEMM', Lambda0 = c(0.3, 0.5)))
#> Running GVEMM for initial values...
#> Fitting the model using different lambdas...
#>   |                                                                              |                                                                      |   0%  |                                                                              |===================================                                   |  50%  |                                                                              |======================================================================| 100%
round(result[[1]]$beta, 3)
#>       [,1]  [,2]  [,3]  [,4]  [,5]  [,6]   [,7]   [,8]  [,9]  [,10]  [,11]
#> [1,] 0.000 0.000 0.000 0.000 0.000 0.000  0.000  0.000  0.00  0.000  0.000
#> [2,] 0.363 0.000 0.342 0.433 0.000 0.000 -0.445 -0.607 -0.43  0.000 -0.549
#> [3,] 0.896 0.348 0.930 1.206 0.968 0.642 -0.962 -1.105 -0.93 -0.687 -1.051
#>       [,12] [,13] [,14] [,15] [,16] [,17] [,18] [,19] [,20]
#> [1,]  0.000     0     0     0     0     0     0 0.000     0
#> [2,] -0.502     0     0     0     0     0     0 0.199     0
#> [3,] -0.912     0     0     0     0     0     0 0.000     0
round(result[[2]]$beta, 3)
#>       [,1] [,2]  [,3]  [,4]  [,5] [,6]   [,7]   [,8]   [,9]  [,10]  [,11]
#> [1,] 0.000    0 0.000 0.000 0.000 0.00  0.000  0.000  0.000  0.000  0.000
#> [2,] 0.000    0 0.000 0.000 0.000 0.00  0.000 -0.611  0.000  0.000  0.000
#> [3,] 0.699    0 0.747 0.928 0.964 0.59 -0.897 -1.125 -0.736 -0.713 -0.798
#>       [,12] [,13] [,14] [,15] [,16] [,17] [,18] [,19] [,20]
#> [1,]  0.000     0     0     0     0     0     0     0     0
#> [2,]  0.000     0     0     0     0     0     0     0     0
#> [3,] -0.888     0     0     0     0     0     0     0     0
```
