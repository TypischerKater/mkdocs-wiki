---
tags:
  - proxmox
  - lxc
---

# Passthrough HDD to LXC container Proxmox

- Go to the shell of proxmox
- With this command the mounted drive folder from NAS here `NexcloudData` from proxmox here in `/mnt/NextcloudData` will be mounted to `mnt/hdd` folder `hdd` on the vm with id `100`
```bash
  pct set 100 -mp0 /mnt/NextcloudData,mp=/mnt/hdd/
```