# Amazon Elastic File System

## Overview
* Managed service (checkbox encryption, high availability)
* File level storage service (windows OS not supported)
* Optional shared file system
* Regional (across multiple AZs) therefore highly available
* Only compatible with linux (NFS V4.0 & 4.1)

## 5.1 Creating EFS
* Select VPC
* Mount target
    * Automatically created across AZs where there are EC2 instances
    * Allow EC2 -> EFS connection via configured mount target IP address
* Performance modes
  * General performance - maximum 7000 file system operations
  * Maximum I/O performance - > 7000 file system operations
 
## 5.2 EFS File Sync
* Transfer dat into EFS securelyvia sync agent

## 5.3 Pricing
* Data consumption per GB-months
  * Calculate GB-hours for a month
    * e.g. 80 GB used in 25 days and 5 GB for rest of the month
    * (80 * 25 * 24) + (5 * 6 * 24) = Ans
  * Divide by average hours in a month (745.76)
    * Ans/745.76

## 5.4 Anti-patterns
  * Archiving (use Glacier)
  * Relational DB (use EBS)
  * Temporary (EC2 instance storage)
