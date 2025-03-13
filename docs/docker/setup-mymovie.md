---
tags:
  - docker
---

# Setup MyMovie

## Install MyMovie

Replace the placeholders and save the file as `docker-compose.yml`
```yaml
version: '3'

services:
  mymovie-database:
    image: mariadb:latest
    container_name: mymovie-database
    restart: always
    networks:
      - mymovie-network
    environment:
      MYSQL_ROOT_PASSWORD: <Replace with your MYSQL password only letters and numbers no special charakters>
      MYSQL_DATABASE: mymovie
      MYSQL_USER: mymovie
      MYSQL_PASSWORD: <Replace with your MYSQL password>
    ports:
      - "3306:3306"

  mymovie-app:
    image: typischerkater/mymovie:latest
    container_name: mymovie-app
    restart: always
    networks:
      - mymovie-network
    environment:
      MYSQL_DATABASE: mymovie
      MYSQL_USER: mymovie
      MYSQL_PASSWORD: <Replace with your MYSQL password>
    ports:
      - "80:80"
    depends_on:
      - mymovie-database

networks:
  mymovie-network:
    driver: bridge
```

Open a console in the folder where the `docker-compose.yml` is and run the `docker-compose.yml` file
```bash
docker-compose up -d
```

## Update MyMovie
Go to the folder where the `docker-compose.yml` file is and run the pull command
```bash
docker-compose pull
```

Next run the `docker-compose.yml` file again to update the container with the new images
```bash
docker-compose up -d
```