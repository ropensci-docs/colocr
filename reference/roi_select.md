# Select regions of interest

Select regions of interest in an image using different morphological
operations

## Usage

``` r
roi_select(img, threshold, shrink = 5, grow = 5, fill = 5,
  clean = 5, tolerance = 0.1, n = 1)
```

## Arguments

- img:

  An object of class [`cimg`](https://rdrr.io/pkg/imager/man/cimg.html)
  or a `list` of multiple
  [`cimg`](https://rdrr.io/pkg/imager/man/cimg.html) items

- threshold:

  A `numeric` to be passed to
  [`threshold`](https://rdrr.io/pkg/imager/man/threshold.html) or a
  `vector` of values for each image in `img`

- shrink:

  A `numeric` to be passed to
  [`shrink`](https://rdrr.io/pkg/imager/man/grow.html) or a `vector` of
  values for each image in `img`

- grow:

  A `numeric` to be passed to
  [`grow`](https://rdrr.io/pkg/imager/man/grow.html) or a `vector` of
  values for each image in `img`

- fill:

  A `numeric` to be passed to
  [`fill`](https://rdrr.io/pkg/imager/man/clean.html) or a `vector` of
  values for each image in `img`

- clean:

  A `numeric` to be passed to
  [`clean`](https://rdrr.io/pkg/imager/man/clean.html) or a `vector` of
  values for each image in `img`

- tolerance:

  A `numeric` to be passed to
  [`label`](https://rdrr.io/pkg/imager/man/label.html) or a `vector` of
  values for each image in `img`

- n:

  A `numeric` of the number of regions of interest or a `vector` of
  values for each image in `img`

## Value

A [`cimg`](https://rdrr.io/pkg/imager/man/cimg.html). The original input
`img` with an additional attribute `label`. `label` is a `vector` of
`integer`s. The labels for the selected regions of interests starts from
1 and 0 is ignored. When `img` is a list, a `list` is returned.

## Details

The function applies several `imager` morphological manipulations to
select the regions of interest. These include
[`threshold`](https://rdrr.io/pkg/imager/man/threshold.html) which sets
all values below certain cut to 0;
[`shrink`](https://rdrr.io/pkg/imager/man/grow.html)/[`grow`](https://rdrr.io/pkg/imager/man/grow.html)
for pixel set dilation and erosion;
[`fill`](https://rdrr.io/pkg/imager/man/clean.html)/[`clean`](https://rdrr.io/pkg/imager/man/clean.html)
for removing isolated regions and holes. When `n` is provided, the
individual regions (connected components) are selected where `tolerance`
is used to determine if two pixels belong to the same region.

## Examples

``` r
# load images
fl <- system.file('extdata', 'Image0001_.jpg', package = 'colocr')
img <- image_load(fl)

# choose ROI
newimg <- roi_select(img, threshold = 90)

# check the ROI labels
unique(attr(newimg, 'label'))
#> [1] 0 1
```
