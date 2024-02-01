
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
result <- with(regDIF_simdata, regDIF_GVEMM(Y, D, X))
#> Running GVEMM for initial values...
#> Fitting the model using different lambdas...
#>   |                                                                              |                                                                      |   0%  |                                                                              |============                                                          |  17%  |                                                                              |=======================                                               |  33%  |                                                                              |===================================                                   |  50%  |                                                                              |===============================================                       |  67%  |                                                                              |==========================================================            |  83%  |                                                                              |======================================================================| 100%
```
