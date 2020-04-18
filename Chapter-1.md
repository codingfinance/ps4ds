Chapter 1 - Exploratory Data Analysis
================

### Import the datasets needed for chapter 1

``` r
library(tidyverse)
library(DT)
```

Next we load all the data from the csv files.

``` r
state <- read_csv('psds_data/state.csv')
dfw <- read_csv('psds_data/dfw_airline.csv')
sp500_px <- read_csv('psds_data/sp500_px.csv')
sp500_sym <- read_csv('psds_data/sp500_sym.csv')
kc_tax <- read_csv('psds_data/kc_tax.csv')
lc_loans <- read_csv('psds_data/lc_loans.csv')
airline_stats <- read_csv('psds_data/airline_stats.csv')
```

``` r
head(state)
```

    ## # A tibble: 6 x 4
    ##   State      Population Murder.Rate Abbreviation
    ##   <chr>           <dbl>       <dbl> <chr>       
    ## 1 Alabama       4779736         5.7 AL          
    ## 2 Alaska         710231         5.6 AK          
    ## 3 Arizona       6392017         4.7 AZ          
    ## 4 Arkansas      2915918         5.6 AR          
    ## 5 California   37253956         4.4 CA          
    ## 6 Colorado      5029196         2.8 CO

#### Estimates of location

Now lets compute the mean and the median of the state pospulation.

``` r
print(mean(state$Population))
```

    ## [1] 6162876

``` r
print(mean(state$Population, trim = 0.1))
```

    ## [1] 4783697

``` r
print(median(state$Population))
```

    ## [1] 4436370

We can also find out the weighted mean.

``` r
weighted.mean(state$Murder.Rate, w = state$Population)
```

    ## [1] 4.445834

#### Estimates of variability
