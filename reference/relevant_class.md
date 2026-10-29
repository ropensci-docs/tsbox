# Extract Relevant Class

Mainly used internally.

## Usage

``` r
relevant_class(x)
```

## Arguments

- x:

  ts-boxable time series, an object of class `ts`, `xts`, `zoo`,
  `zooreg`, `data.frame`, `data.table`, `tbl`, `tbl_ts`, `tbl_time`,
  `tis`, `irts` or `timeSeries`.

## Value

character, the relevant class of ts-boxable object

## Examples

``` r
relevant_class(AirPassengers)
#> [1] "ts"
x <- ts_df(AirPassengers)
relevant_class(x)
#> [1] "data.frame"
```
