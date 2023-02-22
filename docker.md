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

- Why is this a big deal?
- How did it work before Docker?

---

# What problems Docker solves?

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
- [x] Dependency version configicts etc.
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
