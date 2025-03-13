---
tags:
  - proxmox
  - lxc
---

# No Backup on unprivileged LXC container possible

Go to the shell of proxmox
```bash
nano /etc/vzdump.conf
```
- add this line `tmpdir: /tmp` to the vzdump default settings safe and exit now it works

[Documentation Website](https://www.reddit.com/r/Proxmox/comments/9ucz3o/lxc_unprivileged_backup_task_failing/)
