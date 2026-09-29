# Loess Trend Estimation

Trend estimation that uses
[`stats::loess()`](https://rdrr.io/r/stats/loess.html).

## Usage

``` r
ts_trend(x, ...)
```

## Arguments

- x:

  ts-boxable time series, an object of class `ts`, `xts`, `zoo`,
  `zooreg`, `data.frame`, `data.table`, `tbl`, `tbl_ts`, `tbl_time`,
  `tis`, `irts` or `timeSeries`.

- ...:

  arguments, passed to
  [`stats::loess()`](https://rdrr.io/r/stats/loess.html):

  - `degree` degree of Loess smoothing

  - `span` smoothing parameter, if `NULL`, an automated search performed
    (see Details)

## Value

a ts-boxable object of the same class as `x`, i.e., an object of class
`ts`, `xts`, `zoo`, `zooreg`, `data.frame`, `data.table`, `tbl`,
`tbl_ts`, `tbl_time`, `tis`, `irts` or `timeSeries`.

## References

Cleveland, William S., Eric Grosse, and William M. Shyu. "Local
regression models." Statistical models in S. Routledge, 2017. 309-376.

## Examples

``` r
# \donttest{
ts_plot(
  `Raw series` = fdeaths,
  `Loess trend` = ts_trend(fdeaths),
  title = "Deaths from Lung Diseases",
  subtitle = "per month"
)

# }
```
