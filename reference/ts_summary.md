# Time Series Properties

Extract time series properties, such as the number of observations
(`obs`), the time differences between observations (`obs`), the number
of observations per year (`freq`), and the start time stamp (`start`)
and the end time stamp (`end`) of the series.

## Usage

``` r
ts_summary(x, spark = FALSE)
```

## Arguments

- x:

  ts-boxable time series, an object of class `ts`, `xts`, `zoo`,
  `zooreg`, `data.frame`, `data.table`, `tbl`, `tbl_ts`, `tbl_time`,
  `tis`, `irts` or `timeSeries`.

- spark:

  logical should an additional column with a spark-line added to the
  data frame (experimental, ASCII only on Windows.)

## Value

`ts_summary` returns a `data.frame`. Individual column can be accessed
through the `$` notation (see examples).

## Examples

``` r
ts_summary(ts_c(mdeaths, austres))
#>        id obs    diff freq      start        end
#> 1 mdeaths  72 1 month   12 1974-01-01 1979-12-01
#> 2 austres  89 3 month    4 1971-04-01 1993-04-01
ts_summary(ts_c(mdeaths, austres), spark = TRUE)
#>        id obs    diff freq      start        end      spark_line
#> 1 mdeaths  72 1 month   12 1974-01-01 1979-12-01  ⠈⠔⠢⡐⢄         
#> 2 austres  89 3 month    4 1971-04-01 1993-04-01 ⣀⣀⣀⣀⡠⠤⠤⠤⠒⠒⠒⠊⠉⠉⠉
# Extracting specific properties
ts_summary(AirPassengers)$start
#> [1] "1949-01-01"
ts_summary(AirPassengers)$freq
#> [1] 12
ts_summary(AirPassengers)$obs
#> [1] 144
```
