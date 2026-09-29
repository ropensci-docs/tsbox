# Internal Time Series Class

In data frame objects (`data.frame`, `tibble`, `data.table`), tsbox
automatically detects the time and the value column. This function
changes the column names to the defaults (`time`, `value`), so that
auto-detection can be avoided in future operations.

## Usage

``` r
ts_dts(x)
```

## Arguments

- x:

  ts-boxable time series, an object of class `ts`, `xts`, `zoo`,
  `zooreg`, `data.frame`, `data.table`, `tbl`, `tbl_ts`, `tbl_time`,
  `tis`, `irts` or `timeSeries`.

## Value

a ts-boxable object of the same class as `x`, i.e., an object of class
`ts`, `xts`, `zoo`, `zooreg`, `data.frame`, `data.table`, `tbl`,
`tbl_ts`, `tbl_time`, `tis`, `irts` or `timeSeries`.

## Examples

``` r
# \donttest{
df <- ts_df(ts_c(mdeaths, fdeaths))
# non-default colnames
colnames(df) <- c("id", "date", "count")
# switch back to default colnames
ts_default(df)
#> [time]: 'date' [value]: 'count' 
#>          id       time value
#> 1   mdeaths 1974-01-01  2134
#> 2   mdeaths 1974-02-01  1863
#> 3   mdeaths 1974-03-01  1877
#> 4   mdeaths 1974-04-01  1877
#> 5   mdeaths 1974-05-01  1492
#> 6   mdeaths 1974-06-01  1249
#> 7   mdeaths 1974-07-01  1280
#> 8   mdeaths 1974-08-01  1131
#> 9   mdeaths 1974-09-01  1209
#> 10  mdeaths 1974-10-01  1492
#> 11  mdeaths 1974-11-01  1621
#> 12  mdeaths 1974-12-01  1846
#> 13  mdeaths 1975-01-01  2103
#> 14  mdeaths 1975-02-01  2137
#> 15  mdeaths 1975-03-01  2153
#> 16  mdeaths 1975-04-01  1833
#> 17  mdeaths 1975-05-01  1403
#> 18  mdeaths 1975-06-01  1288
#> 19  mdeaths 1975-07-01  1186
#> 20  mdeaths 1975-08-01  1133
#> 21  mdeaths 1975-09-01  1053
#> 22  mdeaths 1975-10-01  1347
#> 23  mdeaths 1975-11-01  1545
#> 24  mdeaths 1975-12-01  2066
#> 25  mdeaths 1976-01-01  2020
#> 26  mdeaths 1976-02-01  2750
#> 27  mdeaths 1976-03-01  2283
#> 28  mdeaths 1976-04-01  1479
#> 29  mdeaths 1976-05-01  1189
#> 30  mdeaths 1976-06-01  1160
#> 31  mdeaths 1976-07-01  1113
#> 32  mdeaths 1976-08-01   970
#> 33  mdeaths 1976-09-01   999
#> 34  mdeaths 1976-10-01  1208
#> 35  mdeaths 1976-11-01  1467
#> 36  mdeaths 1976-12-01  2059
#> 37  mdeaths 1977-01-01  2240
#> 38  mdeaths 1977-02-01  1634
#> 39  mdeaths 1977-03-01  1722
#> 40  mdeaths 1977-04-01  1801
#> 41  mdeaths 1977-05-01  1246
#> 42  mdeaths 1977-06-01  1162
#> 43  mdeaths 1977-07-01  1087
#> 44  mdeaths 1977-08-01  1013
#> 45  mdeaths 1977-09-01   959
#> 46  mdeaths 1977-10-01  1179
#> 47  mdeaths 1977-11-01  1229
#> 48  mdeaths 1977-12-01  1655
#> 49  mdeaths 1978-01-01  2019
#> 50  mdeaths 1978-02-01  2284
#> 51  mdeaths 1978-03-01  1942
#> 52  mdeaths 1978-04-01  1423
#> 53  mdeaths 1978-05-01  1340
#> 54  mdeaths 1978-06-01  1187
#> 55  mdeaths 1978-07-01  1098
#> 56  mdeaths 1978-08-01  1004
#> 57  mdeaths 1978-09-01   970
#> 58  mdeaths 1978-10-01  1140
#> 59  mdeaths 1978-11-01  1110
#> 60  mdeaths 1978-12-01  1812
#> 61  mdeaths 1979-01-01  2263
#> 62  mdeaths 1979-02-01  1820
#> 63  mdeaths 1979-03-01  1846
#> 64  mdeaths 1979-04-01  1531
#> 65  mdeaths 1979-05-01  1215
#> 66  mdeaths 1979-06-01  1075
#> 67  mdeaths 1979-07-01  1056
#> 68  mdeaths 1979-08-01   975
#> 69  mdeaths 1979-09-01   940
#> 70  mdeaths 1979-10-01  1081
#> 71  mdeaths 1979-11-01  1294
#> 72  mdeaths 1979-12-01  1341
#> 73  fdeaths 1974-01-01   901
#> 74  fdeaths 1974-02-01   689
#> 75  fdeaths 1974-03-01   827
#> 76  fdeaths 1974-04-01   677
#> 77  fdeaths 1974-05-01   522
#> 78  fdeaths 1974-06-01   406
#> 79  fdeaths 1974-07-01   441
#> 80  fdeaths 1974-08-01   393
#> 81  fdeaths 1974-09-01   387
#> 82  fdeaths 1974-10-01   582
#> 83  fdeaths 1974-11-01   578
#> 84  fdeaths 1974-12-01   666
#> 85  fdeaths 1975-01-01   830
#> 86  fdeaths 1975-02-01   752
#> 87  fdeaths 1975-03-01   785
#> 88  fdeaths 1975-04-01   664
#> 89  fdeaths 1975-05-01   467
#> 90  fdeaths 1975-06-01   438
#> 91  fdeaths 1975-07-01   421
#> 92  fdeaths 1975-08-01   412
#> 93  fdeaths 1975-09-01   343
#> 94  fdeaths 1975-10-01   440
#> 95  fdeaths 1975-11-01   531
#> 96  fdeaths 1975-12-01   771
#> 97  fdeaths 1976-01-01   767
#> 98  fdeaths 1976-02-01  1141
#> 99  fdeaths 1976-03-01   896
#> 100 fdeaths 1976-04-01   532
#> 101 fdeaths 1976-05-01   447
#> 102 fdeaths 1976-06-01   420
#> 103 fdeaths 1976-07-01   376
#> 104 fdeaths 1976-08-01   330
#> 105 fdeaths 1976-09-01   357
#> 106 fdeaths 1976-10-01   445
#> 107 fdeaths 1976-11-01   546
#> 108 fdeaths 1976-12-01   764
#> 109 fdeaths 1977-01-01   862
#> 110 fdeaths 1977-02-01   660
#> 111 fdeaths 1977-03-01   663
#> 112 fdeaths 1977-04-01   643
#> 113 fdeaths 1977-05-01   502
#> 114 fdeaths 1977-06-01   392
#> 115 fdeaths 1977-07-01   411
#> 116 fdeaths 1977-08-01   348
#> 117 fdeaths 1977-09-01   387
#> 118 fdeaths 1977-10-01   385
#> 119 fdeaths 1977-11-01   411
#> 120 fdeaths 1977-12-01   638
#> 121 fdeaths 1978-01-01   796
#> 122 fdeaths 1978-02-01   853
#> 123 fdeaths 1978-03-01   737
#> 124 fdeaths 1978-04-01   546
#> 125 fdeaths 1978-05-01   530
#> 126 fdeaths 1978-06-01   446
#> 127 fdeaths 1978-07-01   431
#> 128 fdeaths 1978-08-01   362
#> 129 fdeaths 1978-09-01   387
#> 130 fdeaths 1978-10-01   430
#> 131 fdeaths 1978-11-01   425
#> 132 fdeaths 1978-12-01   679
#> 133 fdeaths 1979-01-01   821
#> 134 fdeaths 1979-02-01   785
#> 135 fdeaths 1979-03-01   727
#> 136 fdeaths 1979-04-01   612
#> 137 fdeaths 1979-05-01   478
#> 138 fdeaths 1979-06-01   429
#> 139 fdeaths 1979-07-01   405
#> 140 fdeaths 1979-08-01   379
#> 141 fdeaths 1979-09-01   393
#> 142 fdeaths 1979-10-01   411
#> 143 fdeaths 1979-11-01   487
#> 144 fdeaths 1979-12-01   574
# }
```
