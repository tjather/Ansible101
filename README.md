# Ansible101

## Overview
**Ansible101** is a project that utilizes **Ansible** to automate **configuration management** and **Docker** to containerize the provisioning process. The project automates the setup and maintenance of a **VM host running an Apache web server**, ensuring repeatability and consistency in deployment.

## Features
- **Automated Apache Web Server Deployment**: Installs, configures, and maintains an Apache web server.
- **Containerized Ansible Execution**: Runs Ansible playbooks inside a Docker container using **Docker Compose**.
- **Infrastructure as Code**: Uses Ansible playbooks to manage VM provisioning and service configuration.
- **Repeatable and Scalable**: Ensures consistency in configuration across multiple hosts.

## Prerequisites
- **Docker & Docker Compose** (Install from [Docker's website](https://www.docker.com/get-started))
- **Ansible** (Installed within the Docker container)
- **A Linux-based VM** (e.g., Ubuntu)

## Setup & Deployment
### Step 1: Start the Ansible Container
Run the following command to build and start the Ansible container:
```sh
docker-compose up -d
```

### Step 2: Run the Ansible Playbook
Execute the Ansible playbook to configure the VM and deploy Apache:
```sh
docker exec -it <container_id> ansible-playbook /path/to/playbook.yml
```
Replace `<container_id>` with the actual container ID, which you can retrieve using:
```sh
docker ps
```

### Step 3: Verify Apache Deployment
After running the playbook, open a web browser and navigate to the VM’s IP address. You should see the default **index.html** page served by Apache.

### Step 4: Stopping & Cleaning Up
To stop and remove the Ansible container, run:
```sh
docker-compose down
```

## Customization
Modify `playbook.yml` to:
- Change the **document root**.
- Add additional **software packages**.
- Customize **Apache virtual host settings**.
