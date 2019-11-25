# AWS

## AWS Infrastricture: Components
1. Availability zones (AZs)
2. Region
3. Edge locations
4. Regional edge caches

## 1.1 Availability zones: physical aws data centers (a, b, c)
* Contain resources we provision in our VPCs
* Use atleast two for **high availability**
## 1.2 Region: AZs linked together - low latency resilient connections
* AZs geographically close (usually same city)

![Diagram](https://github.com/Assad-Zahieer/BobsProject/blob/master/aws-infrastructure.jpg)

## 1.3 Edge locations: aws sites deployed in major cities
* Reduce latency
* Used by end user - product owner can't select an edge location

## 1.4 Regional edge cache: store data for edge locations
* When data no longer available at edge loacation
