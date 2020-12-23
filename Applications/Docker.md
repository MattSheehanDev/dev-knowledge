Docker
=========================

CLI
----------------------------------------------

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

