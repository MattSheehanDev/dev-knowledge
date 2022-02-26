Docker Engine
=========================

Commands
----------------------------------------------

### Images

Build an image with name:tag
```
docker build -t <name:tag> .
```

Build an image with a specific dockerfile
```
docker build -f <path-to-dockerfile> .
```

Tag an image
```
docker tag <image-name> <image-name>[:tag]
```

List images
- hides intermediatary images
```
docker image ls
```

List all images
```
docker image ls -a
```

Run an image (creates a container)
```
docker run <image-name>

# Run an image and give a container name
docker run <image-name> --name <container-name>

# Run an image and remove container when it stops
docker run --rm <image-name>
```

Remove an image
- can't remove an image used currently by a container
```
docker rmi <image-id>
```

Run a container from an image
```
docker run <registry/image>
```
- `-v` : mount a volume to local file system. Ex. `-v /local:/container`
- `-p` : expose port. Ex. `-p 80:80`
- `--name <container-name>` : alias name for the image (very useful imo)
- `--rm` : remove container when it exits (very useful imo)

### Containers

Start a container
```
docker start <container-name>
```

Stop a container
```
docker stop <container-name>
```

List running containers
```
docker container ls

# aliased as
docker ps
```

List all containers
```
docker container ls --all

# alias
docker ps -a
```

Remove a container
- `-f` force removal
```
docker rm <container-name|container-id>

docker rm -f <container-name|container-id>
```

### Registries

Login
```
docker login <registry-url>
```

Push
```
docker push <image-name|image-tag>
```

### System

Remove dangling resources
- dangling resources are resources not associated with a container
- `-a` : remove all unused resources, not just dangling ones
- `--volumes` : remove resources including volumes
```
docker system prune

# Remove all unused resources (not just dangling)
docker system prune -a

# Remove all unused resources, including volumes
docker system prune -a --volumes
```



![[types-of-mounts-volume.png]]

