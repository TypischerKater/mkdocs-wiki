---
tags:
  - proxmox
  - lxc
---

# Install Docker on an LXC Container

- Important the LXC container must be `unpreviliged` and `Nesting` and `keyctl` must be activated.

Update your machine to be up to date
```bash
apt update && apt upgrade -y && reboot
```

Install Docker and set up that Docker starts when container starts
```bash
apt install docker.io
systemctl start docker
systemctl enable docker
```

Install docker-compose and check the version after installation replace `1.31.0` with the newest docker compose version
```bash
apt install curl 
curl -L "https://github.com/docker/compose/releases/download/2.31.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
chmod +x /usr/local/bin/docker-compose
docker-compose --version
```

Install portainer
```bash
docker volume create portainer_data
docker run -d -p 8000:8000 -p 9000:9000 --name=portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ee:2.19.0
```

[Documentation Website](https://apfelcast.com/docker-container-unter-proxmox-betreiben-home-server-selbst-bauen-teil-15/)