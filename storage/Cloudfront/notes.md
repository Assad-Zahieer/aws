# Amazon Cloudfront

## Overview
* Content delivery network (CDN) service
* Distribute data requested to end user via ***edge locations***
* Cached data (therefore expires), durability N/A
    * Source data from S3
    
## 6.1 Edge Locations
  * Sites in popular cities, only store cached data
  * Used to lower latency
    * e.g. Website in India accesed in the U.K. user is redirected to closest edge location where data is read

## 6.2 Distributions - data delivery method
### Web Distribution
  * Distribute both static and dynamic content
  * Use both HTTP & HTTPS
  * Gives ability to live stream
### RTMP Distribution
  * Allows user to stream media before download is completed from edge location
  
## 6.3 Configuration
* Specify origin & edge locations

## 6.3 Pricing
* Based on HTTP requests & data transfer
* Additional costs e.g field level encryption

