# Lambda
## Overview
* Serverless compute service - run apps without managing EC2 instances
    * Serverless from users perspective
* Charges when code is running
    * per 100 ms of use
## 1. Components
1. **Lambda function** - your code, called on by triggers
2. **Event source** - AWS service to trigger lambda functions
3. **Trigger** - operation(s) from event source, calls lambda function
4. **Downstream resource** - resources rewuired during function execution
5. **Log streams** - logs
## 2. Steps
1. Upload code
2. Configure lambda functions to execute code on specific trigger
    * Functions are stateless so copies can be launched fast
    * *Stateless* - no affinity (to underlying infrastructure)
    * Trigger example - object uploaded to S3 bucket
3. AWS runs code (upon trigger, as per lamda function)
    * using compute power as defined
4. AWS records compute time (ms) and n.o. lambda functions to get cost
## 3. Example
* File processing - upload photo to S3
    * Event - user clicks upload
    * Trigger - operation from event start lambda function
    * Lamda function - code to upload photo to S3
