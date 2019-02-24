# cloud-cheatsheet

# Comparison
AWS, Azure, Google Cloud
EC2, Virtual Machines, 
ECS, Azure Container Service (ACS),
EC2 Container Registry, Azure Container Registry,
EKS, Azure Kubernetes Service (AKS),
Lambda, Azure Functions,
AWS Auto Scaling, Virtual Machine Scale Sets,
S3, Azure Storage,
RDS, SQL Database,
DynamoDB, Cosmos DB,
ElastiCache, Azure Redis Cache,

# Knowledge
CloudFormation (Template (in json) -> designer to show the graph -> building actual S3, RDS, EC2, ...)
Elastic Load Balancing (Auto Scaling: Add more EC2 (in auto-scaling group) when peak traffic is coming)
EC2 - AWS’s backbone 
AWS Lambda (serverless)
ElasticCache Redis (cache implementation)

API gateway (Resource (Lambda, EC2, ...) + Method (GET, POST, ...) + Deploy)
Why: Caching, Versioning, Metering, Throttling, …
API Version 1: for old application
API Version 2: for new application

AWS Redshift: Data warehouse is a system used for reporting and data analysis, and is considered a core component of business intelligence.

# Tips

## ssh (`<user>` is `your_user_name` in GoogleCloud and it is `ubuntu` in AWS)

```
ssh -i ~/.ssh/<my.pem> <user>@<ip>
```

```
ssh -F /dev/null <user>@<ip>
```

* For GoogleCloud, we need to set `VPC networks` before creating VM (Compute Engine)
1. ssh via Google web console
2. Copy the `key.pub` file contents
3. Append the contents to `~/.ssh/authorized_keys` file

# Ref
https://docs.microsoft.com/en-us/azure/architecture/aws-professional/services
