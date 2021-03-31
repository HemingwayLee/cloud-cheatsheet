# Load Balancer
* We can do load balancing in 
  * Cloud Services (e.g., ELB)
  * k8s 
  * nginx

## AWS
* There are 3 types of load balancer
  * Application (HTTP/HTTPS)
  * Network (TCP/TLS/UDP)
  * Gateway (IP)
* it can be `internal` or `internet-facing`
* We need to choose 2 [availability zones (and subnets)](https://github.com/HemingwayLee/cloud-cheatsheet/tree/master/networking)
  * one of them can be empty
![internet_facing_load_balancer](https://docs.aws.amazon.com/ja_jp/elasticloadbalancing/latest/classic/images/internet_facing_load_balancer.png)
* We need to register `target groups`
* We can redirect `http` to `https` in `Listeners` tab
  * We can select `SSL certificate` (e.g., from `AWS Certificate Manager (ACM)`) when adding listener

### 503 Service Temporarily Unavailable
* check `security group`
* check `target groups`
  * [Reference](https://degaze-film.medium.com/aws-load-balancer-503-service-temporarily-unavailable-e1e91c0dfcdb)
