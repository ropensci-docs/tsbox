# Change Frequency

Changes the frequency of a time series. By default, incomplete periods
of regular series are omitted.

## Usage

``` r
ts_frequency(
  x,
  to = c("year", "quarter", "month", "week", "day", "hour", "min", "sec"),
  aggregate = "mean",
  na.rm = FALSE
)
```

## Arguments

- x:

  ts-boxable time series, an object of class `ts`, `xts`, `zoo`,
  `zooreg`, `data.frame`, `data.table`, `tbl`, `tbl_ts`, `tbl_time`,
  `tis`, `irts` or `timeSeries`.

- to:

  desired frequency, either a character string (`"year"`, `"quarter"`,
  `"month"`) or an integer (`1`, `4`, `12`).

- aggregate:

  character string, or function. Either `"mean"`, `"sum"`, `"first"`, or
  `"last"`, or any aggregate function, such as
  [`base::mean()`](https://rdrr.io/r/base/mean.html).

- na.rm:

  logical, if `TRUE`, incomplete periods are aggregated as well. For
  irregular series, incomplete periods are always aggregated.

## Value

a ts-boxable time series, with the same class as the input.

## Details

The [tempdisagg package](https://CRAN.R-project.org/package=tempdisagg)
can convert low frequency to high frequency data and has support for
ts-boxable objects. See
[`vignette("hf-disagg", package = "tempdisagg")`](http://cynkra.github.io/tempdisagg/articles/hf-disagg.md).

## Examples

``` r
# \donttest{
ts_frequency(cbind(mdeaths, fdeaths), "year", "sum")
#> Time Series:
#> Start = 1974 
#> End = 1979 
#> Frequency = 1 
#>      mdeaths fdeaths
#> 1974   19071    7069
#> 1975   19247    6854
#> 1976   18697    7021
#> 1977   16927    6302
#> 1978   17329    6622
#> 1979   16437    6501
ts_frequency(cbind(mdeaths, fdeaths), "quarter", "last")
#>         mdeaths fdeaths
#> 1974 Q1    1877     827
#> 1974 Q2    1249     406
#> 1974 Q3    1209     387
#> 1974 Q4    1846     666
#> 1975 Q1    2153     785
#> 1975 Q2    1288     438
#> 1975 Q3    1053     343
#> 1975 Q4    2066     771
#> 1976 Q1    2283     896
#> 1976 Q2    1160     420
#> 1976 Q3     999     357
#> 1976 Q4    2059     764
#> 1977 Q1    1722     663
#> 1977 Q2    1162     392
#> 1977 Q3     959     387
#> 1977 Q4    1655     638
#> 1978 Q1    1942     737
#> 1978 Q2    1187     446
#> 1978 Q3     970     387
#> 1978 Q4    1812     679
#> 1979 Q1    1846     727
#> 1979 Q2    1075     429
#> 1979 Q3     940     393
#> 1979 Q4    1341     574

ts_frequency(AirPassengers, 4, "sum")
#>      Qtr1 Qtr2 Qtr3 Qtr4
#> 1949  362  385  432  341
#> 1950  382  409  498  387
#> 1951  473  513  582  474
#> 1952  544  582  681  557
#> 1953  628  707  773  592
#> 1954  627  725  854  661
#> 1955  742  854 1023  789
#> 1956  878 1005 1173  883
#> 1957  972 1125 1336  988
#> 1958 1020 1146 1400 1006
#> 1959 1108 1288 1570 1174
#> 1960 1227 1468 1736 1283

# Note that incomplete years are omited by default
ts_frequency(EuStockMarkets, "year")
#> Time Series:
#> Start = 1992 
#> End = 1997 
#> Frequency = 1 
#>           DAX      SMI      CAC     FTSE
#> 1992 1637.459 1854.162 1852.869 2559.458
#> 1993 1802.471 2372.175 2015.391 2957.114
#> 1994 2123.445 2716.570 2061.115 3144.673
#> 1995 2135.226 2824.320 1872.022 3343.207
#> 1996 2560.317 3610.032 2071.866 3821.407
#> 1997 3694.279 5173.600 2745.503 4673.295
ts_frequency(EuStockMarkets, "year", na.rm = TRUE)
#> Time Series:
#> Start = 1991 
#> End = 1998 
#> Frequency = 1 
#>           DAX      SMI      CAC     FTSE
#> 1991 1602.058 1686.485 1795.779 2541.689
#> 1992 1637.459 1854.162 1852.869 2559.458
#> 1993 1802.471 2372.175 2015.391 2957.114
#> 1994 2123.445 2716.570 2061.115 3144.673
#> 1995 2135.226 2824.320 1872.022 3343.207
#> 1996 2560.317 3610.032 2071.866 3821.407
#> 1997 3694.279 5173.600 2745.503 4673.295
#> 1998 5162.252 7339.186 3723.700 5751.889
# }
```
