# Docker Cheat Sheet or some usefull Snippets

## sample docker-compose.yml
```
version: '3'

networks:
   test:

services:
   site:
      image: ubuntu:18.04
      tty: true
      container_name: test
      networks:
      - test
```

## ssh to a running container
```
docker exec -it container_name bash
```

## copy file from container to host machine
```
docker cp container_name:/root/test.txt .
```

## build a Dockerfile to an image with tag
```
docker build -t test_image:tag .

or with custom_name.Dockerfile
docker build -t test_image:tag -f custom_name.Dockerfile .

or with argument
docker build --build-arg var_name=value -t test_image:tag -f custom_name.Dockerfile .
```

## list image
```
docker images
```

## remove image
```
docker image rm image_id
```

## list all container status
```
docker ps -a
```

## start, restart, stop and remove container
```
docker start container_id
docker restart container_id
docker stop container_id
docker container rm container_id
```

## clone image
```
docker tag image_id image_name:tag
```

## save container to an image with tag
```
docker commit container_id image_name:tag
```

## save image with no tag to an image with tag
```
docker tag image_id image_name:tag
```

## save docker image to a file
```
docker save image_name:tag > backup_image_name.tar
gzip -k backup_image_name.tar
```

## load backup image/file to docker machine
```
gzip -dk backup_image_name.tar.gz
docker load --input backup_image_name.tar
```

### docker volume backup
```
./docker-volume-backup volume-name /path/backup

```

### docker volume restore
```
./docker-volume-restore volume-name /path/backup/backup-file.tar.gz

```

### docker volume clone
```
./docker-volume-clone source-volume destination-volume

```

### docker volume info
```
list all available volume with size
./docker-volume-info
```

