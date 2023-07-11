# What
* Install a GUI on Ubuntu and connect it from Mac
* On EC2, install the following packages
```
sudo apt update
sudo apt install ubuntu-desktop
sudo apt install tightvncserver
sudo apt install gnome-panel gnome-settings-daemon metacity nautilus gnome-terminal
```
* After installation, start a vncserver. It will prompt you to enter the password. This is your remote access password
```
vncserver
```
* Open a config file, and fill in the following content
```
sudo vim ~/.vnc/xstartup
```

```
#!/bin/sh  
# Uncomment the following two lines for normal desktop: 
# unset SESSION_MANAGER 
# exec /etc/X11/xinit/xinitrc  
[ -x /etc/vnc/xstartup ] && exec /etc/vnc/xstartup 
[ -r $HOME/.Xresources ] && xrdb $HOME/.Xresources 
xsetroot -solid grey vncconfig -iconic & 
x-terminal-emulator -geometry 80x24+10+10 -ls -title "$VNCDESKTOP Desktop" & 
x-window-manager &
gnome-panel &
gnome-settings-daemon &
metacity &
nautilus &
gnome-terminal &
```

* Then kill the vncserver and start again
```
vncserver -kill :1
vncserver
```

* log in to your AWS and add the TCP port 5901 to allow the connection to VNC
```
ssh -i <your pem file> ubuntu@ec2–18–140–169–22.ap-southeast-1.compute.amazonaws.com -L 5901:127.0.0.1:5901
```

* On the mac, use the Screen Sharing client (in `Finder's` `Go` menu, click `Connect to Server`, then enter the address `vnc://192.168.0.6`

![vnc](https://github.com/HemingwayLee/cloud-cheatsheet/assets/8428372/a2777259-533d-4605-a6e7-87093fa24777)


## Check how many vnc servers are running
```
ps -ef | grep vnc
```


