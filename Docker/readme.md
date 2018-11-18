# Docker

https://docs.docker.com/engine/reference/commandline/docker/

```
docker --version            # Get the installed version of Docker
```

```
docker run hello-world      # Test docker is working correctly
```

```
docker pull <image>         # Download a prebuilt image from Docker
```

```
docker search <image>       # Search for a prebuilt image from Docker
```

```
docker ps                   #  List running containers
```

```
docker ps -a                # List all containers (running and stoppped)
```

```
docker image ls             # List images
```

```
docker rmi <image>          # Remove Docker image
```

```
docker rm $(docker ps -a -q)    # Remove all containers
```

```
docker kill <container ID>  # Kill a running container
```

```
docker kill $(docker ps -q)     # Kill all containers
```

```
docker exec -it <container ID> /bin/bash    # Starts a bash session inside the container