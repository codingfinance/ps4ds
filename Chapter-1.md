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
datatable(state, class = 'cell-border stripe',
          caption = "Table: Showing state population and their Murder rates")
```

<!--html_preserve-->

<div id="htmlwidget-b7b86e87dc83f310d440" class="datatables html-widget" style="width:100%;height:auto;">

</div>

<script type="application/json" data-for="htmlwidget-b7b86e87dc83f310d440">{"x":{"filter":"none","caption":"<caption>Table: Showing state population and their Murder rates<\/caption>","data":[["1","2","3","4","5","6","7","8","9","10","11","12","13","14","15","16","17","18","19","20","21","22","23","24","25","26","27","28","29","30","31","32","33","34","35","36","37","38","39","40","41","42","43","44","45","46","47","48","49","50"],["Alabama","Alaska","Arizona","Arkansas","California","Colorado","Connecticut","Delaware","Florida","Georgia","Hawaii","Idaho","Illinois","Indiana","Iowa","Kansas","Kentucky","Louisiana","Maine","Maryland","Massachusetts","Michigan","Minnesota","Mississippi","Missouri","Montana","Nebraska","Nevada","New Hampshire","New Jersey","New Mexico","New York","North Carolina","North Dakota","Ohio","Oklahoma","Oregon","Pennsylvania","Rhode Island","South Carolina","South Dakota","Tennessee","Texas","Utah","Vermont","Virginia","Washington","West Virginia","Wisconsin","Wyoming"],[4779736,710231,6392017,2915918,37253956,5029196,3574097,897934,18801310,9687653,1360301,1567582,12830632,6483802,3046355,2853118,4339367,4533372,1328361,5773552,6547629,9883640,5303925,2967297,5988927,989415,1826341,2700551,1316470,8791894,2059179,19378102,9535483,672591,11536504,3751351,3831074,12702379,1052567,4625364,814180,6346105,25145561,2763885,625741,8001024,6724540,1852994,5686986,563626],[5.7,5.6,4.7,5.6,4.4,2.8,2.4,5.8,5.8,5.7,1.8,2,5.3,5,1.9,3.1,3.6,10.3,1.6,6.1,2,5.4,1.6,8.6,6.6,3.6,2.9,6,0.9,3.9,4.8,3.1,5.1,3,4,4.5,2,4.8,2.4,6.4,2.3,5.7,4.4,2.3,1.6,4.1,2.5,4,2.9,2.7],["AL","AK","AZ","AR","CA","CO","CT","DE","FL","GA","HI","ID","IL","IN","IA","KS","KY","LA","ME","MD","MA","MI","MN","MS","MO","MT","NE","NV","NH","NJ","NM","NY","NC","ND","OH","OK","OR","PA","RI","SC","SD","TN","TX","UT","VT","VA","WA","WV","WI","WY"]],"container":"<table class=\"cell-border stripe\">\n  <thead>\n    <tr>\n      <th> <\/th>\n      <th>State<\/th>\n      <th>Population<\/th>\n      <th>Murder.Rate<\/th>\n      <th>Abbreviation<\/th>\n    <\/tr>\n  <\/thead>\n<\/table>","options":{"columnDefs":[{"className":"dt-right","targets":[2,3]},{"orderable":false,"targets":0}],"order":[],"autoWidth":false,"orderClasses":false}},"evals":[],"jsHooks":[]}</script>

<!--/html_preserve-->

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
