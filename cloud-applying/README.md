# Why we need the cloud
* Reduce the cost of maintaining Hardware & Software & IT related stuff
  * VM services are easier to use/setup/deploy/snaphot/update/rollback
    * Bs-series: low-cost solution
    * Fsv2: Compute optimized
    * Dv3: general purpose
    * Ev3: Memory optimized
  * Monitoring services is easier (e.g., charts/reports/status)
  * Easier to do Disaster recovery (DR) and Replication

* Better computational power and pay as you go

# Choose between private cloud, public cloud, and hybird cloud

![terms](https://i.imgur.com/Aj0HhN7.jpg)

![pass](https://user-images.githubusercontent.com/8428372/90464008-51d40b00-e147-11ea-86a0-a5f5a175e050.png)

* Most of services on Azure are PasS and IaaS

# Difficulties of using cloud
* Services are not familiar

# Difficulties of migrating current projects to the cloud 
* infrastructure is different
  * connection to database services or azure file system
  * installing and setting up the environment of services on the cloud
  * change the existing code to be stateless

# Applying cloud step-by-step
* Empty project
  * Learn to use services on the cloud
* PoC project
  * Modifying existing projects to fit into the cloud
* Project without client data
  * Handling data on the cloud
* Real project

## Location
* Location is important because the data should stay in specific conuntry
* Azure does not have data center in Taiwan (2020/07/01), AWS and GCP have

# Ref
https://www.slideshare.net/AmazonWebServices/panel-discussion-76989087  

# Proposal
## Overview
- Develop and deploy a PoC project (might not be webapp) and a open data project to Azure

## Technology Summary
- Python, Django, Postgresql, ReactJs, Azure, Git, and others ...

## Return on Investment (ROI) Estimation
- Cost
   - 3*4 man months
   - Azure services in SANDBOX for 3 months
- Benefit 
   - Japan and/or Global connection
   - Knowledge of running projects on the cloud
   - Able to move projects to the cloud smoothly in the future
   - Able to show/sell projects/source-code to other countries (Thai or Malaysia)

## Project Schedule
- [1-2 weeks] Discover Requirements (e.g., What services we need on the cloud)
  - Visit stakeholders
  - Prioritize Azure services
- [2-4 weeks] Learn & use Azure services and then document them
- [2-4 weeks] Develop a PoC project and a open data project on Azure

## Deliverable List
- Azure DevOps git repos
  - Azure DevOps (PoC webapp project and open data project) -> CI\CD -> VM and AKS (global or Japan)
- Docuemnts of cloud deployment and cloud operations
  - VM, ACR, Storage Account, PostgresSQL, and AKS
  - Machine learning related services
- Architecture diagrams
  - The template for future projects on the cloud
  - For security team to review security issues
- Real cost estimation diagram of moving every project to the cloud

