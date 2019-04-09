<style type="text/css">

.reveal pre code {
  display: block; padding: 0.3em;
  font-size: 1em;
  
</style>


Diamond price prediction
========================================================
author: zakariatsu
date: 09/04/2019
autosize: true
transition: rotate
transition-speed: slow

Overview
========================================================
This presentation contains documentation for the Diamond price prediction application. The application can be found [**here**] 

This application it is building linear regression model using `diamonds` data set and is predicting the price of a diamond depending of its properties.The application allows the user to select:
- Carat
- Cut
- Color
- Clarity

Builds a plot and gives predicted price of the diamond.

Data used
========================================================

The data used for this application is `diamonds` data set, which is part of `ggplot2` package.
This data set contains the information about 53940 diamonds with 10 variables:



```
     carat               cut        color        clarity     
 Min.   :0.2000   Fair     : 1610   D: 6775   SI1    :13065  
 1st Qu.:0.4000   Good     : 4906   E: 9797   VS2    :12258  
 Median :0.7000   Very Good:12082   F: 9542   SI2    : 9194  
 Mean   :0.7979   Premium  :13791   G:11292   VS1    : 8171  
 3rd Qu.:1.0400   Ideal    :21551   H: 8304   VVS2   : 5066  
 Max.   :5.0100                     I: 5422   VVS1   : 3655  
                                    J: 2808   (Other): 2531  
     depth           table           price             x         
 Min.   :43.00   Min.   :43.00   Min.   :  326   Min.   : 0.000  
 1st Qu.:61.00   1st Qu.:56.00   1st Qu.:  950   1st Qu.: 4.710  
 Median :61.80   Median :57.00   Median : 2401   Median : 5.700  
 Mean   :61.75   Mean   :57.46   Mean   : 3933   Mean   : 5.731  
 3rd Qu.:62.50   3rd Qu.:59.00   3rd Qu.: 5324   3rd Qu.: 6.540  
 Max.   :79.00   Max.   :95.00   Max.   :18823   Max.   :10.740  
                                                                 
       y                z         
 Min.   : 0.000   Min.   : 0.000  
 1st Qu.: 4.720   1st Qu.: 2.910  
 Median : 5.710   Median : 3.530  
 Mean   : 5.735   Mean   : 3.539  
 3rd Qu.: 6.540   3rd Qu.: 4.040  
 Max.   :58.900   Max.   :31.800  
                                  
```

Shiny files
========================================================

The application is build using Shiny package and the source code is in 2 files:
- `ui.R`
- `server.R`



Application functionality
========================================================

The application is drawing plot of diamonds in the `diamonds` data set distributed by their size (carat) and price ($). The regression line is shown on the plot as well. 

By selecting specific features of the diamond (carat, cut, clarity, color) the user is able to sub select the data set and the regression is recalculated based only on the diamonds in the data set that share the same features. If no features are selected the regression model is using all diamonds in the data set.

Below the graph the predicted price is shown.
