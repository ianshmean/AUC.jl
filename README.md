# AUC.jl

[![Build Status](https://travis-ci.org/bcbi/AUC.jl.svg?branch=master)](https://travis-ci.org/bcbi/AUC.jl)

[![codecov.io](http://codecov.io/github/bcbi/AUC.jl/coverage.svg?branch=master)](http://codecov.io/github/bcbi/AUC.jl?branch=master)

## Installation
```julia
julia> Pkg.clone("https://github.com/bcbi/AUC.jl.git")
```


## Description
This is a simple package that calculates the area under the curve (AUC) for a receiver operating characteristic curve (ROC) generated from a binary classifier. This package currently has one option for computing AUC, which is the `auc()` function.The `auc()` function should mirror the results generated by the ROCR package in R as well as the scikit-learn package in Python.


## Example
Below is an example of the use of `auc()`. We suppose the `y_score` variable contains the fitted values generated by some binary classification model.

```julia
julia> using AUC

julia> y = [0, 0, 0, 0, 0, 0, 1, 1, 1, 1, 1, 1,
            1, 1, 1, 0, 0, 0, 1, 1, 0, 1, 1, 1, 1]

julia> y_score = [0.3, 0.2, 0.3, 0.23, 0.5, 0.34, 0.45, 0.54, 0.6, 0.7, 0.8, 0.65,
                  0.5, 0.4, 0.3, 0.2, 0.6, 0.7, 0.5, 0.2, 0.1, 0.7, 0.2, 0.7, 0.4]

julia> auc(y, y_score)
```

## To Do
 1. Add alternate methods of calculating AUC for binary classifier.
 2. Add methods for multi-class problems.
 3. Confidence interval calculation
