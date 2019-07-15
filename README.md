# cloud-cheatsheet

## Comparison
AWS, Azure, Google Cloud  
EC2, Virtual Machines,  
ECS, Azure Container Service (ACS),  
EC2 Container Registry, Azure Container Registry,  
EKS, Azure Kubernetes Service (AKS),  
Lambda, Azure Functions,  
AWS Auto Scaling, Virtual Machine Scale Sets,  
S3, Azure Storage,  
RDS, SQL Database (or Azure Database for PostgreSQL),  
DynamoDB, Cosmos DB,  
ElastiCache, Azure Redis Cache,  

## Knowledge
* `CloudFormation` (Template (in json) -> graph editor to show the graph -> building actual `S3`, `RDS`, `EC2`, ...)  
* `Elastic Load Balancing` (Auto Scaling: Add more `EC`2 (in auto-scaling group) when peak traffic is coming)  
* `EC2` - AWS’s backbone, `ECS` is based on `EC2` (`ECS` is basically a logical grouping of `EC2` machines/instances)   
* AWS `Lambda` (serverless), the money is paid by traffic 
  * Lambda functions are executed in the following orders
    * an appropriate runtime (nodejs or python) container is started 
    * code are loaded from `s3`
  * The container will be paused after execution
    * Resumed if there are other requests in some amount of time
    * Deleted if no other request in some amount of time
  * Disk size, memory, number of files are limited
* `ElasticCache` contains Redis and Memcache (cache implementation)  

`Azure Container Instance` (`ACI`) is for running docker instances  
`Azure Container Registry` (`ACR`) is for storing formatted images  

`API gateway` (Resource (Lambda, EC2, ...) + Method (GET, POST, ...) + Deploy)  
Why: Caching, Versioning, Metering, Throttling, ...  
API Version 1: for old application  
API Version 2: for new application  

`Data Lake` is based on Hadoop

`AWS Redshift`: Data warehouse is a system used for reporting and data analysis, and is considered a core component of business intelligence.  

## Tips

### ssh (`<user>` is `your_user_name` in GoogleCloud and it is `ubuntu` in AWS)

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

### Create VM from sanpshot  
https://docs.microsoft.com/en-us/azure/virtual-machines/windows/create-vm-specialized-portal  

## Note

### Azure DevOps
* `Azure DevOps` is better than `gitlab` + `gitlab-ci`
* We can create multiple repo and multiple pipeline on a project
* Both `gitlab-ci` and `Azure DevOps` use yml file for CI\CD
* Its yml file structure is more complicated than `gitlab-ci`
  * Run in condition
  * Run in parallel
* Test report can be generated with nice GUI
* Secret variables can be saved at
  * Repo level
  * Project level
  * Azure level (`KeyValut`)
* Services connection need to be set in order to connect and deploy to Azure
* Problem: not too many discussion on the stack overflow

## Ref
https://docs.microsoft.com/en-us/azure/architecture/aws-professional/services
