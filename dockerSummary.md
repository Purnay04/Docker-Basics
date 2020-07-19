# Docker Summary
## 1. What is Docker?
* It is a set of _**platform as a service (PaaS)**_ products that uses _**OS-level virtualization**_ to deliver software in packages called _**containers**_.
which helps developers,system admins to develop, deploy and run applications.

## 3.Docker Image:
* A Docker image is containing everything needed to run an application as a container. This includes:
	 * **Code**
	 * **Libraries**
	 * **Environment variables**
	 * **Configuration files**
	 
* The image can then be deployed to any Docker environment and executable as a container.

## 4.Container:
* A Docker container is a _**runtime instance**_ of an _**docker image**_.

* From one image you can create multiple containers (all running the sample application) on multiple Docker platforms.

* A container is a runnable instance of an image. You can create, start, stop, move, or delete a container using the Docker API or CLI. You can connect a container to one or more networks, attach storage to it, or even create a new image based on its current state.

## 5.Docker file
* Docker images are a _**set of instructions**_ used to create docker containers.
*   Docker image is created using a docker file.

# Docker Basic Commands

## `docker run`

Run a command in a new container

```
docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
```
### example

```ba
docker run -it --name ubuntu_cont ubuntu:latest bash
```



## `docker start`

Start one or more stopped containers in detached mode

```
docker start [OPTIONS] CONTAINER [CONTAINER...]
```

### example

```ba
docker start -i ca765vb
```

## `docker ps`

List of containers

```bas
docker ps [OPTIONS]
```
### example

```bash
docker ps -a
```

## `docker images`

List of images

```bash
docker images [OPTIONS] [REPOSITORY[:TAG]]
```

- Docker image has intermediate layers that increase reusability, decrease disk usage and speed up `docker build` by allowing each step to be cached! these intermediate layers are not shown by default.

### example

```bas
docker images -a
```

## `docker stop`

Stop one or more running container

```bash
docker stop [OPTIONS] CONTAINER [CONTAINER...]
```

### example

```bas
docker stop -t 100 34tfer 
```

## `docker kill`

Kill one or more running containers

```ba
docker kill [OPTIONS] CONTAINER [CONTAINER...]
```

- stop vs. kill?

### example

```ba
docker kill cae40c
```


## `docker exec`

Run a command in a running container

```b
dockr exec [OPTIONS] CONTAINER [ARGS...]
```
- COMMAND should be an executable, a chained or a quoted command will not work. Example:
  -  `docker exec -ti my_container "echo a && echo b"` will not work, but 
  - `docker exec -ti my_container sh -c "echo a && echo b"` will.

### example

```bas
docker exec -it 120 bash
```


# `docker cp`

Copy files/folders between a container and the local filesystem

```bash
docker cp [OPTIONS] CONTAINER:SRC_PATH DEST_PATH|-
docker cp [OPTIONS] SRC_PATH|- CONTAINER:DEST_PATH
```

### example

```ba
docker cp /file_from_host my_cnt:/dir_in_cnt/
```

# `docker rm`

Remove one or more containers

```bash
docker rm [OPTIONS] CONTAINER [CONTAINER...]
```

### example

```bash
docker rm 34fg 6hfg 
```



[For Detail Information][1]

  [1]: https://medium.com/better-programming/https-medium-com-ozantunca-explaining-docker-in-frontend-terms-9d8d2b282ed8
