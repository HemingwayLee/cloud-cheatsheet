# What
* It is Domain Name System (DNS) web service
* We need to go to `registered domains` and pay the money
* Create `hosted zone`, add a sub-domain, and record (e.g., IP, AWS services like ELB, EKS, ...)

## HTTPS
* Create `SSL certificate` in `AWS Certificate Manager (ACM)`
  * Put domain name we created in Route53
  * We can select `DNS validation` adding a record to Route53
  * It will be in a pending status for a while
