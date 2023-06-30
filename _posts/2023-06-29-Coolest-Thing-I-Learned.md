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
library(httr)
library(jsonlite)

url <- "https://api.nasa.gov/mars-photos/api/v1/rovers/curiosity/photos"
query_params <- list(sol = 1000, api_key = "EefyNfm6f32hLdleNqk62NyYiIF5WmoTjCOIUxWl")

response <- GET(url, query = query_params)

response
```

    ## Response [https://api.nasa.gov/mars-photos/api/v1/rovers/curiosity/photos?sol=1000&api_key=EefyNfm6f32hLdleNqk62NyYiIF5WmoTjCOIUxWl]
    ##   Date: 2023-06-30 05:09
    ##   Status: 200
    ##   Content-Type: application/json; charset=utf-8
    ##   Size: 288 kB

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

Cool, huh? Check in next time!
