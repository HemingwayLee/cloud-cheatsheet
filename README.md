# cloud-cheatsheet

## Comparison
| AWS | Azure | Google Cloud |
| --- | --- | --- |
| EC2 | Virtual Machines | Compute Engine |
| ECS | Azure Container Service (ACS) |  | 
| EC2 Container Registry (ECR) | Azure Container Registry (ACR) | Container Registry | 
| EKS | Azure Kubernetes Service (AKS) | Google Kubernetes Engine | 
| Lambda | Azure Functions | Cloud Functions | 
| AWS Auto Scaling | Virtual Machine Scale Sets | Managed instance groups (MIGs) | 
| S3 | Azure Storage Account | Cloud Storage | 
| RDS | SQL Database (or Azure Database for PostgreSQL) | Cloud SQL |   
| DynamoDB | Cosmos DB | Cloud Bigtable | 
| ElastiCache | Azure Redis Cache | Memorystore | 
| AWS CLI | Azure CLI | unified CLI | 

### Comparison
https://docs.microsoft.com/en-us/azure/architecture/aws-professional/services  
https://cloud.google.com/docs/compare/aws  

## Commonly Used Services
* [VM](https://github.com/HemingwayLee/cloud-cheatsheet/tree/master/vm)
  * for demo
  * easy to setup
  * Pay as you go (if we use ACR, we need to pay everyday)
* Azure Container Registry (ACR)
  * like private Docker Hub
  * We can run containers in Azure Container Instance (ACI), Azure App Service, and Azure Kubernetes Service (AKS) 
  * Easy to setup the same environment
  * From maintenance point of view, limited packaged services reduces the attack surface overall
* Storage Account
* [Azure Database for PostgreSQL](https://github.com/HemingwayLee/cloud-cheatsheet/tree/master/postgresql)
* Azure Kubernetes Service (AKS)

## Knowledge
* `CloudFormation` (Template (in json) -> graph editor to show the graph -> building actual `S3`, `RDS`, `EC2`, ...)  
* `Elastic Load Balancing` (Auto Scaling: Add more `EC2` (in auto-scaling group) when peak traffic is coming)  
* `EC2` - AWS’s backbone, `ECS` is based on `EC2` (`ECS` is basically a logical grouping of `EC2` machines/instances)   
* AWS `Lambda` (serverless), the money is paid by traffic 
  * Lambda functions are executed in the following orders
    * an appropriate runtime (nodejs or python) container is started 
    * code are loaded from `s3`
  * The container will be paused after execution
    * Resumed if there are other requests in some amount of time
    * Deleted if no other request in some amount of time
  * Disk size, memory, number of files are limited
  * Auto-scaling is supported 
* `ElasticCache` contains Redis and Memcache (cache implementation)
* `ACR\AKS` is better than `ECR\EKS`
* `ECS` has better supports on AWS, but using k8s is more flexibile
* `RDS` vs `EC2` with database installed manually
  * `RDS` is easier to use (backup, maintain, replicas, monitoring, ...)
  * `EC2` is cheaper and it has more controls (e.g., OS, settings, ...)

`Azure Container Instance` (`ACI`) is for running docker instances  
`Azure Container Registry` (`ACR`) is for storing formatted images  

`API gateway` or `API Management` (Resource (Lambda, EC2, ...) + Method (GET, POST, ...) + Deploy)  
Why: Caching, Versioning, Metering, Throttling, ...  
API Version 1: for old application  
API Version 2: for new application  

`Data Lake` is based on Hadoop  

`Databricks` is base on spark (spark can be bulit on top of `S3` or `k8s`)  
We can run Notebook on top of `Databricks`  
We can choose `python`, `R`, or `SQL` with Notebook

`AWS Redshift`: Data warehouse is a system used for reporting and data analysis, and is considered a core component of business intelligence.  

## Load Balancer
`Azure Load Balancer`: It load-balances traffic at layer 4 (TCP or UDP)  
`Azure Application Gateway`: It is a layer 7 load balancer  

## Firewall
`Azure Application Gateway - Web Application Firewall`:  
* It can be used to do SSL termination
* It protects you from SQL injection or XSS 
* This protection uses rules from the [Open Web Application Security Project](https://owasp.org/www-project-top-ten/)   

`Azure Firewall`:   
* It can be used to limit outbound traffic to a specified list of FQDN including wild cards
* You can set the rules to allow or deny network access by source and destination IP address, port, and protocol and since the Azure Firewall is fully stateful (L3-L7)

`Azure Network Security Groups (NSG)`:  
* It allow you to filter traffic to and from your resources in an Azure virtual network  
* Usually, NSG for VNET, Firewall for public access

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
* There are some services only exist in specific region (e.g., NC series VM in US)

### Azure DevOps
* `Azure DevOps` is better than `gitlab` + `gitlab-ci`
* We can create multiple repo and multiple pipeline on a project
* Both `gitlab-ci` and `Azure DevOps` use yml file for CI\CD
* Its yml file structure is more complicated than `gitlab-ci`
  * Run in condition
  * Run in parallel
* Test report can be generated with nice GUI which contains iframe (url need to be https) so that we can provide customized charts
* Secret variables can be saved at
  * Repo level
  * Project level
  * Azure level (`KeyValut`)
* Services connection need to be set in order to connect and deploy to Azure
* It seperates CI and CD into `Build Pipeline` and `Release Pipeline`
* Problem: not too many discussion on the stack overflow

### Azure CLI
* need to do `az login` first
  * `az login` does not work with accounts that have 2-factor authentication
* Azure DevOps provides build-in tasks for Azure CLI
* `az container create` will not wait for `--command-line` option to complete, so we need to use `az container show` periodically to check if we can do `az container delete`
* some commands will return JSON, we can use `query` option to parse JSON

### Azure Data Lake (Gen 2)

### Azure Machine Learning Service Workshop

#### Run jupyter note on azure
#### AutoML

# Private Cloud
* A lot of company use `OpenStack`

![jp_private_cloud](https://image.itmedia.co.jp/ait/articles/1706/13/l_si_iaas-share-01.jpg)

![jp_private_cloud2](https://it.impressbm.co.jp/mwimgs/d/4/-/img_d45808afbf2230b1b2e9e1e5a779208385215.jpg)

## State of DevOps
https://services.google.com/fh/files/misc/state-of-devops-2019.pdf
