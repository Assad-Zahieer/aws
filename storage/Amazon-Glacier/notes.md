# Amazon Glacier: Low cost, long term data archiving solution

## Overview
  * Durable as S3 (11 9s)
  * Retrieval up to several hours
  * Glacier dashboard can only be sued to create vaults
    * operations must be carried out through CLI

## 2.1 Data Structure - vaults & archives
  * vault = container for archives
  * unltd archives
  
## 2.2 Data Into Glacier
  1. Create vault
  2. move date into glacier
    * via API or SDK or S3 lifecycle rules

## 2.3 Data Retrieval - Using API, SDKs
### Retrieval job: options
1. Expedited: 1-5 mins
    1. 250 MB archive limit
    2. Cost = $0.03 per GB
2. Standard: 3-5 hours
    1 No size limit
3. Bulk: cheapest
    1. 5-12 hours for Petabytes of data
  
## 2.4 Security: AES-256 (advanced encryption standard) algorythm used to encrypt data
* IAM - I.D. based policies
* Vault access policies: resourse based (similar to bucket policies)
  * each vault only has one
* Vault lock policy: same as VAccess policy but **can't be changed**
1. A numbered list
    1. A nested numbered list
    2. Which is numbered
