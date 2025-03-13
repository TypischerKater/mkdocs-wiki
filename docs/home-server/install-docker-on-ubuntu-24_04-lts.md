---
tags:
  - docker
---

# Install Docker on Ubuntu 24.04 LTS

- Update and reboot the container with `apt update && apt upgrade -y && reboot`

Step 1: Install Required Packages
```bash
apt install apt-transport-https curl
```

Step 2: Add Docker’s Official GPG Key
```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```

Step 3: Set Up Docker’s Stable Repository
```bash
echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | tee /etc/apt/sources.list.d/docker.list > /dev/null
```

```bash
apt update
```

Step 4: Install Docker Engine on Ubuntu 24.04 LTS
```bash
apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

In addition, check its status using the command below to confirm that everything is as expected:
```bash
systemctl is-active docker
```

## Uninstall Docker Engine

Install Docker Engine on Ubuntu 24.04 LTS
```bash
apt purge docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin docker-ce-rootless-extras
```

Then, manually remove the following two directories:
```bash
rm -rf /var/lib/docker
rm -rf /var/lib/containerd
```

[Documentation Website](https://linuxiac.com/how-to-install-docker-on-ubuntu-24-04-lts/)