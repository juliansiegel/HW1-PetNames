HW 01 - Pet names
================
Julian Siegel
01/09/2023

## Load packages and data

``` r
library(tidyverse)
library(openintro)
```

## Exercises

### Exercise 1

There are 52,519 pets in the data set.

### Exercise 2

There are 7 variables in the data set.

### Exercise 3

``` r
seattlepets %>%
  count(animal_name, sort = TRUE)
```

    ## # A tibble: 13,930 × 2
    ##    animal_name     n
    ##    <chr>       <int>
    ##  1 <NA>          483
    ##  2 Lucy          439
    ##  3 Charlie       387
    ##  4 Luna          355
    ##  5 Bella         331
    ##  6 Max           270
    ##  7 Daisy         261
    ##  8 Molly         240
    ##  9 Jack          232
    ## 10 Lily          232
    ## # … with 13,920 more rows

The three most common names are N/A, Lucy, and Charlie

### Exercise 4

``` r
seattlepets %>% 
  group_by(species) %>%
  count(animal_name, sort = TRUE)
```

    ## # A tibble: 16,823 × 3
    ## # Groups:   species [4]
    ##    species animal_name     n
    ##    <chr>   <chr>       <int>
    ##  1 Cat     <NA>          406
    ##  2 Dog     Lucy          337
    ##  3 Dog     Charlie       306
    ##  4 Dog     Bella         249
    ##  5 Dog     Luna          244
    ##  6 Dog     Daisy         221
    ##  7 Dog     Cooper        189
    ##  8 Dog     Lola          187
    ##  9 Dog     Max           186
    ## 10 Dog     Molly         186
    ## # … with 16,813 more rows

``` r
seattlepets %>%
  count(species, sort = TRUE)
```

    ## # A tibble: 4 × 2
    ##   species     n
    ##   <chr>   <int>
    ## 1 Dog     35181
    ## 2 Cat     17294
    ## 3 Goat       38
    ## 4 Pig         6

``` r
seattlepets %>% 
  group_by(species) %>%
  count(animal_name, sort = TRUE) %>% 
  slice_max(n, n = 5) %>% 
  arrange(species, n)
```

    ## # A tibble: 53 × 3
    ## # Groups:   species [4]
    ##    species animal_name     n
    ##    <chr>   <chr>       <int>
    ##  1 Cat     Max            83
    ##  2 Cat     Lily           86
    ##  3 Cat     Lucy          102
    ##  4 Cat     Luna          111
    ##  5 Cat     <NA>          406
    ##  6 Dog     Daisy         221
    ##  7 Dog     Luna          244
    ##  8 Dog     Bella         249
    ##  9 Dog     Charlie       306
    ## 10 Dog     Lucy          337
    ## # … with 43 more rows

### Exercise 5

The names below the line are more common for cats than for dogs.

### Exercise 6

The relationship for the variables is positive because when a name is
more common for a cat it will generally be more common for a dog or vice
versa.
