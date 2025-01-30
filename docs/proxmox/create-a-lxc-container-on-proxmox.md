---
tags:
  - proxmox
  - lxc
---

# Create a LXC Container on Proxmox

- Go to proxmox
- Click on the `Create CT` button

| Parameter `General`      | Values need to change                 |
|:-------------------------|:--------------------------------------|
| `CT ID`                  | The ID from our container `101`       |
| `Hostname`               | The name of the container `Test-Name` |
| `Password`               | Password `testPassword`               |

| Parameter `Template`     | Values need to change                                                   |
|:-------------------------|:------------------------------------------------------------------------|
| `Template`               | Template of the container `ubuntu-24.04-standard_24.04-2_amd64.tar.zst` |

| Parameter `Memory` | Values need to change                            |
|:-------------------|:-------------------------------------------------|
| `Memory (MiB)`     | Memory `1024` for 1GB `2048` for 2GB etc...      |
| `Swap (MiB)`       | Swap Memory `1024` for 1GB `2048` for 2GB etc... |

| Parameter `Network` | Values need to change                           |
|:--------------------|:------------------------------------------------|
| `Gateway (IPv4)`    | IP address from the router `192.168.178.1`      |
| `IPv4/CIDR`         | Use free unused IP address `192.168.178.100/24` |

- Don't check the button `Start after created` button
- Click finish and the container gets created
- Click on the created LXC container and go to the `options` tab and double click on `features`
- Make sure `keyctl` and `Nesting` is checked and click OK
- Now start the container and go to the `Console` tab
- Log into the container with `root` and the password here `testPassword`
- To enable ssh login run this command `nano /etc/ssh/sshd_config` and find `#PermitRootLogin prohibit-password`
- Replace `#PermitRootLogin prohibit-password` with `PermitRootLogin yes`
- And save the file with `Strg + o` and exit with `Strg + x`
- Update and reboot the container with `apt update && apt upgrade -y && reboot`