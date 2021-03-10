# Lambda
* Lambda functions are executed in the following orders
  * an appropriate `runtime` (nodejs or python) container is started
    * We can only select the pre-defined runtime, can not create our own runtime
  * `code` (in zip file format) are loaded from s3
* The container will be paused after execution
  * Resumed if there are other requests in some amount of time
  * Deleted if no other request in some amount of time
* Lambda is billed on a combination of the number of requests, memory, and seconds of function execution
* When: unpredictable or inconsistent workloads

# Fargate 
* It is AWS solution to run docker containers without managing any servers for container orchestration
  * It exists with ECS, we can not run Fargate without [ECS](https://github.com/HemingwayLee/container-services-showcase/tree/main/ecs)
  * The other option of running ECS is EC2
* Containers are always running, there is no warmup time caused by Fargate, not like Lambda
* Fargate is billed on CPU and memory used per hour
* When: consistent workloads or applications that want to use docker generally

