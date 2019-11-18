Full text: https://docs.aws.amazon.com/vpc/latest/userguide/vpc-subnets-commands-example.html

# 1. Create vpc
**aws ec2 create-vpc --cidr-block 10.0.0.0/16**
* cidr block is the only required argument for aws vpc
* /16 netmask = largest IPv4 subnet & VPC
* more options: https://docs.aws.amazon.com/cli/latest/reference/ec2/create-vpc.html

# 2. Create two subnets
**aws ec2 create-subnet --vpc-id vpc-2f09a348 --cidr-block 10.0.1.0/24**
**aws ec2 create-subnet --vpc-id vpc-2f09a348 --cidr-block 10.0.0.0/24**
* both required arguments - can add availability zone and other args
* subnet CIDR must be within VPC CDDR block range
* more options: https://docs.aws.amazon.com/cli/latest/reference/ec2/create-subnet.html

# 3. Make subnet public
* Must attach Internet gateway to VPC, create custom route table and configure routing for subnet to internet gateway
## 3.1 Create Internet gateway
**aws ec2 create-internet-gateway**
## 3.2 Attach the Internet gateway to your VPC
**aws ec2 attach-internet-gateway --vpc-id vpc-2f09a348 --internet-gateway-id igw-1ff7a07b**
* gateway-id from 3.1
## 3.3 Create custom route table
**aws ec2 create-route-table --vpc-id vpc-2f09a348**
## 3.4 Create a route in the route table that points all traffic (0.0.0.0/0) to the Internet gateway.
**aws ec2 create-route --route-table-id rtb-c1c8faa6 --destination-cidr-block 0.0.0.0/0 --gateway-id igw-1ff7a07b**
* route table id from 3.3
## 3.5 Associate route table with a subnet
**aws ec2 associate-route-table  --subnet-id subnet-b46032ec --route-table-id rtb-c1c8faa6**
* use aws ec2 describe-subnets to get id can --filter
## 3.7 (optional) instance launched into subnet automatically given a public IP address
**aws ec2 modify-subnet-attribute --subnet-id subnet-b46032ec --map-public-ip-on-launch**
* Otherwise, you should associate an Elastic IP address with your instance after launch to connect via internet

# 4. Launch instance into subnet
## 4.1 Create key-pair .pem
**aws ec2 create-key-pair --key-name MyKeyPair --query 'KeyMaterial' --output text > MyKeyPair.pem**
**chmod 400 MyKeyPair.pem**
## 4.2 Create security group with SSH access from anywhere
**aws ec2 create-security-group --group-name SSHAccess --description "Security group for SSH access" --vpc-id vpc-2f09a348**
**aws ec2 authorize-security-group-ingress --group-id sg-e1fb8c9a --protocol tcp --port 22 --cidr 0.0.0.0/0**
* 0.0.0.0/0, enables all IPv4 addresses SSH access to instance, in production use specific IP
## 4.3 launch ec2 instance into subnet - using security group and key pair
**aws ec2 run-instances --image-id ami-a4827dc9 --count 1 --instance-type t2.micro --key-name MyKeyPair --security-group-ids sg-e1fb8c9a --subnet-id subnet-b46032ec**
## 4.4 SSH (linux example)
**ssh -i "MyKeyPair.pem" ec2-user@52.87.168.235**
* MyKeyPair.pem = downloaded key file

# 5. Delete all
- **aws ec2 delete-security-group --group-id sg-e1fb8c9a**
- **aws ec2 delete-subnet --subnet-id subnet-b46032ec**
- **aws ec2 delete-subnet --subnet-id subnet-a46032fc**
- **aws ec2 delete-route-table --route-table-id rtb-c1c8faa6**
- **aws ec2 detach-internet-gateway --internet-gateway-id igw-1ff7a07b --vpc-id vpc-2f09a348**
- **aws ec2 delete-internet-gateway --internet-gateway-id igw-1ff7a07b**
- **aws ec2 delete-vpc --vpc-id vpc-2f09a348**
