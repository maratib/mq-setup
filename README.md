# MQ Setup in Docker Container 
```bash
# To Pull the image
docker pull ibmcom/mq:latest

# List docker images
docker images

# Docker create volume
docker volume create qmldata

# List Docker volumes 
docker volume ls

# Docker run (image)
docker run 
    --env LICENSE=accept \
    --env MQ_QMGR_NAME=QM1 \
    --volume qmldata:/mnt/mqm \
    --publish 1414:1414 \
    --publish 9443:9443 \
    --env MQ_APP_PASSWORD=Sam12345 ibmcom/mq:latest \
    --detach

# --detach : means runs in the background    

# List Docker running containers
docker ps

dspmqver # to see the version
dspmq # to see the mq name and status

# Visit MQ control panel at
https://localhost:9443

user/pass: admin/passw0rd

```