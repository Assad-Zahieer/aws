# Elastic Kuberneties Service
## Overview
* Container orchestration for kuberneties
* Kuberneties infrastructure manged by AWS in control plane
* Your job to provision and maintain *worker nodes*
## 1. Control Plane
* Managed by AWS
* Run across *master node*
* Schedules containers onto nodes
    * In accordance with **declared computing requirements**
* unhealthy control plane nodes automatically patched
## 2. Worker Nodes
* Your responsibility
* Specific AMI used
* Connect to EKS endpoint
## 3. Steps
1. Create EKS service role
    * IAM service role allow EKS to provision and configure specific resources
    * amazon eks service policy
    * amazon eks cluster policy
2. Create VPC for EKS cluster
    * Use cloudformation
3. Install kubectl & AWS-IAM-Authenticator
    * https://docs.aws.amazon.com/eks/latest/userguide/install-kubectl.html
4. Create EKS cluster
5. Configure kubectl for EKS
    * AWS CLI - use update-kubeconfig command to create config file
6. Provision and configure worker nodes
7. Configure worker nodes to join cluster
    * curl -O https://amazon-eks.s3-us-west-2.amazonaws.com/cloudformation/2019-02-11/aws-auth-cm.yaml
    * replace <ARN instance role> with value from step 6
