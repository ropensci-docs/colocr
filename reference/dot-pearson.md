# Calculate Pearson's Correlation Coefficient

Calculates the Pearson's correlation coefficient between two numeric
vectors

## Usage

``` r
.pearson(r, g)
```

## Arguments

- r:

  A `numeric` vector

- g:

  A `numeric` vector

## Value

A `numeric` of length one.

## Examples

``` r
set.seed(123)
r <- rnorm(10)

set.seed(1234)
g <- rnorm(10)

.pearson(r, g)
#> [1] 0.53322
```
