# WIRE-POD.DOCKER

Simple docker build from [kercre123/wire-pod](https://github.com/kercre123/wire-pod.git) repository project to a container in docker-compose.yml

### Key Notes
- macvlan example in `docker-compose.yml` to assign container lan side ip address, so host does not have to be renamed to `escapepod`
- One-Click setup provided (need to change LAN and IP configuration in `docker-compose.yml`)

---

## Table of Contents

- [OPENAI-GEMINI-DOCKER](#openai-gemini-docker)
  - [Prerequisites](#prerequisites)
  - [Setup](#setup-instructions)
  - [Run](#build-and-run-the-container)
  - [How to Use](https://github.com/PublicAffairs/openai-gemini/blob/main/readme.MD#how-to-use)
---

## Prerequisites

Ensure your host system has:
- **Git** installed
- **Docker** & **Docker Compose** installed

## Setup Instructions

1. Clone the required repositories:
   ```sh
   git clone https://github.com/PublicAffairs/openai-gemini.git
   git clone https://github.com/t00geek4u/openai-gemini-docker.git
   ```
2. Move the Docker files into the openai-gemini directory:
   ```sh
   mv openai-gemini-docker/Dockerfile openai-gemini
   mv openai-gemini-docker/docker-compose.yml openai-gemini
   rm -fr openai-gemini-docker
   cd openai-gemini
   ```

## Build and Run the Container

### Start in Foreground
To build and start the container in the foreground, run:
```sh
docker compose up
```

### Start in Detached Mode
To run the container in the background (detached mode), use:
```sh
docker compose up -d
docker logs openai-gemini
```
> **Note**: The container will listen on **port 11434** for API calls.

### One-Click Setup and Run
To setup and run in detached mode from script, use:
```sh
wget -qO- https://raw.githubusercontent.com/t00geek4u/openai-gemini-docker/main/setup_run.sh | bash
```


### For more information on How to Use, goto [_openai-gemini repository#how-to-use_](https://github.com/PublicAffairs/openai-gemini/blob/main/readme.MD#how-to-use)
