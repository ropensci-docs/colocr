# Show the selected regions of interest

Show/highlight the selected regions of interest on different image
channels

## Usage

``` r
roi_show(img, ind = c(1, 2))
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

calling this function with `img` object which is returned from
[`roi_select`](https://docs.ropensci.org/colocr/reference/roi_select.md)
returns four different plots. The original image, a low resolution
representation of the selected regions of interest and the two channels
indicated through `ind` highlighted.

## Examples

``` r
# load images
fl <- system.file('extdata', 'Image0001_.jpg', package = 'colocr')
img <- image_load(fl)

# choose and show ROI
oldpar <- par()
par(mfrow=c(2,2))

roi_select(img, threshold = 90) %>%
  roi_show()


par(oldpar)
#> Warning: graphical parameter "cin" cannot be set
#> Warning: graphical parameter "cra" cannot be set
#> Warning: graphical parameter "csi" cannot be set
#> Warning: graphical parameter "cxy" cannot be set
#> Warning: graphical parameter "din" cannot be set
#> Warning: graphical parameter "page" cannot be set
```
