# 🚀 NodeDockerApp – Node.js App in a Docker Container Mounted on AWS EC2

## 📝 Overview
- This project demonstrates how to:

- Build a simple Node.js + Express app

- Containerize it using Docker

- Push the Docker image to Docker Hub

- Deploy and run it on an AWS EC2 instance

  # ⚙️ Technologies Used
  Node.js Docker DockerHub, AWS,

  # Step 1: Launch AWS EC2 Instance
- Go to AWS EC2 Console and login
- Launch a new instance using: Ubuntu 20.04,instant type:t2.micro,keypair,storage:8Gib,
- Open port 22 and 3000 in the security group.
- Connect via SSH:
```
ssh -i "your-key.pem" ec2-user@your-ec2-public-ip
```

  # Step 2: Install Docker on EC2
  ```
sudo apt update -y
sudo  apt install docker .oi
sudo service docker start
ps aux | grep docker #check if docker is running
sudo usermod -aG docker $USER #Put docker as a group user
groups #check if docker is a group user
```
# Step 2: Clone the Project on gitHub
```
git clone 

