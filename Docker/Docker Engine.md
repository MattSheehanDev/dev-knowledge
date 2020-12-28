Docker Engine
=========================

Commands
----------------------------------------------

Run a container from an image
```
docker run <registry/image>
```
- `-v` : mount a volume to local file system. Ex. `-v /local:/container`
- `-p` : expose port. Ex. `-p 80:80`

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

LIst all containers
```
docker ps -a
```

Remove a container
- `-f` force removal
```
docker rm -f <container-name>
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

![[types-of-mounts-volume.png]]

