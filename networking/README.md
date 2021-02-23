# VPC (Virtual Private Cloud)
It is a service that lets you launch AWS resources (e.g., EC2, ECS) in a logically isolated virtual network  
* Selection of your own IP address range
  * Specify a range of IPv4 addresses for the VPC in the form of a Classless Inter-Domain Routing (CIDR) block (e.g., `10.0.0.0/16`)
* Creation of subnets
* Configuration of route tables and network gateways

![vpc-diagram](https://docs.aws.amazon.com/vpc/latest/userguide/images/vpc-diagram.png)

## You can
* Create a public-facing subnet for your web servers 
* Place your backend systems, such as databases or application servers, in a private-facing subnet with no internet access
* Use multiple layers of security, including security groups and network access control lists

![subnets-diagram](https://docs.aws.amazon.com/vpc/latest/userguide/images/subnets-diagram.png)

## Regions and Availability Zones
Each region is a separate geographic area. Each region has multiple, isolated locations known as `Availability Zones`  

## Subnet
* Each subnet must reside entirely within one Availability Zone and cannot span zones

## IP Address
* Each instance in AWS gets 2 IP address
  * a private ip address 
  * a public ip address

## Security group
* A security group acts as a virtual firewall that controls the traffic for one or more instances

## Terms
* Region: Think of the office building
* Availability Zone: Think of each floor
  * A building can have more than one floor
* VPC: Each department in the office
  * VPCs span across availability zones in a region
  * Each department in your office can span across different floors
* Subnet: Each Suite represents a subnet
  * Like how each subnet resides ONLY within an availability zone, each suite will be part of the floor and it won’t span across floors
* IP Address: Each desk within a suite

# Ref
https://www.infoq.com/articles/aws-vpc-explained/  
https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Subnets.html  
