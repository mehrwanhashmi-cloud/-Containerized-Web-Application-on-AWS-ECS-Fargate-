# aws-ecs-fargate-container-app
The application is built with Flask, containerized using Docker, stored in Amazon ECR, and deployed using Amazon ECS with AWS Fargate, making it fully serverless and scalable.

## 🌐 Live Demo
load-balancer-109188194.us-east-1.elb.amazonaws.com

## 🧠 Architecture
🔁 Architecture Flow

User → Application Load Balancer → Target Group → ECS (Fargate) → Container → Flask App
                                                      ↑
                                                     ECR
                                                     
<img width="1536" height="1024" alt="ecr" src="https://github.com/user-attachments/assets/ccfa0981-3f34-4a7c-9924-06540908913f" />

## ECR
🏗️ AWS Services Used
Amazon Elastic Container Service – Container orchestration
AWS Fargate – Serverless compute engine
Amazon Elastic Container Registry – Docker image storage
Application Load Balancer – Traffic distribution
AWS Identity and Access Management – Secure access control

## ⚙️ Tech Stack
Python (Flask)
Docker
AWS Cloud Services

## 🚀 Features
Containerized web application using Docker
Serverless deployment using AWS Fargate
Load balanced architecture using ALB
Secure image storage with ECR
Highly available and scalable design
Publicly accessible web application

## 📸 Screenshots
# 🌐 Live Application
<img width="1912" height="949" alt="load balancer dns in browser" src="https://github.com/user-attachments/assets/80ff50b2-cb17-4c8b-916e-7400bdea3f42" />

# 📦 ECR Repository
<img width="1920" height="949" alt="ecr repo" src="https://github.com/user-attachments/assets/6d0241aa-6b97-41b9-8bed-e2c26d56ad85" />

# ⚙️ ECS Service Running
<img width="1920" height="953" alt="cluster-service" src="https://github.com/user-attachments/assets/50a56bba-e2e2-4cdc-b7e9-921eade5eed5" />

# 📋 Task Definition
<img width="1920" height="938" alt="ecs task config" src="https://github.com/user-attachments/assets/55526fa8-11f7-4224-a3e5-97b89affff37" />

# 🌍 Load Balancer
<img width="1920" height="945" alt="load balancer dns" src="https://github.com/user-attachments/assets/a18b8bde-ff5d-4063-90d6-e81e08500790" />

# 🎯 Target Group Health
<img width="1920" height="953" alt="target group health" src="https://github.com/user-attachments/assets/ba57b626-35ea-4b0d-b180-20c0ff8d1241" />

# Docker
<img width="1920" height="1008" alt="docker push" src="https://github.com/user-attachments/assets/a1a3d34f-cf8b-4798-916e-933baf783ae6" />


## 🛠️ Deployment Steps
# 1. Build Docker Image
docker build -t my-app .

# 2. Push Image to ECR
aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin <ECR_URI>
docker tag my-app:latest <ECR_URI>
docker push <ECR_URI>

# 3. Create ECS Cluster (Fargate)
Cluster type: Fargate
Name: my-cluster

# 4. Create Task Definition
Launch type: Fargate
Container image: ECR URI
Port: 80

# 5. Create Service
Desired tasks: 1
Load Balancer: Application Load Balancer
Target group: IP-based

# 6. Access Application
Use ALB DNS URL to access the app

## 🧠 Key Learnings
How to containerize applications using Docker
How to push images to AWS ECR
How to deploy containers using ECS + Fargate
How load balancing works with ALB and target groups
IAM roles and permissions for secure access
Troubleshooting real-world AWS errors

## 🚧 Challenges Faced
IAM permission issues with ECR (AccessDeniedException)
AWS CLI configuration errors
Incorrect Docker tagging before push
Understanding target groups and networking




