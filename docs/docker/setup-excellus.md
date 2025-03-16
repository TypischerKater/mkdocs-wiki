---
tags:
  - docker
---

# Setup Excellus

## Install Excellus

Replace the placeholders and save the file as `docker-compose.yml`
```yaml
version: '3'

services:
  excellus-database:
    image: mariadb:latest
    container_name: excellus-database
    restart: always
    networks:
      - excellus-network
    environment:
      MYSQL_ROOT_PASSWORD: <Replace with your MYSQL password only letters and numbers no special charakters>
      MYSQL_DATABASE: excellus
      MYSQL_USER: excellus
      MYSQL_PASSWORD: <Replace with your MYSQL password>
    ports:
      - "3306:3306"

  excellus-app:
    image: typischerkater/excellus:latest
    container_name: excellus-app
    restart: always
    networks:
      - excellus-network
    environment:
      MYSQL_DATABASE: excellus
      MYSQL_USER: excellus
      MYSQL_PASSWORD: <Replace with your MYSQL password>
    ports:
      - "80:80"
    volumes:
      - "/root/excellus/itemFiles:/app/itemFiles"
    depends_on:
      - excellus-database

networks:
  excellus-network:
    driver: bridge
```

Open a console in the folder where the `docker-compose.yml` is and run the `docker-compose.yml` file
```bash
docker-compose up -d
```

## Update Excellus
Go to the folder where the `docker-compose.yml` file is and run the pull command
```bash
docker-compose pull
```

Next run the `docker-compose.yml` file again to update the container with the new images
```bash
docker-compose up -d
```

📖 [More Detail Excellus](https://brunosolf.de/excellus/)
