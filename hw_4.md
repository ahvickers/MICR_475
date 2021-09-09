Homework 4
================

``` r
# Loading libraries

library(tidyverse)
library(nycflights13)
```

## Exercise 1

``` r
a <- 3
b <- 2
print(a + b)
```

    ## [1] 5

## Exercise 2

``` r
sum(2,3)
```

    ## [1] 5

## Exercise 3

``` r
# Limiting data to only flights through American Airlines
AA_flights <- filter(flights, carrier == "AA")

ggplot(data = AA_flights) +
  geom_point(mapping = aes(x = dep_delay, y = arr_delay))
```

    ## Warning: Removed 782 rows containing missing values (geom_point).

![](hw_4_files/figure-gfm/exercise_3-1.png)<!-- -->
