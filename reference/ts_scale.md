# Scale and Center Time Series

Subtract mean (*sum(x)/n*) and divide by standard deviation
(*sqrt(sum(x^2)/(n-1))*). Based on
[`base::scale()`](https://rdrr.io/r/base/scale.html).

## Usage

``` r
ts_scale(x, center = TRUE, scale = TRUE)
```

## Arguments

- x:

  ts-boxable time series, an object of class `ts`, `xts`, `zoo`,
  `zooreg`, `data.frame`, `data.table`, `tbl`, `tbl_ts`, `tbl_time`,
  `tis`, `irts` or `timeSeries`.

- center:

  logical

- scale:

  logical

## Value

a ts-boxable object of the same class as `x`, i.e., an object of class
`ts`, `xts`, `zoo`, `zooreg`, `data.frame`, `data.table`, `tbl`,
`tbl_ts`, `tbl_time`, `tis`, `irts` or `timeSeries`.

## Examples

``` r
# \donttest{
ts_plot(ts_scale((ts_c(airmiles, co2, JohnsonJohnson, discoveries))))

ts_plot(ts_scale(ts_c(AirPassengers, DAX = EuStockMarkets[, "DAX"])))

# }
```
