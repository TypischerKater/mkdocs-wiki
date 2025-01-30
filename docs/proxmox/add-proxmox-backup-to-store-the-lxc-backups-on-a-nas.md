---
tags:
  - proxmox
  - lxc
---

# Add Proxmox Backup to store the LXC Backups on a NAS

- Create a shared folder where the backup data should be stored on your NAS with NFS
    - Go to QNAP and go to `Network & File Services` then got to `Win/Mac/NFS/WebDAV` and go to `NFS Service` check that NFS is enabled
    - Go to `Provilege` and `Shared Folders` go and click on `edit shared folder permission` for the shared folder you want to share over NFS
    - Select `NFS host access` and enable access right and ad the IP address from proxmox and give it read and write permissions
- In proxmox go to datacenter and then the tab `Storage`
- Click on `Add` and select `NFS`

| Parameter `NFS` | Values need to change                                                                                     |
|:----------------|:----------------------------------------------------------------------------------------------------------|
| `ID`            | Name of the storage                                                                                       |
| `Server`        | IP address from the NAS                                                                                   |
| `Export`        | here you can check the shared folders available through nfs here select the shared folder you want to use |
| `Content`       | select `VZDump backup file`                                                                               |

- Then click on Add
- In proxmox go to datacenter and then the tab `Backup`

| Parameter `Backup Job` | Values need to change                                                     |
|:-----------------------|:--------------------------------------------------------------------------|
| `Storage`              | select the storage from the NAS for example what we created before Backup |
| `Schedule`             | select sunday at 1am                                                      |
| `Selection mode`       | select `All`                                                              |
| `Compression`          | select `ZSTD`                                                             |
| `Mode`                 | select `Snapshot`                                                         |

[Documentation Website](https://www.youtube.com/watch?v=cKepvGRtSxc)