# Re-Class ts-Boxable Object

Copies class attributes from an existing ts-boxable series. Mainly used
internally.

## Usage

``` r
copy_class(
  x,
  template,
  preserve.mode = TRUE,
  preserve.names = FALSE,
  preserve.time = FALSE,
  preserve.attr = TRUE
)
```

## Arguments

- x:

  ts-boxable time series, an object of class `ts`, `xts`, `zoo`,
  `zooreg`, `data.frame`, `data.table`, `tbl`, `tbl_ts`, `tbl_time`,
  `tis`, `irts` or `timeSeries`.

- template:

  ts-boxable time series, an object of class `ts`, `xts`, `zoo`,
  `zooreg`, `data.frame`, `data.table`, `tbl`, `tbl_ts`, `tbl_time`,
  `tis`, `irts` or `timeSeries`.

- preserve.mode:

  should the mode the time column be preserved (data frame only)

- preserve.names:

  should the name of the time column be preserved (data frame only)

- preserve.time:

  should the values time column be preserved (data frame only)

- preserve.attr:

  should the attributes of the value column be preserved (data frame
  only)

## Value

a ts-boxable object of the same class as `template`, i.e., an object of
class `ts`, `xts`, `zoo`, `data.frame`, `data.table`, `tbl`, `tbl_ts`,
`tbl_time`, `tis`, `irts` or `timeSeries`.

## Details

Inspired by [`xts::reclass`](https://rdrr.io/pkg/xts/man/reclass.html),
which does something similar.

## Examples

``` r
copy_class(mdeaths, ts_tbl(fdeaths))
#> # A tibble: 72 × 2
#>    time       value
#>    <date>     <dbl>
#>  1 1974-01-01  2134
#>  2 1974-02-01  1863
#>  3 1974-03-01  1877
#>  4 1974-04-01  1877
#>  5 1974-05-01  1492
#>  6 1974-06-01  1249
#>  7 1974-07-01  1280
#>  8 1974-08-01  1131
#>  9 1974-09-01  1209
#> 10 1974-10-01  1492
#> # ℹ 62 more rows
```
