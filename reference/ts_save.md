# Save Previous Plot

Save Previous Plot

## Usage

``` r
ts_save(
  filename = tempfile(fileext = ".pdf"),
  width = 10,
  height = 5,
  device = NULL,
  open = TRUE
)
```

## Arguments

- filename:

  filename

- width:

  width

- height:

  height

- device:

  device

- open:

  logical, should the saved plot be opened?

## Value

invisible `TRUE`, if successful

## Examples

``` r
# \donttest{
ts_plot(AirPassengers)

tf <- tempfile(fileext = ".pdf")
ts_save(tf)
unlink(tf)
# }
```
