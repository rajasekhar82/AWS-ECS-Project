
<img width="1280" height="720" alt="ECS-Diwali-Project-Thumbnail" src="https://github.com/user-attachments/assets/259084cf-4a01-484b-a642-914568ae1b5a" />


# 🪔 Static Diwali Wishes Website Deployment on AWS ECS

This project is a festive DevOps exercise 🎉 — I built a **static Diwali wishes website** and deployed it on **AWS ECS** using a complete CI/CD pipeline with Jenkins and Terraform.

---

## 📌 Project Overview
The goal was to:
- Build a static HTML5, CSS3, JavaScript, Three.js **Diwali wishes website**
- Deploy it on **AWS ECS** in a secure and automated way
- Use **Infrastructure as Code** for provisioning AWS resources

---

## 🛠 Tech Stack

- **AWS Services:** EC2, ECS, ECR, VPC, Subnets, ALB, Route 53, Certificate Manager
- **Tools & Technologies:** Jenkins, Docker, Trivy, Terraform, GitHub
- **Programming/Markup:** HTML5, CSS3, JavaScript, Three.js

---

## ⚙️ Architecture

1. **EC2 Setup**  
   - Ubuntu EC2 instance  
   - Install **Jenkins**, **Docker**, **Trivy**, **Terraform**

2. **CI/CD Pipeline**  
   - Jenkins pipeline pulls source code from **GitHub**
   - Authenticates with **AWS** and Build Docker image and pushes to **AWS ECR**

3. **Infrastructure Provisioning** (Terraform)  
   - VPC  
   - Public Subnets  
   - Internet Gateway & Route Tables  
   - Application Load Balancer & Target Groups  
   - ECS Cluster

4. **Deployment**  
   - Jenkins deploys the **latest docker image** to AWS ECS

5. **Domain & Security**  
   - ALB DNS mapped to **Route 53**
   - HTTPS enabled using **Amazon Certificate Manager**

---


https://github.com/user-attachments/assets/95dfb597-df3e-405f-a3a7-4e3f0399de12

