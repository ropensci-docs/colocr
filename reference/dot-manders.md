# Calculate Marnders Overlap Coefficient

Calculates the manders overlap coefficient between two numeric vectors

## Usage

``` r
.manders(r, g)
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

.manders(r, g)
#> [1] 0.4615586
```
