---
tags:
  - proxmox
  - lxc
---

# Mount a shared folder from NAS to Proxmox

- On the NAS create a shared folder you want to mount and a user with the rights for the shared folder
- Go to the shell of proxmox
```bash
nano /etc/fstab
```
- add this line and updated to the correct values form the NAS `//192.168.178.41/PlexMedia /mnt/PlexMedia cifs username=Plex,password=1u1GX7ZlBQ5kJej9ZAG0U+,iocharset=utf8,noperm 0 0` to the file and safe and exit now it works importent check that the password has no special charecters because this can make a problem like `/` etc
- Now you need to create the folder on proxmox you want to mount to like here `mnt/PlexMedia` so create the PlexMedia folder in the mnt directory
- To mount the folder you need to run this command to connect with the NAS and the folder should be mounted correctly
```bash
mount -a
```
