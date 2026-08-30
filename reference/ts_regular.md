# Enforce Regularity

Enforces regularity in data frame and `xts` objects, by turning implicit
`NA`s into explicit `NA`s. In `ts` objects, regularity is automatically
enforced.

## Usage

``` r
ts_regular(x, fill = NA)
```

## Arguments

- x:

  ts-boxable time series, an object of class `ts`, `xts`, `zoo`,
  `zooreg`, `data.frame`, `data.table`, `tbl`, `tbl_ts`, `tbl_time`,
  `tis`, `irts` or `timeSeries`.

- fill:

  numeric, instead of `NA`, an alternative value can be specified. E.g.,
  0, -99.

## Value

a ts-boxable object of the same class as `x`, i.e., an object of class
`ts`, `xts`, `zoo`, `zooreg`, `data.frame`, `data.table`, `tbl`,
`tbl_ts`, `tbl_time`, `tis`, `irts` or `timeSeries`.

## Examples

``` r
x0 <- AirPassengers
x0[c(10, 15)] <- NA
x <- ts_na_omit(ts_dts(x0))
ts_regular(x)
#>            time value
#>          <Date> <num>
#>   1: 1949-01-01   112
#>   2: 1949-02-01   118
#>   3: 1949-03-01   132
#>   4: 1949-04-01   129
#>   5: 1949-05-01   121
#>  ---                 
#> 140: 1960-08-01   606
#> 141: 1960-09-01   508
#> 142: 1960-10-01   461
#> 143: 1960-11-01   390
#> 144: 1960-12-01   432
ts_regular(x, fill = 0)
#>            time value
#>          <Date> <num>
#>   1: 1949-01-01   112
#>   2: 1949-02-01   118
#>   3: 1949-03-01   132
#>   4: 1949-04-01   129
#>   5: 1949-05-01   121
#>  ---                 
#> 140: 1960-08-01   606
#> 141: 1960-09-01   508
#> 142: 1960-10-01   461
#> 143: 1960-11-01   390
#> 144: 1960-12-01   432

m <- mdeaths
m[c(10, 69)] <- NA
f <- fdeaths
f[c(1, 3, 15)] <- NA

ts_regular(ts_na_omit(ts_dts(ts_c(f, m))))
#>          id       time value
#>      <char>     <Date> <num>
#>   1:      f 1974-02-01   689
#>   2:      f 1974-03-01    NA
#>   3:      f 1974-04-01   677
#>   4:      f 1974-05-01   522
#>   5:      f 1974-06-01   406
#>  ---                        
#> 139:      m 1979-08-01   975
#> 140:      m 1979-09-01    NA
#> 141:      m 1979-10-01  1081
#> 142:      m 1979-11-01  1294
#> 143:      m 1979-12-01  1341
```
