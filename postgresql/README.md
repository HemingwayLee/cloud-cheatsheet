# Note
## Azure
* Connection security setting on GUI
  * Deny public network access
  * Allow access to Azure services (provide ip range)
    * We can add current IP or all IPs from GUI
* Connection strings (with multiple programming languages) are on the GUI, we can just copy-and-paste them
* We can use terminal on the azure GUI to test the connection
* We can do replication, health check, CPU/memory usage, ... on the GUI

## AWS RDS
* Azure has better user experience
* Connection timeout issue checking
  * address and port
  * allow public option is on? or only allow access from other AWS services
  * network security group settings

### Test script
```
psql --host xxx.rds.amazonaws.com --port 5432 --username=postgres --password --dbname=postgres
psql -h xxx.rds.amazonaws.com -p 5432 -U postgres postgres
```

