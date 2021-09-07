Homework 4
================

``` r
#########
# Script for Homework 4
# Abigail Vickers
#########

# Loading libraries

library(tidyverse)
library(nycflights13)

# Exercise 1

a <- 3
b <- 2
a + b
```

    ## [1] 5

``` r
# Exercise 2

sum(2,3)
```

    ## [1] 5

``` r
# Exercise 3

# Creating data frame with only flights by American Airlines
AA_flights <- filter(flights, carrier == "AA")
# Creating scatter plot
ggplot(data = AA_flights) +
  geom_point(mapping = aes(x = dep_delay, y = arr_delay))
```

    ## Warning: Removed 782 rows containing missing values (geom_point).

![](hw_4_files/figure-gfm/homework_4-1.png)<!-- -->
