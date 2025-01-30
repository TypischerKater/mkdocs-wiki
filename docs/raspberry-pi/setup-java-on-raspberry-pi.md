---
tags:
  - raspberry-pi
---

# Setup Java on Raspberry PI

Update your machine to be up to date
```bash
  sudo apt update && apt upgrade -y && reboot
```

Install Java 8 or Java 17 with `openjdk-8-jdk` or `openjdk-17-jdk` and show version after installation
```bash
  sudo apt install openjdk-17-jdk -y 
  sudo java -version
```