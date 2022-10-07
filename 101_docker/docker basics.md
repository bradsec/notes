## docker basics

Topics: [[docker]]  

---
## Pull Image
`docker pull <image-name>:<image-version>`

## Show Images
`docker images`

## Show Running Containers
`docker ps`

## Show All Containers
`docker ps -a`

## Stopping Containers
`docker stop <container-name> or <container-id>`

## Dockerfile Example (poor caching)

Filename: `Dockerfile`

```
FROM golang:1.18.1-bullseye

# Working direction
WORKDIR /app

# Copy path - second . relevative to working direction
COPY . .

# Commands to be run at time image is built
RUN go mod tidy
RUN go build -o webapp

# Port exposed on container
EXPOSE 8282

# Command run when container starts
CMD ["./webapp"]

```

## Dockerfile Example (improved caching)

Filename: `Dockerfile`

```
FROM golang:1.18.1-bullseye

# Working direction
WORKDIR /app

# Copy go.mod
COPY go.mod .
COPY go.sum .

# Grab required mods
RUN go mod tidy

# Copy path - second . relevative to working direction
COPY . .

# Commands to be run at time image is built
RUN go build -o webapp

# Port/s exposed from container
EXPOSE 8282

# Command run when container starts
CMD ["./webapp"]

```

## Build image
`docker build -t myapp .`

## Build image with version number
`docker build -y myapp:v1 .`

## Run container examples - 'run' creates a new container
```
docker run --name myapp_test myapp
# myapp_test is name of container
# myapp is image used
# No listening port access specified

docker run --name myapp_test -p 4000:8282 myapp
# Port on right is port exposed by the container ie. 8282
# Port on left is port mapped from localhost

# To use detached mode - not blocking terminal user flag -d

# Running an specific image version
docker run --name myapp_test -p 4000:8282 myapp:v1

# Remove container when stopped
# Append flag: --rm before image name
docker run --name myapp_test -p 4000:8282 --rm myapp:v1

# Using Volumes (map directories between containers and host computer)
docker run --name myapp_test -p 4000:8282 --rm -v <local-path>:/app myapp:v1

# Add persistent volume path managed by docker
docker run --name myapp_test -p 4000:8282 --rm -v <local-path>:/app -v /app/leavemefolder myapp:v1

```

## Start existing container - 'start' uses an existing container
```
docker start <container-name>
```

## Deleting Containers
```
# Remove single
docker container rm myapp_container01

# Remove multiple 
docker container rm myapp_container01 myapp_container02
```

## Deleting Images
```
# If image not in use by containers
docker image rm myapp

# Force remove even if in use by containers
docker image rm myapp -f
```

## Remove all images, containers and volumes
```
docker system prune
```

## Docker Compose
```
# Place in root directory
Filename: `docker-compose.yaml`

```

## Running `docker-compose.yaml`
```
# Whilst in directory containing docker-compose.yaml
docker-compose up

# To stop and remove containers
docker-compose down

# To stop remove containers and all images
docker-compose down --rml all

# To stop remove containers, all images and volumes
docker-compose down --rml all -v
```
