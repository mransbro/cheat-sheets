# Docker

https://docs.docker.com/engine/reference/commandline/docker/


## Images

```bash
docker pull <image>         # Download a prebuilt image from Docker
```

```bash
docker search <image>       # Search for a prebuilt image from Docker
```

```bash
docker image ls             # List images
```

```bash
docker rmi <image>          # Remove Docker image
```


## Containers

```bash
docker run -t -i centos /bin/bash   # Starts a container and runs bash in the shell
```

```bash
docker --version            # Get the installed version of Docker
```

```bash
docker run hello-world      # Test docker is working correctly
```

```bash
docker ps                   #  List running containers
```

```bash
docker ps -a                # List all containers (running and stoppped)
```

```bash
docker rm $(docker ps -a -q)    # Remove all containers
```

```bash
docker kill <container ID>  # Kill a running container
```

```bash
docker kill $(docker ps -q)     # Kill all containers
```

## Shell access

```bash
docker container exec -it <container> /bin/bash    # Starts a bash session inside the container
```

```bash
docker container run -it centos bash         # Create a Centos container and load bash in the terminal
```

```bash
docker container start -ai <container>      # Start a stopped container and load the shell in the terminal
```

## Process Monitoring

```bash
docker container top <container>         # Display the running processes inside the container
```

```bash
docker container inspect <container>    # Displays details information on the container
```

```bash
docker container stats                  # Displays a live stream of container resource usage stats
```

# Networks

```bash
docker network ls                       # List all networks
```

```bash
docker network create <network>         # Creates a docker network
```

