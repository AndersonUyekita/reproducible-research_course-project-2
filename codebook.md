`Course Project 2` Reproducible Research
================

-   👨🏻‍💻 Author: Anderson H Uyekita
-   📚 Specialization: <a
    href="https://www.coursera.org/specializations/data-science-foundations-r"
    target="_blank" rel="noopener">Data Science: Foundations using R
    Specialization</a>
-   📖 Course:
    <a href="https://www.coursera.org/learn/reproducible-research"
    target="_blank" rel="noopener">Reproducible Research</a>
    -   🧑‍🏫 Instructor: Roger D Peng
-   📆 Week 4
    -   🚦 Start: Friday, 24 June 2022
    -   🏁 Finish: Saturday, 25 June 2022
-   🌎 Rpubs: [Interactive
    Document](https://rpubs.com/AndersonUyekita/course-project-2_reproducible-research)
-   📋 Instructions: [Project Instructions](./instructions.md)
-   📄 README: [README.md](./README.md)

------------------------------------------------------------------------

## Codebook

### 1. Requirements

### 2. Scripts

#### 2.1. README

### 3. Output and Input Details

Course Project 2 has only one input dataset from NOAA.

#### 3.1. Inputs

``` r
# Loading raw data.
raw_data <- read.csv(file = "./data/repdata_data_StormData.csv.bz2")

# Convert the regular data frame into a dplyr table
tbl_raw_data <- tbl_df(raw_data)
```

``` r
pryr::object_size(tbl_raw_data)
```

    ## 491.53 MB

``` r
dim(tbl_raw_data)
```

    ## [1] 902297     37

``` r
str(tbl_raw_data)
```

    ## tibble [902,297 × 37] (S3: tbl_df/tbl/data.frame)
    ##  $ STATE__   : num [1:902297] 1 1 1 1 1 1 1 1 1 1 ...
    ##  $ BGN_DATE  : chr [1:902297] "4/18/1950 0:00:00" "4/18/1950 0:00:00" "2/20/1951 0:00:00" "6/8/1951 0:00:00" ...
    ##  $ BGN_TIME  : chr [1:902297] "0130" "0145" "1600" "0900" ...
    ##  $ TIME_ZONE : chr [1:902297] "CST" "CST" "CST" "CST" ...
    ##  $ COUNTY    : num [1:902297] 97 3 57 89 43 77 9 123 125 57 ...
    ##  $ COUNTYNAME: chr [1:902297] "MOBILE" "BALDWIN" "FAYETTE" "MADISON" ...
    ##  $ STATE     : chr [1:902297] "AL" "AL" "AL" "AL" ...
    ##  $ EVTYPE    : chr [1:902297] "TORNADO" "TORNADO" "TORNADO" "TORNADO" ...
    ##  $ BGN_RANGE : num [1:902297] 0 0 0 0 0 0 0 0 0 0 ...
    ##  $ BGN_AZI   : chr [1:902297] "" "" "" "" ...
    ##  $ BGN_LOCATI: chr [1:902297] "" "" "" "" ...
    ##  $ END_DATE  : chr [1:902297] "" "" "" "" ...
    ##  $ END_TIME  : chr [1:902297] "" "" "" "" ...
    ##  $ COUNTY_END: num [1:902297] 0 0 0 0 0 0 0 0 0 0 ...
    ##  $ COUNTYENDN: logi [1:902297] NA NA NA NA NA NA ...
    ##  $ END_RANGE : num [1:902297] 0 0 0 0 0 0 0 0 0 0 ...
    ##  $ END_AZI   : chr [1:902297] "" "" "" "" ...
    ##  $ END_LOCATI: chr [1:902297] "" "" "" "" ...
    ##  $ LENGTH    : num [1:902297] 14 2 0.1 0 0 1.5 1.5 0 3.3 2.3 ...
    ##  $ WIDTH     : num [1:902297] 100 150 123 100 150 177 33 33 100 100 ...
    ##  $ F         : int [1:902297] 3 2 2 2 2 2 2 1 3 3 ...
    ##  $ MAG       : num [1:902297] 0 0 0 0 0 0 0 0 0 0 ...
    ##  $ FATALITIES: num [1:902297] 0 0 0 0 0 0 0 0 1 0 ...
    ##  $ INJURIES  : num [1:902297] 15 0 2 2 2 6 1 0 14 0 ...
    ##  $ PROPDMG   : num [1:902297] 25 2.5 25 2.5 2.5 2.5 2.5 2.5 25 25 ...
    ##  $ PROPDMGEXP: chr [1:902297] "K" "K" "K" "K" ...
    ##  $ CROPDMG   : num [1:902297] 0 0 0 0 0 0 0 0 0 0 ...
    ##  $ CROPDMGEXP: chr [1:902297] "" "" "" "" ...
    ##  $ WFO       : chr [1:902297] "" "" "" "" ...
    ##  $ STATEOFFIC: chr [1:902297] "" "" "" "" ...
    ##  $ ZONENAMES : chr [1:902297] "" "" "" "" ...
    ##  $ LATITUDE  : num [1:902297] 3040 3042 3340 3458 3412 ...
    ##  $ LONGITUDE : num [1:902297] 8812 8755 8742 8626 8642 ...
    ##  $ LATITUDE_E: num [1:902297] 3051 0 0 0 0 ...
    ##  $ LONGITUDE_: num [1:902297] 8806 0 0 0 0 ...
    ##  $ REMARKS   : chr [1:902297] "" "" "" "" ...
    ##  $ REFNUM    : num [1:902297] 1 2 3 4 5 6 7 8 9 10 ...

``` r
for (i in colnames(tbl_raw_data)) {
    p <- summary(tbl_raw_data[,i])
    
    cat("<h4>",i,"</h4>")
    cat("<p>","Some stuff here just to make an easy test","</p>")
    cat("<ul>")
    for (j in p) {
        cat("<li>",j,"</li>")}
    cat("</ul>")
    cat("<p>","More text here!!","</p>")
    
    cat("<code>")
    cat(p)
    cat("</code>")
    
    cat("<code>")
    cat(str(tbl_raw_data$LATITUDE))
    cat("</code>")
    
    
}
```

<h4>
STATE\_\_
</h4>
<p>
Some stuff here just to make an easy test
</p>
<ul>
<li>
Min. : 1.0
</li>
<li>
1st Qu.:19.0
</li>
<li>
Median :30.0
</li>
<li>
Mean :31.2
</li>
<li>
3rd Qu.:45.0
</li>
<li>
Max. :95.0
</li>
</ul>
<p>
More text here!!
</p>
<code>Min. : 1.0 1st Qu.:19.0 Median :30.0 Mean :31.2 3rd Qu.:45.0 Max.
:95.0 </code><code> num \[1:902297\] 3040 3042 3340 3458 3412 … </code>
<h4>
BGN_DATE
</h4>
<p>
Some stuff here just to make an easy test
</p>
<ul>
<li>
Length:902297
</li>
<li>
Class :character
</li>
<li>
Mode :character
</li>
</ul>
<p>
More text here!!
</p>
<code>Length:902297 Class :character Mode :character </code><code> num
\[1:902297\] 3040 3042 3340 3458 3412 … </code>
<h4>
BGN_TIME
</h4>
<p>
Some stuff here just to make an easy test
</p>
<ul>
<li>
Length:902297
</li>
<li>
Class :character
</li>
<li>
Mode :character
</li>
</ul>
<p>
More text here!!
</p>
<code>Length:902297 Class :character Mode :character </code><code> num
\[1:902297\] 3040 3042 3340 3458 3412 … </code>
<h4>
TIME_ZONE
</h4>
<p>
Some stuff here just to make an easy test
</p>
<ul>
<li>
Length:902297
</li>
<li>
Class :character
</li>
<li>
Mode :character
</li>
</ul>
<p>
More text here!!
</p>
<code>Length:902297 Class :character Mode :character </code><code> num
\[1:902297\] 3040 3042 3340 3458 3412 … </code>
<h4>
COUNTY
</h4>
<p>
Some stuff here just to make an easy test
</p>
<ul>
<li>
Min. : 0.0
</li>
<li>
1st Qu.: 31.0
</li>
<li>
Median : 75.0
</li>
<li>
Mean :100.6
</li>
<li>
3rd Qu.:131.0
</li>
<li>
Max. :873.0
</li>
</ul>
<p>
More text here!!
</p>
<code>Min. : 0.0 1st Qu.: 31.0 Median : 75.0 Mean :100.6 3rd Qu.:131.0
Max. :873.0 </code><code> num \[1:902297\] 3040 3042 3340 3458 3412 …
</code>
<h4>
COUNTYNAME
</h4>
<p>
Some stuff here just to make an easy test
</p>
<ul>
<li>
Length:902297
</li>
<li>
Class :character
</li>
<li>
Mode :character
</li>
</ul>
<p>
More text here!!
</p>
<code>Length:902297 Class :character Mode :character </code><code> num
\[1:902297\] 3040 3042 3340 3458 3412 … </code>
<h4>
STATE
</h4>
<p>
Some stuff here just to make an easy test
</p>
<ul>
<li>
Length:902297
</li>
<li>
Class :character
</li>
<li>
Mode :character
</li>
</ul>
<p>
More text here!!
</p>
<code>Length:902297 Class :character Mode :character </code><code> num
\[1:902297\] 3040 3042 3340 3458 3412 … </code>
<h4>
EVTYPE
</h4>
<p>
Some stuff here just to make an easy test
</p>
<ul>
<li>
Length:902297
</li>
<li>
Class :character
</li>
<li>
Mode :character
</li>
</ul>
<p>
More text here!!
</p>
<code>Length:902297 Class :character Mode :character </code><code> num
\[1:902297\] 3040 3042 3340 3458 3412 … </code>
<h4>
BGN_RANGE
</h4>
<p>
Some stuff here just to make an easy test
</p>
<ul>
<li>
Min. : 0.000
</li>
<li>
1st Qu.: 0.000
</li>
<li>
Median : 0.000
</li>
<li>
Mean : 1.484
</li>
<li>
3rd Qu.: 1.000
</li>
<li>
Max. :3749.000
</li>
</ul>
<p>
More text here!!
</p>
<code>Min. : 0.000 1st Qu.: 0.000 Median : 0.000 Mean : 1.484 3rd Qu.:
1.000 Max. :3749.000 </code><code> num \[1:902297\] 3040 3042 3340 3458
3412 … </code>
<h4>
BGN_AZI
</h4>
<p>
Some stuff here just to make an easy test
</p>
<ul>
<li>
Length:902297
</li>
<li>
Class :character
</li>
<li>
Mode :character
</li>
</ul>
<p>
More text here!!
</p>
<code>Length:902297 Class :character Mode :character </code><code> num
\[1:902297\] 3040 3042 3340 3458 3412 … </code>
<h4>
BGN_LOCATI
</h4>
<p>
Some stuff here just to make an easy test
</p>
<ul>
<li>
Length:902297
</li>
<li>
Class :character
</li>
<li>
Mode :character
</li>
</ul>
<p>
More text here!!
</p>
<code>Length:902297 Class :character Mode :character </code><code> num
\[1:902297\] 3040 3042 3340 3458 3412 … </code>
<h4>
END_DATE
</h4>
<p>
Some stuff here just to make an easy test
</p>
<ul>
<li>
Length:902297
</li>
<li>
Class :character
</li>
<li>
Mode :character
</li>
</ul>
<p>
More text here!!
</p>
<code>Length:902297 Class :character Mode :character </code><code> num
\[1:902297\] 3040 3042 3340 3458 3412 … </code>
<h4>
END_TIME
</h4>
<p>
Some stuff here just to make an easy test
</p>
<ul>
<li>
Length:902297
</li>
<li>
Class :character
</li>
<li>
Mode :character
</li>
</ul>
<p>
More text here!!
</p>
<code>Length:902297 Class :character Mode :character </code><code> num
\[1:902297\] 3040 3042 3340 3458 3412 … </code>
<h4>
COUNTY_END
</h4>
<p>
Some stuff here just to make an easy test
</p>
<ul>
<li>
Min. :0
</li>
<li>
1st Qu.:0
</li>
<li>
Median :0
</li>
<li>
Mean :0
</li>
<li>
3rd Qu.:0
</li>
<li>
Max. :0
</li>
</ul>
<p>
More text here!!
</p>
<code>Min. :0 1st Qu.:0 Median :0 Mean :0 3rd Qu.:0 Max. :0
</code><code> num \[1:902297\] 3040 3042 3340 3458 3412 … </code>
<h4>
COUNTYENDN
</h4>
<p>
Some stuff here just to make an easy test
</p>
<ul>
<li>
Mode:logical
</li>
<li>
NA’s:902297
</li>
</ul>
<p>
More text here!!
</p>
<code>Mode:logical NA’s:902297 </code><code> num \[1:902297\] 3040 3042
3340 3458 3412 … </code>
<h4>
END_RANGE
</h4>
<p>
Some stuff here just to make an easy test
</p>
<ul>
<li>
Min. : 0.0000
</li>
<li>
1st Qu.: 0.0000
</li>
<li>
Median : 0.0000
</li>
<li>
Mean : 0.9862
</li>
<li>
3rd Qu.: 0.0000
</li>
<li>
Max. :925.0000
</li>
</ul>
<p>
More text here!!
</p>
<code>Min. : 0.0000 1st Qu.: 0.0000 Median : 0.0000 Mean : 0.9862 3rd
Qu.: 0.0000 Max. :925.0000 </code><code> num \[1:902297\] 3040 3042 3340
3458 3412 … </code>
<h4>
END_AZI
</h4>
<p>
Some stuff here just to make an easy test
</p>
<ul>
<li>
Length:902297
</li>
<li>
Class :character
</li>
<li>
Mode :character
</li>
</ul>
<p>
More text here!!
</p>
<code>Length:902297 Class :character Mode :character </code><code> num
\[1:902297\] 3040 3042 3340 3458 3412 … </code>
<h4>
END_LOCATI
</h4>
<p>
Some stuff here just to make an easy test
</p>
<ul>
<li>
Length:902297
</li>
<li>
Class :character
</li>
<li>
Mode :character
</li>
</ul>
<p>
More text here!!
</p>
<code>Length:902297 Class :character Mode :character </code><code> num
\[1:902297\] 3040 3042 3340 3458 3412 … </code>
<h4>
LENGTH
</h4>
<p>
Some stuff here just to make an easy test
</p>
<ul>
<li>
Min. : 0.0000
</li>
<li>
1st Qu.: 0.0000
</li>
<li>
Median : 0.0000
</li>
<li>
Mean : 0.2301
</li>
<li>
3rd Qu.: 0.0000
</li>
<li>
Max. :2315.0000
</li>
</ul>
<p>
More text here!!
</p>
<code>Min. : 0.0000 1st Qu.: 0.0000 Median : 0.0000 Mean : 0.2301 3rd
Qu.: 0.0000 Max. :2315.0000 </code><code> num \[1:902297\] 3040 3042
3340 3458 3412 … </code>
<h4>
WIDTH
</h4>
<p>
Some stuff here just to make an easy test
</p>
<ul>
<li>
Min. : 0.000
</li>
<li>
1st Qu.: 0.000
</li>
<li>
Median : 0.000
</li>
<li>
Mean : 7.503
</li>
<li>
3rd Qu.: 0.000
</li>
<li>
Max. :4400.000
</li>
</ul>
<p>
More text here!!
</p>
<code>Min. : 0.000 1st Qu.: 0.000 Median : 0.000 Mean : 7.503 3rd Qu.:
0.000 Max. :4400.000 </code><code> num \[1:902297\] 3040 3042 3340 3458
3412 … </code>
<h4>
F
</h4>
<p>
Some stuff here just to make an easy test
</p>
<ul>
<li>
Min. :0.0
</li>
<li>
1st Qu.:0.0
</li>
<li>
Median :1.0
</li>
<li>
Mean :0.9
</li>
<li>
3rd Qu.:1.0
</li>
<li>
Max. :5.0
</li>
<li>
NA’s :843563
</li>
</ul>
<p>
More text here!!
</p>
<code>Min. :0.0 1st Qu.:0.0 Median :1.0 Mean :0.9 3rd Qu.:1.0 Max. :5.0
NA’s :843563 </code><code> num \[1:902297\] 3040 3042 3340 3458 3412 …
</code>
<h4>
MAG
</h4>
<p>
Some stuff here just to make an easy test
</p>
<ul>
<li>
Min. : 0.0
</li>
<li>
1st Qu.: 0.0
</li>
<li>
Median : 50.0
</li>
<li>
Mean : 46.9
</li>
<li>
3rd Qu.: 75.0
</li>
<li>
Max. :22000.0
</li>
</ul>
<p>
More text here!!
</p>
<code>Min. : 0.0 1st Qu.: 0.0 Median : 50.0 Mean : 46.9 3rd Qu.: 75.0
Max. :22000.0 </code><code> num \[1:902297\] 3040 3042 3340 3458 3412 …
</code>
<h4>
FATALITIES
</h4>
<p>
Some stuff here just to make an easy test
</p>
<ul>
<li>
Min. : 0.0000
</li>
<li>
1st Qu.: 0.0000
</li>
<li>
Median : 0.0000
</li>
<li>
Mean : 0.0168
</li>
<li>
3rd Qu.: 0.0000
</li>
<li>
Max. :583.0000
</li>
</ul>
<p>
More text here!!
</p>
<code>Min. : 0.0000 1st Qu.: 0.0000 Median : 0.0000 Mean : 0.0168 3rd
Qu.: 0.0000 Max. :583.0000 </code><code> num \[1:902297\] 3040 3042 3340
3458 3412 … </code>
<h4>
INJURIES
</h4>
<p>
Some stuff here just to make an easy test
</p>
<ul>
<li>
Min. : 0.0000
</li>
<li>
1st Qu.: 0.0000
</li>
<li>
Median : 0.0000
</li>
<li>
Mean : 0.1557
</li>
<li>
3rd Qu.: 0.0000
</li>
<li>
Max. :1700.0000
</li>
</ul>
<p>
More text here!!
</p>
<code>Min. : 0.0000 1st Qu.: 0.0000 Median : 0.0000 Mean : 0.1557 3rd
Qu.: 0.0000 Max. :1700.0000 </code><code> num \[1:902297\] 3040 3042
3340 3458 3412 … </code>
<h4>
PROPDMG
</h4>
<p>
Some stuff here just to make an easy test
</p>
<ul>
<li>
Min. : 0.00
</li>
<li>
1st Qu.: 0.00
</li>
<li>
Median : 0.00
</li>
<li>
Mean : 12.06
</li>
<li>
3rd Qu.: 0.50
</li>
<li>
Max. :5000.00
</li>
</ul>
<p>
More text here!!
</p>
<code>Min. : 0.00 1st Qu.: 0.00 Median : 0.00 Mean : 12.06 3rd Qu.: 0.50
Max. :5000.00 </code><code> num \[1:902297\] 3040 3042 3340 3458 3412 …
</code>
<h4>
PROPDMGEXP
</h4>
<p>
Some stuff here just to make an easy test
</p>
<ul>
<li>
Length:902297
</li>
<li>
Class :character
</li>
<li>
Mode :character
</li>
</ul>
<p>
More text here!!
</p>
<code>Length:902297 Class :character Mode :character </code><code> num
\[1:902297\] 3040 3042 3340 3458 3412 … </code>
<h4>
CROPDMG
</h4>
<p>
Some stuff here just to make an easy test
</p>
<ul>
<li>
Min. : 0.000
</li>
<li>
1st Qu.: 0.000
</li>
<li>
Median : 0.000
</li>
<li>
Mean : 1.527
</li>
<li>
3rd Qu.: 0.000
</li>
<li>
Max. :990.000
</li>
</ul>
<p>
More text here!!
</p>
<code>Min. : 0.000 1st Qu.: 0.000 Median : 0.000 Mean : 1.527 3rd Qu.:
0.000 Max. :990.000 </code><code> num \[1:902297\] 3040 3042 3340 3458
3412 … </code>
<h4>
CROPDMGEXP
</h4>
<p>
Some stuff here just to make an easy test
</p>
<ul>
<li>
Length:902297
</li>
<li>
Class :character
</li>
<li>
Mode :character
</li>
</ul>
<p>
More text here!!
</p>
<code>Length:902297 Class :character Mode :character </code><code> num
\[1:902297\] 3040 3042 3340 3458 3412 … </code>
<h4>
WFO
</h4>
<p>
Some stuff here just to make an easy test
</p>
<ul>
<li>
Length:902297
</li>
<li>
Class :character
</li>
<li>
Mode :character
</li>
</ul>
<p>
More text here!!
</p>
<code>Length:902297 Class :character Mode :character </code><code> num
\[1:902297\] 3040 3042 3340 3458 3412 … </code>
<h4>
STATEOFFIC
</h4>
<p>
Some stuff here just to make an easy test
</p>
<ul>
<li>
Length:902297
</li>
<li>
Class :character
</li>
<li>
Mode :character
</li>
</ul>
<p>
More text here!!
</p>
<code>Length:902297 Class :character Mode :character </code><code> num
\[1:902297\] 3040 3042 3340 3458 3412 … </code>
<h4>
ZONENAMES
</h4>
<p>
Some stuff here just to make an easy test
</p>
<ul>
<li>
Length:902297
</li>
<li>
Class :character
</li>
<li>
Mode :character
</li>
</ul>
<p>
More text here!!
</p>
<code>Length:902297 Class :character Mode :character </code><code> num
\[1:902297\] 3040 3042 3340 3458 3412 … </code>
<h4>
LATITUDE
</h4>
<p>
Some stuff here just to make an easy test
</p>
<ul>
<li>
Min. : 0
</li>
<li>
1st Qu.:2802
</li>
<li>
Median :3540
</li>
<li>
Mean :2875
</li>
<li>
3rd Qu.:4019
</li>
<li>
Max. :9706
</li>
<li>
NA’s :47
</li>
</ul>
<p>
More text here!!
</p>
<code>Min. : 0 1st Qu.:2802 Median :3540 Mean :2875 3rd Qu.:4019 Max.
:9706 NA’s :47 </code><code> num \[1:902297\] 3040 3042 3340 3458 3412 …
</code>
<h4>
LONGITUDE
</h4>
<p>
Some stuff here just to make an easy test
</p>
<ul>
<li>
Min. :-14451
</li>
<li>
1st Qu.: 7247
</li>
<li>
Median : 8707
</li>
<li>
Mean : 6940
</li>
<li>
3rd Qu.: 9605
</li>
<li>
Max. : 17124
</li>
</ul>
<p>
More text here!!
</p>
<code>Min. :-14451 1st Qu.: 7247 Median : 8707 Mean : 6940 3rd Qu.: 9605
Max. : 17124 </code><code> num \[1:902297\] 3040 3042 3340 3458 3412 …
</code>
<h4>
LATITUDE_E
</h4>
<p>
Some stuff here just to make an easy test
</p>
<ul>
<li>
Min. : 0
</li>
<li>
1st Qu.: 0
</li>
<li>
Median : 0
</li>
<li>
Mean :1452
</li>
<li>
3rd Qu.:3549
</li>
<li>
Max. :9706
</li>
<li>
NA’s :40
</li>
</ul>
<p>
More text here!!
</p>
<code>Min. : 0 1st Qu.: 0 Median : 0 Mean :1452 3rd Qu.:3549 Max. :9706
NA’s :40 </code><code> num \[1:902297\] 3040 3042 3340 3458 3412 …
</code>
<h4>
LONGITUDE\_
</h4>
<p>
Some stuff here just to make an easy test
</p>
<ul>
<li>
Min. :-14455
</li>
<li>
1st Qu.: 0
</li>
<li>
Median : 0
</li>
<li>
Mean : 3509
</li>
<li>
3rd Qu.: 8735
</li>
<li>
Max. :106220
</li>
</ul>
<p>
More text here!!
</p>
<code>Min. :-14455 1st Qu.: 0 Median : 0 Mean : 3509 3rd Qu.: 8735 Max.
:106220 </code><code> num \[1:902297\] 3040 3042 3340 3458 3412 …
</code>
<h4>
REMARKS
</h4>
<p>
Some stuff here just to make an easy test
</p>
<ul>
<li>
Length:902297
</li>
<li>
Class :character
</li>
<li>
Mode :character
</li>
</ul>
<p>
More text here!!
</p>
<code>Length:902297 Class :character Mode :character </code><code> num
\[1:902297\] 3040 3042 3340 3458 3412 … </code>
<h4>
REFNUM
</h4>
<p>
Some stuff here just to make an easy test
</p>
<ul>
<li>
Min. : 1
</li>
<li>
1st Qu.:225575
</li>
<li>
Median :451149
</li>
<li>
Mean :451149
</li>
<li>
3rd Qu.:676723
</li>
<li>
Max. :902297
</li>
</ul>
<p>
More text here!!
</p>

<code>Min. : 1 1st Qu.:225575 Median :451149 Mean :451149 3rd Qu.:676723
Max. :902297 </code><code> num \[1:902297\] 3040 3042 3340 3458 3412 …
</code>

#### 3.2. Output
