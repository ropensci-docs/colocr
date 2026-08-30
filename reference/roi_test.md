# Test Co-localization

Perform co-localization test statistics.

## Usage

``` r
roi_test(img, ind = c(1, 2), type = "pcc")
```

## Arguments

- img:

  A [`cimg`](https://rdrr.io/pkg/imager/man/cimg.html) object or a
  `list` of multiple images such as the one returned from
  [`roi_select`](https://docs.ropensci.org/colocr/reference/roi_select.md)

- ind:

  A `numeric` object of length two. For the channel indexes. or a `list`
  of similar vectors for each of `img` items.

- type:

  A `character` vector of the desired co-localization statistics.
  Default is 'pcc', other inputs are 'moc' or 'both'.

## Value

A `data.frame` or a `list` of `data.frame`s.

## Details

The co-localization stats requested in `type` is returned as a column
for each. When different labels are provided, the stats are calculated
for each label individually. When is `img` is a `list` a `list` of such
`data.frame`s is returned

## Examples

``` r
# load images
fl <- system.file('extdata', 'Image0001_.jpg', package = 'colocr')
img <- image_load(fl)

# choose roi and test colocalization
roi_select(img, threshold = 90) %>%
  roi_test()
#>         pcc
#> 1 0.9049954
```
