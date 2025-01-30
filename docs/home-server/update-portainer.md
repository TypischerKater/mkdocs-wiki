---
tags:
  - portainer
---

# Update Portainer

Update your machine to be up to date
```bash
  apt update && apt upgrade -y && reboot
```

Get the container id of portainer
```bash
  docker ps
```

Stop all the containers and also the container of portainer
```bash
  docker stop 0cc703e3d6f1
```

Remove the container of portainer
```bash
  docker rm 0cc703e3d6f1
```

Remove portainer Image currently installed `here version 2.19.0`
```bash
  docker rmi portainer/portainer-ce:2.19.0
```

Run the first command like setting up portainer `replace version 2.19.0 with the newst version`
```bash
  docker run -d -p 8000:8000 -p 9000:9000 --name portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ee:2.19.0
```

[YouTube Explanation](https://www.youtube.com/watch?v=M365jgJ0O2E)