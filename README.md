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
