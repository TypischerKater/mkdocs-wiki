---
tags:
  - proxmox
  - lxc
---

# Expand storage from LXC Container

Go to the shell of proxmox
```bash
pct resize 102 rootfs 32G
```
- `102` is the container id from proxmox and `32G` is the new size for the storage
