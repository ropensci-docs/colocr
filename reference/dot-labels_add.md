# Label regions of interest

Add labels to regions of interest in an image

## Usage

``` r
.labels_add(px, tolerance, n)
```

## Arguments

- px:

  An object of class
  [`pixset`](https://rdrr.io/pkg/imager/man/pixset.html)

- tolerance:

  A `numeric` to be passed to
  [`label`](https://rdrr.io/pkg/imager/man/label.html)

- n:

  A `numeric`, the number of desired regions of interest

## Value

An object of class [`cimg`](https://rdrr.io/pkg/imager/man/cimg.html).
The labels are coded the values in the object starting from 1. The rest
of the image is labeled 0.
