# 🚀 NodeDockerApp – Node.js App in a Docker Container Mounted on AWS EC2

## 📝 Overview
- This project demonstrates how to:

- Build a simple Node.js + Express app

- Containerize it using Docker

- Push the Docker image to Docker Hub

- Deploy and run it on an AWS EC2 instance

  ## ⚙️ Technologies Used
  Node.js Docker DockerHub, AWS,

  # Step 1: Launch AWS EC2 Instance
- Go to AWS EC2 Console and login
- Launch a new instance using: Ubuntu 20.04,instant type:t2.micro,keypair,storage:8Gib,
- Open port 22 and 3000 in the security group.




- Connect via SSH:
```
ssh -i "your-key.pem" ec2-user@your-ec2-public-ip
```

  ## Step 2: Install Docker on EC2
  ```
sudo apt update -y
sudo  apt install docker .io
sudo service docker start
dockwe --version
ps aux | grep docker #check if docker is running
sudo usermod -aG docker $USER #Put docker as a group user
sudo reboot # to reboot the system(wait for 10 minutes and the ssh back to the server)
groups #check if docker is a group user
```
## Step 3: Clone the Project on gitHub
```
git clone https://github.com/kingakwa/nodjs-app12
```
-cd to the clone repository 

## Step 4 : Build Docker Image Locally
```
 docker build -t nodjs-app12 . # the . signifies build it in the current directory 
docker images # check the images that has been built
```

## step 5: Tag the Image for Docker Hub
```
docker tag nodjs-app12 kingakwa/nodjs-app12:latest
```
## Step 6: Push to Docker Hub
```
docker login
docker push kingakwa/nodjs-app12:latest
```
## Step 7: Run Docker Container on EC2
```
docker run -d -p 3000:3080 your-dockerhub-username/nodedockerapp:latest  #
```
This maps host port 3000 to container port 3080

## Step 8: Access the App
`http://<your-ec2-public-ip>`

 ## Conclusion
The NodeDockerApp project provides a practical and scalable foundation for deploying a Node.js application using Docker and AWS EC2. By containerizing the app, we ensure consistency across environments, simplify deployments, and enable easy integration with cloud infrastructure. Hosting it on an EC2 instance allows for cost-effective and flexible scalability suitable for both development and production use cases.

This project not only demonstrates the fundamentals of Docker and Node.js but also introduces best practices in modern DevOps workflows. Whether you're a developer looking to containerize your apps or a DevOps engineer deploying scalable services, this project serves as a solid starting point for real-world containerized deployments.
