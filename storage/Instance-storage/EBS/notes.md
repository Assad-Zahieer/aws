# Amazon Elastic Block Storage

## Overview
* Block level storage for EC2 instances
* Persistant storage
* Elastically scalable storage
* Not highly available
  * unlike S3 EBS is not replicated across  multiple AZs
* Seperate to EC2
  * like external hard drive
  * each storage volume attached to 1 instance

## 4.1 EBS Snapshots - point in time back-up (stored in S3)
* Create new volume from snapshots
* Manual or scheduled
* incremental (only add changes therefore quicker)

## 4.2 EBS Volume Types
### SSD - gp2, io1
* More suitable for smaller data blocks
  * e.g DB using transactional workloads
#### General purpose SSD (gp2)
* Recommended for most workloads
* Low latency
* System boot volume
#### Provision IOPS SSD (io1)
* For i/o instensive workloads
  * Large databases
### HDD - Cold HDD, throughput optimized
* More suitable for larger blocks
  * e.g. big data, logging
#### Cold HDD (SC1) 
* Can't be used as boot volumes
* Lowest cost 
#### Throughput optimised HDD (ST1)
* For frequently accessed data
* ***Throughput = How much data travelling through a channel***
* ***Bandwidth = Maximum rate of data transfer through a channel***

## 4.3 Encryption - Both at rest and in transit
* Managed by EBS (checkbox)
* Aes-256 encryption algorythm
  * Interact with key management service (AWS KMS)
  * Also used to encrypt snapshots

## 4.4 Pricing
* **Pay for provisioned** including unused storage

## 4.5 Antipatterns
* Temporary storage (use EC2 instance storage)
* Multi-instance access
* Not highly available (use S3 or elastic file system)

