# Elastic Container Registry
## Overview
* Secure location to store and manage *docker images*
* Fully managed service
## 1. Registry
* Where docker images are hosted and stored
* controlled via **IAM** policies
## 2. Authentication Token
* Required to access registry
1. aws ecr get-login --registry-ids <XXXXX> --no-include-email
    * output = docker login command
2. paste output into docker terminal
    * authentication token produced - last 12 hours
## 3. Repository Policies
* Repositories allow grouping and securing of images
* Resource based policies
    * Add principles: who has access to what?
    * e.g. aws user able to access ecr:GetAuthorizationToken API call to access registry
    
