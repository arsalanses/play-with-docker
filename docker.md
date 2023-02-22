---
title: Docker
author: Arsalanse
date: 2023-02-18
styles:
  style: monokai
  table:
    column_spacing: 3
    header_divider: "-"
---

# Arsalan Sefidgar (@arsalanse)
- DevOps engineer @G2tech
- www.g2tech.co

---
# History

##2008
- LXC

##2013
- Docker released to open source in March
- RedHat: Fedora, redhat enterprise, openshift

##2014
- Microsoft: next windows server release, and native support for the docker client
- Stratoscale: partnership with docker
- IBM: strategic partnership with docker

##2016
- docker introduces first commercial product

##2018
- open source community includes:
- 3.300+ captaines
- 47.000+ stars
- 14.000+ forks

---

# What is Docker?

- Virtualization software
- Makes developing and deploying applications much easier 
- Packages application with all the necessary dependencies, configuration, system tools and runtime
- Portable artifact, easily shared and distributed

---
# What problems Docker solves?
- Why is this a big deal?
- How did it work before Docker?

---

# **DEVELOPMENT** process before containers?

- Each developer needs to **install and configure** all services **directly on their OS** on their local machine
- [x] **Installation process different** for each OS environment
- [x] **Many steps**, where something can go wrong

---

# **DEVELOPMENT** process with containers?

- Own **isolated environment**
- Postgres packaged with all dependencies and config
- Start service as a Docker container using a **1 Docker command** 
- Command same for all OS
- Command same for all services
- **Easy to run different versions** of same app without any conflicts

```shell
docker run postgres
```

---

# **DEPLOYMENT** process before containers?

- Artifact and instructions handed over to Ops team
- Ops team handles installing and configuring apps and its dependencies
- [x] Installations and configurations done directly on the server's OS
- [x] Dependency version confilicts etc.
- [x] Human errors can happen
- [x] Back and forth communication

---

# **DEPLOYMENT** process with containers?

- Docker artifact includes everything the app needs
- No configurations needed on the server
- Less room for errors
- Run Docker command to fetch and run the Docker artifacts

---
# Virtual Machine vs Docker

- Why is Docker so widely used?
- What advantages does it have over Virtual Machines?
- What is the differences?

---

# Any questions to ask since here?

---

# Architecture

- Server
- Rest API
- Command Line Interface (CLI)
---

# images vs containers

---

# https://labs.play-with-docker.com/
# https://hub.docker.com/signup

---

```
docker run -i -t ubuntu /bin/bash (--interactive, --tty)
```

```
docker run -d -p 80:80 docker/getting-started
```

---

```
git clone https://github.com/G2Tech-co/docker-getting-started.git
```
```
docker build -t getting-started .
```
```
docker run -dp 3000:3000 getting-started
```
```
docker ps
docker stop <the-container-id>
docker rm <the-container-id>
```
---
# Persisting Database

```
docker volume create todo-db
```

```
docker run -dp 3000:3000 -v todo-db:/etc/todos getting-started
```

```
docker volume inspect todo-db
```
---
# Multi container apps

```
docker network create todo-app
```
```
docker run -d \
  --network todo-app \
  --network-alias mysql \
  -v todo-mysql-data:/var/lib/mysql \
  -e MYSQL_ROOT_PASSWORD=secret \
  -e MYSQL_DATABASE=todos \
  mysql:5.7
```
```
docker run -it --network todo-app nicolaka/netshoot
drill mysql
```
---

# Dev-Mode Container

```
docker run -d \
  -p 3001:3000 \
  -w /app \
  -v "$(pwd):/app" \
  --network todo-app \
  -e MYSQL_HOST=mysql \
  -e MYSQL_USER=root \
  -e MYSQL_PASSWORD=secret \
  -e MYSQL_DB=todos \
  node:18-alpine \
  sh -c "yarn install && yarn run dev"
```

```
vim src/static/js/app.js
line 109
```

```
docker logs -f
docker exec -it <mysql-container-id> mysql -p todos
select * from todo_items;
```
---
# What is next?
```
iptables -t nat -vnL
docker compose
docker stats
save/load export/import
update
history
events
```
---

# Bye
