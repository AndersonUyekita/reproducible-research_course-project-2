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
    -   🏁 Finish: Tuesday, 28 June 2022
-   🌎 Rpubs: [Interactive
    Document](https://rpubs.com/AndersonUyekita/course-project-2_reproducible-research)
-   📋 Instructions: [Project Instructions](./instructions.md)
-   📄 README: [README.md](./README.md)

------------------------------------------------------------------------

## Codebook

### 1. Requirements

### 2. Scripts

Course Project 2 aims to create an Rmd file to create a **Literate
Programming**. To do so, I have made the `README.Rmd` which merges text
and code.

#### 2.1. README

### 3. Output and Input Details

Course Project 2 has only one input dataset from NOAA and there is no
output file.

#### 3.1. Inputs

The file from NOAA should be downloaded from:

-   Source:
    <https://d396qusza40orc.cloudfront.net/repdata%2Fdata%2FStormData.csv.bz2>
-   Download file size: 47 Mbytes

##### 3.1.1. Raw dataset

The content of `repdata_data_StormData.csv.bz2` is a `CSV` file
compressed in a `bz2` file.

-   Object Size in R environment: 4.9152506^{8}
-   Number of Observations: 902,297
-   Number of Variables: 37

**Structure**

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

**Variables**

    ##  [1] "STATE__"    "BGN_DATE"   "BGN_TIME"   "TIME_ZONE"  "COUNTY"    
    ##  [6] "COUNTYNAME" "STATE"      "EVTYPE"     "BGN_RANGE"  "BGN_AZI"   
    ## [11] "BGN_LOCATI" "END_DATE"   "END_TIME"   "COUNTY_END" "COUNTYENDN"
    ## [16] "END_RANGE"  "END_AZI"    "END_LOCATI" "LENGTH"     "WIDTH"     
    ## [21] "F"          "MAG"        "FATALITIES" "INJURIES"   "PROPDMG"   
    ## [26] "PROPDMGEXP" "CROPDMG"    "CROPDMGEXP" "WFO"        "STATEOFFIC"
    ## [31] "ZONENAMES"  "LATITUDE"   "LONGITUDE"  "LATITUDE_E" "LONGITUDE_"
    ## [36] "REMARKS"    "REFNUM"

**Summary**

    ##     STATE__       BGN_DATE           BGN_TIME          TIME_ZONE        
    ##  Min.   : 1.0   Length:902297      Length:902297      Length:902297     
    ##  1st Qu.:19.0   Class :character   Class :character   Class :character  
    ##  Median :30.0   Mode  :character   Mode  :character   Mode  :character  
    ##  Mean   :31.2                                                           
    ##  3rd Qu.:45.0                                                           
    ##  Max.   :95.0                                                           
    ##                                                                         
    ##      COUNTY       COUNTYNAME           STATE              EVTYPE         
    ##  Min.   :  0.0   Length:902297      Length:902297      Length:902297     
    ##  1st Qu.: 31.0   Class :character   Class :character   Class :character  
    ##  Median : 75.0   Mode  :character   Mode  :character   Mode  :character  
    ##  Mean   :100.6                                                           
    ##  3rd Qu.:131.0                                                           
    ##  Max.   :873.0                                                           
    ##                                                                          
    ##    BGN_RANGE          BGN_AZI           BGN_LOCATI          END_DATE        
    ##  Min.   :   0.000   Length:902297      Length:902297      Length:902297     
    ##  1st Qu.:   0.000   Class :character   Class :character   Class :character  
    ##  Median :   0.000   Mode  :character   Mode  :character   Mode  :character  
    ##  Mean   :   1.484                                                           
    ##  3rd Qu.:   1.000                                                           
    ##  Max.   :3749.000                                                           
    ##                                                                             
    ##    END_TIME           COUNTY_END COUNTYENDN       END_RANGE       
    ##  Length:902297      Min.   :0    Mode:logical   Min.   :  0.0000  
    ##  Class :character   1st Qu.:0    NA's:902297    1st Qu.:  0.0000  
    ##  Mode  :character   Median :0                   Median :  0.0000  
    ##                     Mean   :0                   Mean   :  0.9862  
    ##                     3rd Qu.:0                   3rd Qu.:  0.0000  
    ##                     Max.   :0                   Max.   :925.0000  
    ##                                                                   
    ##    END_AZI           END_LOCATI            LENGTH              WIDTH         
    ##  Length:902297      Length:902297      Min.   :   0.0000   Min.   :   0.000  
    ##  Class :character   Class :character   1st Qu.:   0.0000   1st Qu.:   0.000  
    ##  Mode  :character   Mode  :character   Median :   0.0000   Median :   0.000  
    ##                                        Mean   :   0.2301   Mean   :   7.503  
    ##                                        3rd Qu.:   0.0000   3rd Qu.:   0.000  
    ##                                        Max.   :2315.0000   Max.   :4400.000  
    ##                                                                              
    ##        F               MAG            FATALITIES          INJURIES        
    ##  Min.   :0.0      Min.   :    0.0   Min.   :  0.0000   Min.   :   0.0000  
    ##  1st Qu.:0.0      1st Qu.:    0.0   1st Qu.:  0.0000   1st Qu.:   0.0000  
    ##  Median :1.0      Median :   50.0   Median :  0.0000   Median :   0.0000  
    ##  Mean   :0.9      Mean   :   46.9   Mean   :  0.0168   Mean   :   0.1557  
    ##  3rd Qu.:1.0      3rd Qu.:   75.0   3rd Qu.:  0.0000   3rd Qu.:   0.0000  
    ##  Max.   :5.0      Max.   :22000.0   Max.   :583.0000   Max.   :1700.0000  
    ##  NA's   :843563                                                           
    ##     PROPDMG         PROPDMGEXP           CROPDMG         CROPDMGEXP       
    ##  Min.   :   0.00   Length:902297      Min.   :  0.000   Length:902297     
    ##  1st Qu.:   0.00   Class :character   1st Qu.:  0.000   Class :character  
    ##  Median :   0.00   Mode  :character   Median :  0.000   Mode  :character  
    ##  Mean   :  12.06                      Mean   :  1.527                     
    ##  3rd Qu.:   0.50                      3rd Qu.:  0.000                     
    ##  Max.   :5000.00                      Max.   :990.000                     
    ##                                                                           
    ##      WFO             STATEOFFIC         ZONENAMES            LATITUDE   
    ##  Length:902297      Length:902297      Length:902297      Min.   :   0  
    ##  Class :character   Class :character   Class :character   1st Qu.:2802  
    ##  Mode  :character   Mode  :character   Mode  :character   Median :3540  
    ##                                                           Mean   :2875  
    ##                                                           3rd Qu.:4019  
    ##                                                           Max.   :9706  
    ##                                                           NA's   :47    
    ##    LONGITUDE        LATITUDE_E     LONGITUDE_       REMARKS         
    ##  Min.   :-14451   Min.   :   0   Min.   :-14455   Length:902297     
    ##  1st Qu.:  7247   1st Qu.:   0   1st Qu.:     0   Class :character  
    ##  Median :  8707   Median :   0   Median :     0   Mode  :character  
    ##  Mean   :  6940   Mean   :1452   Mean   :  3509                     
    ##  3rd Qu.:  9605   3rd Qu.:3549   3rd Qu.:  8735                     
    ##  Max.   : 17124   Max.   :9706   Max.   :106220                     
    ##                   NA's   :40                                        
    ##      REFNUM      
    ##  Min.   :     1  
    ##  1st Qu.:225575  
    ##  Median :451149  
    ##  Mean   :451149  
    ##  3rd Qu.:676723  
    ##  Max.   :902297  
    ## 

Some variables have not been imported correctly, which will demand
adjustments.

##### 3.1.1. Tidy Dataset

The tidy dataset is a subset of the raw dataset because the Course
Project does not require using all variables. Initially, I selected the
following variables as part of the tidy dataset. Later some variables
will be bundled together and may be dropped.

-   `EVTYPE`: Event type;
-   `INJURIES`: Quantity of injuries;
-   `FATALITIES`: Quantity of fatalities;
-   `PROPDMG`: Amount in USD in Damages in properties;
-   `CROPDMG`: Amount in USD in Damages in crops;
-   `PROPDMGEXP`: The exponential in base 10 used to notate the PROPDMG,
    and;
-   `CROPDMGEXP`: The exponential in base 10 used to notate the CROPDMG.

After the data manipulation, the tidy dataset will have the following
characteristics.

-   Object Size in R environment: 3.2485736^{7}
-   Number of Observations: 902,297
-   Number of Variables: 5

**Structure**

    ## tibble [902,297 × 5] (S3: tbl_df/tbl/data.frame)
    ##  $ INJURIES  : num [1:902297] 15 0 2 2 2 6 1 0 14 0 ...
    ##  $ FATALITIES: num [1:902297] 0 0 0 0 0 0 0 0 1 0 ...
    ##  $ PROPDMGABS: num [1:902297] 25000 2500 25000 2500 2500 2500 2500 2500 25000 25000 ...
    ##  $ CROPDMGABS: num [1:902297] 0 0 0 0 0 0 0 0 0 0 ...
    ##  $ EVTYPE    : Factor w/ 19 levels "AVALANCHE","CURRENT",..: 17 17 17 17 17 17 17 17 17 17 ...

**Variables**

    ## [1] "INJURIES"   "FATALITIES" "PROPDMGABS" "CROPDMGABS" "EVTYPE"

**Summary**

    ##     INJURIES           FATALITIES         PROPDMGABS          CROPDMGABS       
    ##  Min.   :   0.0000   Min.   :  0.0000   Min.   :0.000e+00   Min.   :0.000e+00  
    ##  1st Qu.:   0.0000   1st Qu.:  0.0000   1st Qu.:0.000e+00   1st Qu.:0.000e+00  
    ##  Median :   0.0000   Median :  0.0000   Median :0.000e+00   Median :0.000e+00  
    ##  Mean   :   0.1557   Mean   :  0.0168   Mean   :4.746e+05   Mean   :5.442e+04  
    ##  3rd Qu.:   0.0000   3rd Qu.:  0.0000   3rd Qu.:5.000e+02   3rd Qu.:0.000e+00  
    ##  Max.   :1700.0000   Max.   :583.0000   Max.   :1.150e+11   Max.   :5.000e+09  
    ##                                         NA's   :13                             
    ##                EVTYPE      
    ##  THUNDERSTORM WIND:343796  
    ##  HAIL             :289281  
    ##  FLOOD            : 86133  
    ##  TORNADO          : 60700  
    ##  EXCESSIVE HEAT   : 33788  
    ##  HIGH WIND        : 28173  
    ##  (Other)          : 60426

#### 3.2. Output

Course Project 2 do not have any output.

### 4. Publication

Course Project 2 should be published in
[Rpubs](https://rpubs.com/AndersonUyekita/course-project-2_reproducible-research).
