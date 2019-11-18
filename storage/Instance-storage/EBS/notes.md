# Amazon Elastic Block Storage

## Overview
* Block level storage for EC2 instances
* Persistant storage
* Seperate to EC2
  * like external hard drive
  * each storage volume attached to 1 instance

## 4.1 EBS Snapshots - point in time back-up (stored in S3)
* Create new volume from snapshots
* Manual or scheduled
* incremental (only add changes therefore quicker)
