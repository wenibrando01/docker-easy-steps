docker-easy-steps

    curl -fsSL https://get.docker.com | sudo sh

    bashsudo systemctl enable docker

    sudo systemctl start docker

Makes Docker auto-start on boot and starts it immediately.


Step 2 — Check if Docker is Running

    bashsudo systemctl status docker

Should show active (running) 


Step 3 — Verify Docker Version

    docker --version
Output example:
Docker version 24.0.2, build cb74dfc

Step 4 — Add User to Docker Group (No sudo needed)
    
    bashsudo usermod -aG docker $USER
    newgrp docker

After this you can run Docker without typing sudo every time.


Step 5 — Test Docker Works

    docker run hello-world


 Installation & Setup/ Docker terminal commnands
 
    bashsudo apt update
    
    sudo apt install docker-ce docker-ce-cli containerd.io
    sudo systemctl enable docker
    sudo systemctl start docker
    sudo systemctl status docker

 Start / Stop / Restart
        
    bashsudo systemctl start docker       # Start Docker
    sudo systemctl stop docker        # Stop Docker
    sudo systemctl restart docker     # Restart Docker
    sudo systemctl enable docker      # Enable on boot
    sudo systemctl disable docker     # Disable on boot

 Docker Version & Info
   
    bashdocker --version                  # Docker version
    docker version                    # Full version info
    docker info                       # System-wide info

 Images

    bashdocker images                     # List all images
    docker pull ubuntu                # Download an image
    docker push myimage               # Push image to registry
    docker rmi ubuntu                 # Remove an image
    docker rmi $(docker images -q)    # Remove all images
    docker build -t myapp .           # Build image from Dockerfile
    docker tag myapp myapp:v1         # Tag an image

 Containers

    bashdocker ps                         # List running containers
    docker ps -a                      # List all containers
    docker run ubuntu                 # Run a container
    docker run -d ubuntu              # Run in background
    docker run -p 8080:80 nginx       # Map ports
    docker run --name mycontainer ubuntu  # Name a container
    docker start mycontainer          # Start a container
    docker stop mycontainer           # Stop a container
    docker restart mycontainer        # Restart a container
    docker rm mycontainer             # Remove a container
    docker rm $(docker ps -aq)        # Remove all containers

 Inspect & Logs

    bashdocker logs mycontainer           # View logs
    docker logs -f mycontainer        # Follow live logs
    docker inspect mycontainer        # Detailed info
    docker stats                      # Live resource usage
    docker top mycontainer            # Running processes

 Execute Commands Inside Container

    bashdocker exec -it mycontainer bash        # Open bash shell
    docker exec -it mycontainer sh          # Open sh shell
    docker exec mycontainer ls /app         # Run a command

 Networks

    bashdocker network ls                        # List networks
    docker network create mynetwork          # Create network
    docker network inspect mynetwork         # Inspect network
    docker network rm mynetwork              # Remove network
    docker network connect mynetwork mycontainer    # Connect container
    docker network disconnect mynetwork mycontainer # Disconnect

 Volumes

    bashdocker volume ls                         # List volumes
    docker volume create myvolume            # Create volume
    docker volume inspect myvolume           # Inspect volume
    docker volume rm myvolume                # Remove volume
    docker volume prune                      # Remove unused volumes

 Docker Compose

    bashdocker compose up                        # Start services
    docker compose up -d                     # Start in background
    docker compose down                      # Stop services
    docker compose ps                        # List services
    docker compose logs                      # View logs
    docker compose build                     # Build images
    docker compose restart                   # Restart services
    docker compose pull                      # Pull latest images

 Cleanup

    bashdocker system prune                      # Remove unused data
    docker system prune -a                   # Remove all unused
    docker container prune                   # Remove stopped containers
    docker image prune                       # Remove unused images
    docker volume prune                      # Remove unused volumes

 Docker Hub Login

    bashdocker login                             # Login to Docker Hub
    docker logout                            # Logout
    docker search ubuntu                     # Search images
