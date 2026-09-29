# Show pixel intensities

Show the pixel intensities of certain image channels

## Usage

``` r
roi_check(img, ind = c(1, 2))
```

## Arguments

- img:

  A [`cimg`](https://rdrr.io/pkg/imager/man/cimg.html) object or a
  `list` of multiple images such as the one returned from
  [`roi_select`](https://docs.ropensci.org/colocr/reference/roi_select.md)

- ind:

  A `numeric` object of length two. For the channel indexes. or a `list`
  of similar vectors for each of `img` items.

## Details

Calling this function returns two plots. The first is a scatter plot of
the pixel intensities from two channels. The second is the density
distribution of the intensities from the two channels.

## Examples

``` r
# load images
fl <- system.file('extdata', 'Image0001_.jpg', package = 'colocr')
img <- image_load(fl)

# choose ROI and show the pixel intensities
oldpar <- par()
par(mfrow = c(1, 2))

roi_select(img, threshold = 90) %>%
  roi_check()


par(oldpar)
#> Warning: graphical parameter "cin" cannot be set
#> Warning: graphical parameter "cra" cannot be set
#> Warning: graphical parameter "csi" cannot be set
#> Warning: graphical parameter "cxy" cannot be set
#> Warning: graphical parameter "din" cannot be set
#> Warning: graphical parameter "page" cannot be set
```
