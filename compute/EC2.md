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
  * Short-term use - best for dev environment
 * **On-demand capacity reservation** - reserve within specific AZ
* **Reserved instances**
  * *All upfront*: most discount, pay for 1 or 3 year time frame
  * *Partial upfront*: smaller upfront payment
  * *No upfront*
  * Use case - long term **predictable** workloads
 * **Scheduled instances** - reserve on recurring schedule
  * Charge even if you don't use the instance
  * e.g. bulk processing of data same time every week
  * Use for processes which are not continuously running
 * **Spot instances** - bid for unused ec2 compute resources
  * Not guaranteed for fixed time
  * Prices fluctuate - supply andf demand, bid < price 2 min warning given
  * Use for batch jobs b/c processes may be interupted
## 4. Tenancy
 * **Shared tenancy** - same host used by multiple customers
 * **Dedicated instance** - host on hardware only your account can access
 * **Dedicated host** - same as above but more control of physical host
## 5. User data
 * Commands run during 1st boot cycle of instance - e.g. software installation, OS
## 6. Storage Options
 * **Persistent storage** - attatch EBS volumes to instance (like external hard drive)
  * EBS volume seperate from instance - attatched via AWS network
 * **Ephermal storage** - local EC2 storage 
  * Physical attatched to host
  * Data is lost when instance is stopped or terminated (not rebooted)
  * K.A. *Instance store volumes*
## 7. Security
 * **Security group** - instance level firewall to manage traffic
 * **Key-pair** - encrypt login info
  * *Public key* - encrypts data (username, password)
   * Held by AWS
  * *Private key* - decrypts data: allow remote connection (linux SSH)
   * Your responsibility **DON'T LOSE or SHARE**
## 8. Status Checks
 * **System** status check - problem with host
  * e.g loss of power
  * stop/start to solve as this starts up instance on new server
 * **Instance** status checks - require your input
  * e.g. Incorrect network configuration
