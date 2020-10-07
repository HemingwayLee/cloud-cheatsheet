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

## `scp` packages into a super secure VM
* Setup the same environment with docker locally 
* Install packages in the environment
* `zip` and `docker cp` all installed packages from docker to local mac
* `scp` the zip file into the target super secure VM on the cloud
* `unzip` and install package from files in the VM
