# Load images from files

A wrap around
[`image_read`](https://docs.ropensci.org/magick/reference/editing.html)
and [`magick2cimg`](https://rdrr.io/pkg/imager/man/magick.html) to load
one or more images from files.

## Usage

``` r
image_load(image_file)
```

## Arguments

- image_file:

  A `character` vector of one or more paths to image files

## Value

A `cimg` object or a `list` of `cimg` objects when multiple files are
passed to `image_file`.

## Examples

``` r
# load image
fl <- system.file('extdata', 'Image0001_.jpg', package = 'colocr')
img <- image_load(fl)
```
