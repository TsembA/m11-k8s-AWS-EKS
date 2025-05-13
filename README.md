# Kubernetes on AWS: EKS

## 🐳 ECS (Elastic Container Service)

Amazon ECS, short for Elastic Container Service, is a fully managed service designed to run and orchestrate containerized applications. It lets you deploy and scale containers across a fleet of EC2 instances. You can think of it as a simplified container orchestrator where AWS handles the scheduling and lifecycle of containers, similar in some ways to Docker Swarm but running on AWS-managed infrastructure.

## 🔄 ECS vs. Fargate

**Fargate** is a serverless compute engine for containers that works with ECS (and also EKS). Unlike ECS with EC2, Fargate allows you to run containers without provisioning or managing the underlying virtual machines. It automatically scales the compute capacity needed to run your containers, and removes the need for patching or maintaining EC2 instances. It’s ideal if you want to focus only on containers and leave infrastructure management to AWS.

## ☸️ EKS (Elastic Kubernetes Service)

Amazon EKS is a managed Kubernetes service that helps you run Kubernetes clusters on AWS. It’s a solid choice if you're already invested in Kubernetes or want to avoid being locked into a single cloud provider. Since Kubernetes is open-source, using EKS gives you the freedom to migrate workloads across clouds using tools like Terraform. Compared to tools like Docker Swarm, EKS provides greater flexibility, ecosystem support, and production-grade features.

## ⚙️ How to Set Up an EKS Cluster

1. **Create the EKS control plane** – this initializes the cluster on AWS.
2. **Define a Node Group** – usually a set of EC2 instances that will run your workloads.
3. **Link Node Group to the Cluster** – so Kubernetes can schedule pods onto your nodes.

## 🗃️ ECR (Elastic Container Registry)

Amazon ECR is AWS’s managed Docker image registry. It integrates easily with ECS, EKS, and other AWS services. While it’s optimized for AWS, some developers prefer GitHub Container Registry for its broader integration and flexibility. However, using GitHub with AWS often requires extra configuration when setting up CI/CD pipelines.

## 🚀 Fargate Recap

Fargate provides a compute layer for containers without the need to provision or manage servers. It's a usage-based service, so you only pay for the resources consumed while your containers are running. This makes it an attractive option for small, flexible workloads or teams who prefer not to handle infrastructure operations manually.
