# AWS-DevOps-Project-Advanced-Automated-CI-CD-Pipeline
This project demonstrates how to set up an advanced automated CI/CD pipeline with Infrastructure as Code (IaC), microservices, a service mesh, and monitoring using AWS. Tools like Terraform, Jenkins, Kubernetes (EKS), Istio, Prometheus, Grafana, and ArgoCD are utilized.
![DALL·E 2024-12-31 22 32 34 - A professional architectural diagram of a modern cloud-native application setup, visually designed to look like it was created by a human  The image i](https://github.com/user-attachments/assets/e066fdc5-ef2c-4e70-a1f7-353872007ff1)

## Architecture Overview
Infrastructure as Code: AWS resources are provisioned using Terraform.
Containerized Microservices: Deployed on EKS.
Service Mesh: Managed by Istio for advanced traffic control and observability.
CI/CD Pipeline: Managed with Jenkins and ArgoCD.
Monitoring: Implemented using Prometheus and Grafana.

### Pre-requisites
AWS Account.
Terraform installed locally.
Kubectl and Helm installed.
Jenkins installed and configured.
Docker installed.
Prometheus and Grafana configured for monitoring.

### Step 1: Provision Infrastructure with Terraform
Terraform Configuration (main.tf)

### Step 2: Deploy Jenkins for CI/CD
Helm Chart for Jenkins
helm repo add jenkinsci https://charts.jenkins.io
helm repo update
helm install jenkins jenkinsci/jenkins
Access Jenkins UI and install required plugins (e.g., Docker, Kubernetes, Git, Pipeline).

### Step 3: Deploy Kubernetes Cluster and Microservices

kubectl apply -f microservice-deployment.yaml

### Step 4: Configure Istio Service Mesh
Install Istio
istioctl install --set profile=demo -y
kubectl label namespace default istio-injection=enabled

kubectl apply -f virtualservice.yaml

