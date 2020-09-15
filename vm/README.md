# Note
* Test connection from GUI
* Download pem key and connect to VM
```
ssh -i ~/.ssh/<my.pem> <user>@<ip>
```
 
* Put SSH public key to GUI and connect it
```
ssh -F /dev/null <user>@<ip>
```

* Auto shutdown can be set
* Ports can be opened by adding inbound port rule
  * nginx (or other http servers) need to be running inside VM (listening to the port which is opened)



