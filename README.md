# AWS-Networking
AWS setup 
Step 1: VPC Creation
Created a custom VPC named JM-VPC

CIDR block used: 10.0.0.0/16

This CIDR block allows for multiple subnet divisions in future configurations

DNS hostnames and DNS resolution were enabled to allow for easier EC2 instance interaction later

Step 2: Subnet Configuration
Public Subnet
CIDR block: 10.0.1.0/24

Placed in one availability zone

Intended for resources that require internet access (e.g., web servers)

Will be associated with a route table that includes a route to the Internet Gateway

Private Subnet
CIDR block: 10.0.2.0/24

Also placed in a separate availability zone

Intended for internal-only resources such as databases

No direct internet access; isolated within the VPC

Step 3: Internet Gateway
Created a new Internet Gateway

Attached it to the JM-VPC

This gateway is required to enable outbound internet traffic from the public subnet

Step 4: Route Table Configuration
Public Route Table
Created a custom route table

Added a route with destination 0.0.0.0/0 pointing to the Internet Gateway

Associated this route table with the public subnet (10.0.1.0/24)

Private Route Table
Used the default route table or created a new one for private subnets

No route to 0.0.0.0/0 or Internet Gateway

Only internal VPC communication allowed for resources in the private subnet

Summary
This setup demonstrates how to:

Create a VPC with a large address range

Segment networks into public and private subnets

Control traffic flow using route tables

Enable internet access for only selected subnets

This lab helped solidify my understanding of VPC design and routing concepts in AWS
