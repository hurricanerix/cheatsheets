# Docker

Docker is an open platform for developing, shipping, and running applications. Docker enables you to separate your applications from your infrastructure so you can deliver software quickly. With Docker, you can manage your infrastructure in the same ways you manage your applications. By taking advantage of Docker's methodologies for shipping, testing, and deploying code, you can significantly reduce the delay between writing code and running it in production.

## INSTALLATION

### Docker Desktop is available for Mac, Linux and Windows

https://docs.docker.com/desktop

### View example projects that use Docker

https://github.com/docker/awesome-compose

### Check out our docs for information on using Docker

https://docs.docker.com


## IMAGES

Docker images are a lightweight, standalone, executable package
of software that includes everything needed to run an application:
code, runtime, system tools, system libraries and settings.

### Build an Image from a Dockerfile

```Shell
$ docker build -t <image_name>
```

### Build an Image from a Dockerfile without the cache

```Shell
$ docker build -t <image_name> . –no-cache
```

### List local images

```Shell
$ docker images
```

### Delete an Image

```Shell
$ docker rmi <image_name>
```

### Remove all unused images

```Shell
$ docker image prune
```


## DOCKER HUB

Docker Hub is a service provided by Docker for finding and sharing
container images with your team. Learn more and find images
at https://hub.docker.com

### Login into Docker

```Shell
$ docker login -u <username>
```

### Publish an image to Docker Hub

```Shell
$ docker push <username>/<image_name>
```

### Search Hub for an image

```Shell
$ docker search <image_name>
```

### Pull an image from a Docker Hub

```Shell
$ docker pull <image_name>
```


## GENERAL COMMANDS

### Start the docker daemon

```Shell
$ docker -d
```

### Get help with Docker. Can also use –help on all subcommands

```Shell
$ docker --help
```

### Display system-wide information

```Shell
$ docker info
```


## CONTAINERS

A container is a runtime instance of a docker image. A container
will always run the same, regardless of the infrastructure.
Containers isolate software from its environment and ensure
that it works uniformly despite differences for instance between
development and staging.

### Create and run a container from an image, with a custom name:

```Shell
$ docker run --name <container_name> <image_name>
```

### Run a container with and publish a container’s port(s) to the host.

```Shell
$ docker run -p <host_port>:<container_port> <image_name>
```

### Run a container in the background

```Shell
$ docker run -d <image_name>
```

### Start or stop an existing container:

```Shell
$ docker start|stop <container_name> (or <container-id>)
```

### Remove a stopped container:

```Shell
$ docker rm <container_name>
```

### Open a shell inside a running container:

```Shell
$ docker exec -it <container_name> sh
```

### Fetch and follow the logs of a container:

```Shell
$ docker logs -f <container_name>
```

### To inspect a running container:

```Shell
$ docker inspect <container_name> (or <container_id>)
```

### To list currently running containers:

```Shell
$ docker ps
```

### List all docker containers (running and stopped):

```Shell
$ docker ps --all
```

### View resource usage stats

```Shell
$ docker container stats
```

## Original Source

https://docs.docker.com/get-started/docker_cheatsheet.pdf
