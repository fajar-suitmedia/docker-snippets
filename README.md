# Docker Cheat Sheet or some usefull Snippets

## save container to an image with tag
docker commit container_id image_name:tag

## save image with no tag to an image with tag
docker tag image_id image_name:tag

## save docker image to a file
docker save image_name:tag > backup_image_name.tar
gzip -k backup_image_name.tar

## load backup image/file to docker machine
gzip -dk backup_image_name.tar.gz
docker load --input backup_image_name.tar

## list image
docker images

## remove image
docker image rm image_id

## clone image
docker tag image_id image_name:tag

## list all container status
docker ps -a

## start, restart, stop and remove container
docker start container_id
docker restart container_id
docker stop container_id
docker container rm container_id
