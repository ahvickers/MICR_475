Homework 5
================

``` r
library(tidyverse)
```

## 1.

``` r
diamonds %>%
  group_by(cut) %>%
  summarise(n = n())
```

    ## # A tibble: 5 × 2
    ##   cut           n
    ##   <ord>     <int>
    ## 1 Fair       1610
    ## 2 Good       4906
    ## 3 Very Good 12082
    ## 4 Premium   13791
    ## 5 Ideal     21551

## 2.

``` r
diamonds %>%
  slice_sample(prop = 0.01)
```

    ## # A tibble: 539 × 10
    ##    carat cut       color clarity depth table price     x     y     z
    ##    <dbl> <ord>     <ord> <ord>   <dbl> <dbl> <int> <dbl> <dbl> <dbl>
    ##  1  0.41 Premium   D     SI1      62.1    59  1015  4.76  4.74  2.95
    ##  2  0.51 Ideal     I     SI2      62.2    55   913  5.14  5.15  3.2 
    ##  3  1.21 Fair      H     SI2      65.6    56  3862  6.69  6.59  4.36
    ##  4  1.5  Very Good D     SI1      63.1    57 11863  7.31  7.24  4.59
    ##  5  0.55 Ideal     F     SI1      61.7    56  1718  5.3   5.26  3.25
    ##  6  0.33 Ideal     H     VS2      60.7    57   521  4.45  4.48  2.71
    ##  7  1.2  Premium   H     VS2      62.8    59  6500  6.75  6.7   4.22
    ##  8  0.66 Premium   E     SI1      61.1    56  1708  5.68  5.62  3.45
    ##  9  0.3  Very Good G     VVS2     60.4    60   638  4.3   4.34  2.61
    ## 10  0.3  Ideal     G     VVS1     61.6    58   764  4.31  4.32  2.66
    ## # … with 529 more rows

## 3.

``` r
diamonds %>%
  group_by(clarity) %>%
  slice_max(order_by = carat, n = 100, with_ties = FALSE) %>%
  summarise(avg.size = mean(carat))
```

    ## # A tibble: 8 × 2
    ##   clarity avg.size
    ##   <ord>      <dbl>
    ## 1 I1          2.51
    ## 2 SI2         2.62
    ## 3 SI1         2.30
    ## 4 VS2         2.23
    ## 5 VS1         2.10
    ## 6 VVS2        1.66
    ## 7 VVS1        1.51
    ## 8 IF          1.40

## 4.

``` r
ggplot(diamonds, aes(x = x, y = y)) +
  geom_point()
```

![](hw_5_files/figure-gfm/plot_dimensions-1.png)<!-- -->

``` r
ggplot(diamonds, aes(x = x, y = z)) +
  geom_point()
```

![](hw_5_files/figure-gfm/plot_dimensions-2.png)<!-- -->

## 5.

``` r
diamonds_dubious_pts_rmvd <- diamonds %>%
  filter(!(x <= 0 | y <= 0 | z <= 0 | y > 20 | z > 10))

ggplot(diamonds_dubious_pts_rmvd, aes(x = x, y = y)) +
  geom_point()
```

![](hw_5_files/figure-gfm/filter_sus_removed-1.png)<!-- -->

``` r
ggplot(diamonds_dubious_pts_rmvd, aes(x = x, y = z)) +
  geom_point()
```

![](hw_5_files/figure-gfm/filter_sus_removed-2.png)<!-- -->
