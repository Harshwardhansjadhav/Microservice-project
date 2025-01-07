# Building a Scalable and Resilient Microservices Architecture with AWS EKS, GitOps, ArgoCD, and Istio
## **Implemented a Kubernetes Cluster on AWS EKS with GitOps and Istio for Modern Microservices**

I designed and deployed a Kubernetes cluster using AWS Elastic Kubernetes Service (EKS), adhering to GitOps principles with ArgoCD to achieve automated and seamless continuous deployment workflows. To optimize traffic management, observability, and security, I integrated Istio as a service mesh.

This project highlights a robust microservices-based architecture powering a dynamic website, composed of multiple services developed in Python, Ruby, Java, and Node.js. The stack demonstrates scalability, fault tolerance, and streamlined deployments, aligning with modern DevOps practices.

## **1. Prerequisites**

First, these are the following tools were installed and configured:  
- **Git:** Used for version control to manage application code and Kubernetes manifests.
- **GitHub:** Hosted repositories for application source code and GitOps configuration files.
- **ArgoCD CLI:** Managed GitOps workflows for automated synchronization and deployment of Kubernetes resources.
- **eksctl:** Simplified creation and management of the EKS cluster and associated resources.
- **AWS CLI:** Configured and managed AWS services, including authentication and EKS cluster access.
- **kubectl:** Interacted with Kubernetes clusters for resource management and troubleshooting.
- **Istio CLI (istioctl):** Deployed and managed the Istio service mesh for traffic control and observability.

## **2. EKS Cluster Creation**

### The Kubernetes cluster was provisioned on AWS using eksctl. After deployment, I validated the cluster's status to confirm that all nodes were active and ready to handle workloads.
