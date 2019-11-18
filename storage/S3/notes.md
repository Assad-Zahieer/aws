# Amazon Simple Storage Service (S3): Fuly managed object storage service

## Overview
  * Highly available, durable and scalable
    * D = 11 9's, A = 99.99%
  * Regional based - amazon will deploy across multiple AZs in specified region
  * Used for:
    * Data backup - accessible from anywhere
    * Static content - images, static website
    * Large data sets - statistical data
  
## 1.0 S3 Buckets: Data object uploaded into bucket
  * Name - globally unique
  * LT. 100 buckets/account (default)
  
## 1.1 Storage Classes
  * Standard
  * Standard_IA (Infrequent Access)
  * Intelligent_tiering
  * OneZone_IA
  * RRS reduced redundancy (not reccomended)
### Use Cases
#### Frequent access
 * Standard - more cost effective and durable than RRS
#### Infrequent access - additional charge to retrieve data
  * Standard_IA & OneZone_IA
    * OneZone_IA = lower availability
#### Intelligent tiering: for unpredictable access patterns
  * Data object moved frequent access -> IA after 30 days (if not used for period)
    
## 1.2 Security
### Bucket Policies: Control access to data in associated bucket
  * Specific permissions - who? time period? etc.
  * JSON format
### Access Control Lists: For users outside aws account (e.g. public access)
  * Broad permissions - list object, write object etc
### Data Encryption: Server & client side options
#### Server-side: Encryption in S3 
  * SSE-S3 (S3 managed keys)
  * SSE-KMS (kms managed keys)
  * SSE-C (custimer managed keys)
#### Client-side: Encryption prior to upload
  * CSE-KMS
  * CSE-C
  #### SSL supported
  
## 1.3 Data Management
### Versioning: Data recovery
  * Not enabled by default, more cost
### Lifecycle rules: automatic method of data lifecycle management (what happens to data after x time)
  * Set criteria e.g. after 30 days:
    * Archieve data (amazon glacier)
    * Delete data
    * Move to cheaper storage class
    
## 1.4 Service Integration of S3
  * With EBS - volume snapshots stored in S3
  * AWS Cloudtrail - store api calls in logs, logs sent to preconfigure storage bucket
## 1.5 Pricing: Region specific
### Additional costs
  * Request costs: put, copy, post, get requests
    * charged per 10,000
  * Data transfer
    * Into S3 = free
    * Another region - $0.02/GB
## 1.6 S3 Anti-patterns: what is not good for
* Archiving data for long term use
* Dynamic data
* Structured data with queries
    
