# Jenkins Pipeline for AWS ECS Fargate Deployment

This `Jenkinsfile` automates the CI/CD process for building, pushing, and deploying a Dockerized application to AWS ECS Fargate using Terraform and AWS ECR.

## Pipeline Overview

The pipeline performs the following steps:

1. **Clean Workspace**: Cleans the Jenkins workspace before starting the build.
2. **Git Checkout**: Clones the source code from the specified GitHub repository.
3. **Authenticate with AWS and ECR**: Uses Jenkins credentials to authenticate with AWS and log in to Amazon ECR.
4. **Build, Tag & Push Docker Image**: Builds the Docker image from the `applicationcode` directory, tags it, and pushes it to AWS ECR.
5. **Provision ECS**: Checks if the ECS infrastructure is provisioned using Terraform. If not, it provisions the infrastructure.
6. **Deploy to ECS**: Deploys the latest Docker image to the ECS service using Terraform.

## Prerequisites

- Jenkins server with Docker, AWS CLI, and Terraform installed.
- Jenkins credentials for AWS (`aws-credentials-id`) and GitHub (`github-cred`).
- AWS ECR repository created and accessible.
- Terraform scripts for ECS infrastructure in the `terraform` directory.
- Application source code in the `applicationcode` directory.

## Environment Variables

- `AWS_DEFAULT_REGION`: AWS region (e.g., `us-east-1`)
- `AWS_ACCOUNT_ID`: Your AWS account ID
- `IMAGE_TAG`: Docker image tag, based on Jenkins build number
- `ECR_URI`: AWS ECR repository URI
- `TF_DIR`: Directory containing Terraform scripts (default: `terraform`)

## How It Works

- The pipeline builds and pushes a Docker image to ECR.
- It checks for ECS infrastructure changes and applies them if needed.
- It always deploys the latest Docker image to ECS by updating the `container_image` variable in Terraform.

## Usage

1. Place the `Jenkinsfile` in your repository root.
2. Configure Jenkins with the required credentials and tools.
3. Trigger the pipeline manually or via webhook.

## Example Jenkinsfile Stages

- Clean Workspace
- Git Checkout
- Authenticate with AWS and ECR
- Build, Tag & Push Docker Image
- Provision ECS (Terraform)
- Deploy to ECS (Terraform)

---

Feel free to customize the pipeline for your specific requirements.
