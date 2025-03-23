**Basic Commands:**

docker --version: Check Docker's version.

docker help: Get help on Docker usage.

docker info: Display system-wide information.

**Container Management:**

docker ps: List running containers.

docker ps -a: List all containers (running and stopped).

docker start [container_name/id]: Start a stopped container.

docker stop [container_name/id]: Stop a running container.

docker restart [container_name/id]: Restart a container.

docker rm [container_name/id]: Remove a container.

**Image Management:**

docker images: List all images.

docker pull [image_name]: Pull an image from a registry (e.g., Docker Hub).

docker rmi [image_name]: Remove an image.

docker build -t [image_name] .: Build an image from a Dockerfile.

**Running Containers:**

docker run [image_name]: Run a container from an image.

docker run -it [image_name]: Run a container interactively.

docker run -d [image_name]: Run a container in detached mode.

**Volume Management:**

docker volume create [volume_name]: Create a volume.

docker volume ls: List all volumes.

docker volume rm [volume_name]: Remove a volume.

**Network Management:**

docker network create [network_name]: Create a network.

docker network ls: List all networks.

docker network rm [network_name]: Remove a network.

**Exec Commands:**

docker exec -it [container_name/id] [command]: Run a command inside a running container.

**Logs and Stats:**

docker logs [container_name/id]: View logs of a container.

docker stats: Display real-time resource usage statistics.
