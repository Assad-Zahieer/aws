# Elastic Cloud Computing
## Overview
* Provides secure, resizable compute capacity in the cloud.
* Complete control of your instances
## Components
1. Amazon machine image (AMI)
2. Instance types
3. Instance payment options
4. Tenancy
5. User data
6. Storage options
## 1. Amazon Machine Image (AMI)
* Pre-configured EC2 templates
  * Include OS, Applications (e.g some AMIs have SQL)
* Create AMIs from customised instance
  * Useful for auto-scaling
## 2. Instance Types
* Size is based on:
  * ECUs - n.o. EC2 compute units for the instance
  * vCPUs - n.o. virtual CPUs
  * Physical processor
  * Storage, Memory etc.
* **Instance families**
  * Micro - low traffic websites 
  * Compute optomised - high performance e.g. batch processing, high performance front-end
  * Storage optimised - use SSDs and NoSQL databases
  * Memory optimised - fast performance for large data sets
## 3. Instance payment options
* **On-demand instance**
  * Flat rate - base on instance type
  * Short-term use
* **Reserved instances**
  * *All upfront*: most discount, pay for 1 or 3 year time frame
  * *Partial upfront*: smaller upfront payment
  * *No upfront
  * Use case - long term **predictable** workloads
