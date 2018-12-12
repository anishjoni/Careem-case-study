Careem Case Study
================
Anish Joni
December 12, 2018

Data Generation
---------------

``` r
orders_df %>% 
  group_by(order_day) %>% 
  count() %>%  
  ggplot(aes(order_day, n)) +
  geom_bar(stat = "identity") +
  scale_color_viridis_c() +
  theme_fivethirtyeight()
```

![](Careem-case-study_files/figure-markdown_github/EDA%20&%20Plots-1.png)

``` r
orders_df %>% 
  mutate(order_day = wday(order_datetime, label = T))
```

    ## # A tibble: 1,000 x 7
    ##    store_id store_name order_datetime      destination delivery_time      
    ##       <int> <chr>      <dttm>              <chr>       <dttm>             
    ##  1      109 KFC        2018-08-23 00:00:00 Neighbourh~ 2018-08-23 00:21:10
    ##  2      107 McDonald's 2018-10-26 00:00:00 Neighbourh~ 2018-10-26 00:42:29
    ##  3      129 Dipndip    2018-10-10 00:00:00 Neighbourh~ 2018-10-10 00:56:05
    ##  4       82 Didi Burg~ 2018-08-21 00:00:00 Neighbourh~ 2018-08-21 00:34:53
    ##  5       44 KFC        2018-11-25 00:00:00 Neighbourh~ 2018-11-25 00:30:43
    ##  6       65 McDonald's 2018-11-25 00:00:00 Neighbourh~ 2018-11-25 00:36:53
    ##  7       88 KFC        2018-08-16 00:00:00 Neighbourh~ 2018-08-16 00:54:03
    ##  8      135 Doce       2018-11-11 00:00:00 Neighbourh~ 2018-11-11 00:25:26
    ##  9       48 Broccoli ~ 2018-09-27 00:00:00 Neighbourh~ 2018-09-27 00:55:13
    ## 10       50 Didi Burg~ 2018-10-07 00:00:00 Neighbourh~ 2018-10-07 00:23:59
    ## # ... with 990 more rows, and 2 more variables: travel_time <time>,
    ## #   order_day <ord>
