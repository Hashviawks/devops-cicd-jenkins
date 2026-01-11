**Project Overview**

This project demonstrates an end-to-end CI/CD pipeline that automatically builds and deploys a Dockerized application using Jenkins.
The pipeline pulls source code from GitHub, builds a Docker image, and deploys the application as a running container on an AWS EC2 instance.

**Technologies Used**

- Jenkins – CI/CD automation
- Docker – Containerization
- Git & GitHub – Version control
- AWS EC2 – Deployment server
- Linux (Ubuntu) – Operating system
- Python – Sample application

**Dockerfile**

. Uses an official Python base image
. Copies application files into the container
. Installs dependencies
. Exposes application port
. Starts the application using python app.py

**CI/CD Pipeline Flow**

. Jenkins pulls the latest code from GitHub
. Jenkins builds a Docker image from the Dockerfile
. Existing container (if any) is stopped and removed
. A new container is deployed using the latest image
. Application is accessible via browser

**Jenkinsfile**

. Builds a Docker image without cache to avoid stale builds
. Stops old container, removes it, and deploys a fresh container

**How to Run Locally**
docker build -t my-app .
docker run -d -p 5000:5000 my-app
Access the application at:
http://localhost:5000

**Deployment on AWS EC2**
- Launch an EC2 Ubuntu instance
- Install Docker and Jenkins
- Open port 5000 in the EC2 security group
- Run Jenkins pipeline
- Access the app using:
  http://<EC2-PUBLIC-IP>:5000

**My Key Learnings**
. Understanding CI/CD pipelines
. Docker image build and container lifecycle
. Jenkins pipeline scripting
. Debugging real-world CI/CD issues
. Deploying applications on AWS EC2
