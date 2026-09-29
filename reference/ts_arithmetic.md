# Arithmetic Operators for ts-boxable objects

Arithmetic Operators for ts-boxable objects

## Usage

``` r
e1 %ts+% e2

e1 %ts-% e2

e1 %ts*% e2

e1 %ts/% e2
```

## Arguments

- e1:

  ts-boxable time series, an object of class `ts`, `xts`, `zoo`,
  `zooreg`, `data.frame`, `data.table`, `tbl`, `tbl_ts`, `tbl_time`,
  `tis`, `irts` or `timeSeries`.

- e2:

  ts-boxable time series, an object of class `ts`, `xts`, `zoo`,
  `zooreg`, `data.frame`, `data.table`, `tbl`, `tbl_ts`, `tbl_time`,
  `tis`, `irts` or `timeSeries`.

## Value

a ts-boxable time series, with the same class as the left input.

## Examples

``` r
head(fdeaths - mdeaths)
#>        Jan   Feb   Mar   Apr   May   Jun
#> 1974 -1233 -1174 -1050 -1200  -970  -843
head(fdeaths %ts-% mdeaths)
#>        Jan   Feb   Mar   Apr   May   Jun
#> 1974 -1233 -1174 -1050 -1200  -970  -843
head(ts_df(fdeaths) %ts-% mdeaths)
#>         time value
#> 1 1974-01-01 -1233
#> 2 1974-02-01 -1174
#> 3 1974-03-01 -1050
#> 4 1974-04-01 -1200
#> 5 1974-05-01  -970
#> 6 1974-06-01  -843
```
