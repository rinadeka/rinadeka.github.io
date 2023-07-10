Coolest Thing I Learned
================
Rina Deka
2023-06-29

# The Most Interesting Thing i’ve Learned

By far, one of the most interesting things I’ve learned was how to
connect to and query an API. Here’s an example below, using an API Key
“EefyNfm6f32hLdleNqk62NyYiIF5WmoTjCOIUxWl” from the NASA API.

## API Example: NASA Data

``` r
library(tidyverse)
```

    ## ── Attaching core tidyverse packages ──────────────────────── tidyverse 2.0.0 ──
    ## ✔ dplyr     1.1.2     ✔ readr     2.1.4
    ## ✔ forcats   1.0.0     ✔ stringr   1.5.0
    ## ✔ ggplot2   3.4.2     ✔ tibble    3.2.1
    ## ✔ lubridate 1.9.2     ✔ tidyr     1.3.0
    ## ✔ purrr     1.0.1     
    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()
    ## ℹ Use the ]8;;http://conflicted.r-lib.org/conflicted package]8;; to force all conflicts to become errors

``` r
library(httr)
library(jsonlite)
```

    ## 
    ## Attaching package: 'jsonlite'
    ## 
    ## The following object is masked from 'package:purrr':
    ## 
    ##     flatten

``` r
url <- "https://api.nasa.gov/mars-photos/api/v1/rovers/curiosity/photos"
query_params <- list(sol = 1000, api_key = "EefyNfm6f32hLdleNqk62NyYiIF5WmoTjCOIUxWl")

response <- GET(url, query = query_params)

response
```

    ## Response [https://api.nasa.gov/mars-photos/api/v1/rovers/curiosity/photos?sol=1000&api_key=EefyNfm6f32hLdleNqk62NyYiIF5WmoTjCOIUxWl]
    ##   Date: 2023-07-10 02:45
    ##   Status: 200
    ##   Content-Type: application/json; charset=utf-8
    ##   Size: 673 kB

We connected to the computer that NASA has this on! Now let’s get some
data, let’s say, the first thing from the data. It’ll be parsed, too.

``` r
if (http_type(NASA_Call) == "application/json") {
  data <- content(response, as = "parsed")}

data$photos[[1]]
```

    ## $id
    ## [1] 102693
    ## 
    ## $sol
    ## [1] 1000
    ## 
    ## $camera
    ## $camera$id
    ## [1] 20
    ## 
    ## $camera$name
    ## [1] "FHAZ"
    ## 
    ## $camera$rover_id
    ## [1] 5
    ## 
    ## $camera$full_name
    ## [1] "Front Hazard Avoidance Camera"
    ## 
    ## 
    ## $img_src
    ## [1] "http://mars.jpl.nasa.gov/msl-raw-images/proj/msl/redops/ods/surface/sol/01000/opgs/edr/fcam/FLB_486265257EDR_F0481570FHAZ00323M_.JPG"
    ## 
    ## $earth_date
    ## [1] "2015-05-30"
    ## 
    ## $rover
    ## $rover$id
    ## [1] 5
    ## 
    ## $rover$name
    ## [1] "Curiosity"
    ## 
    ## $rover$landing_date
    ## [1] "2012-08-06"
    ## 
    ## $rover$launch_date
    ## [1] "2011-11-26"
    ## 
    ## $rover$status
    ## [1] "active"
    ## 
    ## $rover$max_sol
    ## [1] 3881
    ## 
    ## $rover$max_date
    ## [1] "2023-07-07"
    ## 
    ## $rover$total_photos
    ## [1] 662891
    ## 
    ## $rover$cameras
    ## $rover$cameras[[1]]
    ## $rover$cameras[[1]]$name
    ## [1] "FHAZ"
    ## 
    ## $rover$cameras[[1]]$full_name
    ## [1] "Front Hazard Avoidance Camera"
    ## 
    ## 
    ## $rover$cameras[[2]]
    ## $rover$cameras[[2]]$name
    ## [1] "NAVCAM"
    ## 
    ## $rover$cameras[[2]]$full_name
    ## [1] "Navigation Camera"
    ## 
    ## 
    ## $rover$cameras[[3]]
    ## $rover$cameras[[3]]$name
    ## [1] "MAST"
    ## 
    ## $rover$cameras[[3]]$full_name
    ## [1] "Mast Camera"
    ## 
    ## 
    ## $rover$cameras[[4]]
    ## $rover$cameras[[4]]$name
    ## [1] "CHEMCAM"
    ## 
    ## $rover$cameras[[4]]$full_name
    ## [1] "Chemistry and Camera Complex"
    ## 
    ## 
    ## $rover$cameras[[5]]
    ## $rover$cameras[[5]]$name
    ## [1] "MAHLI"
    ## 
    ## $rover$cameras[[5]]$full_name
    ## [1] "Mars Hand Lens Imager"
    ## 
    ## 
    ## $rover$cameras[[6]]
    ## $rover$cameras[[6]]$name
    ## [1] "MARDI"
    ## 
    ## $rover$cameras[[6]]$full_name
    ## [1] "Mars Descent Imager"
    ## 
    ## 
    ## $rover$cameras[[7]]
    ## $rover$cameras[[7]]$name
    ## [1] "RHAZ"
    ## 
    ## $rover$cameras[[7]]$full_name
    ## [1] "Rear Hazard Avoidance Camera"

Cool, huh? Check in next time!
