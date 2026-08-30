# Test if an Object is ts-Boxable

Mainly used internally.

## Usage

``` r
ts_boxable(x)

check_ts_boxable(x)
```

## Arguments

- x:

  ts-boxable time series, an object of class `ts`, `xts`, `zoo`,
  `zooreg`, `data.frame`, `data.table`, `tbl`, `tbl_ts`, `tbl_time`,
  `tis`, `irts` or `timeSeries`.

## Value

logical, either `TRUE` or `FALSE`. `check_ts_boxable()` fails if not
`TRUE`

## Examples

``` r
ts_boxable(AirPassengers)
#> [1] TRUE
ts_boxable(lm)
#> [1] FALSE
```
