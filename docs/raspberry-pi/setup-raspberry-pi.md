---
tags:
  - raspberry-pi
---

# Setup Raspberry PI

Update your machine to be up to date
```bash
sudo apt update && apt upgrade -y && reboot
```

Expand filesystem
```bash
sudo raspi-config
```
- Go to advanced options and a1 expand filesystem

Setup Remote Desktop
```bash
sudo apt-get install xrdp
```
- Manage Remote Desktop with commands `sudo service xrdp start | stop | restart | status`

Video problem with remote desktop
```bash
sudo adduser xrdp ssl-cert
sudo nano /etc/X11/xrdp/xorg.conf
```
- And find the line `Option DRMDevice` line and change it to `Option "DRMDevice" ""`
- Reboot raspberry pi

[Documentation Website video problem with remote desktop](https://forums.raspberrypi.com/viewtopic.php?p=2151746)