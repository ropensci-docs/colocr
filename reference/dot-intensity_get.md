# Get pixel intensities

Get the pixel intensities of certain image channels

## Usage

``` r
.intensity_get(img, ind = c(1, 2))
```

## Arguments

- img:

  An object of class [`cimg`](https://rdrr.io/pkg/imager/man/cimg.html)

- ind:

  A `numeric` of length two for channel indexes

## Value

A `list` of three items. The first two items are the values of the pixel
intensities of the channels indicated by `ind`. The third is the labels
of the individual regions of interest.

## Examples

``` r
# load image
fl <- system.file('extdata', 'Image0001_.jpg', package = 'colocr')
img <- image_load(fl)

# choose parameters
int <- roi_select(img, threshold = 90) %>%
  .intensity_get()
```
