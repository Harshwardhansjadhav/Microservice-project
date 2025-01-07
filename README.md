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
![Capture](https://github.com/user-attachments/assets/f8975349-90cc-4872-bc17-b74f24090dc3)       

## **3. Installing and Configuring ArgoCD**
- Created a separate namespace for ArgoCD within the Kubernetes cluster.
- Deployed ArgoCD using kubectl and switched the context to the ArgoCD namespace.
- Forwarded the ArgoCD server port to enable local access to the UI.
- Logged into the ArgoCD dashboard for authentication and management purposes.

![aa](https://github.com/user-attachments/assets/6417c176-20c8-4656-bc06-c343dfe8c5e4)

![1736190623135](https://github.com/user-attachments/assets/5dd7e92b-d118-4fa7-b6df-e8e939326c10)

![Capture](https://github.com/user-attachments/assets/485e0ab8-e409-4be9-b258-2b26124d9f71)

![1736190623135](https://github.com/user-attachments/assets/ee16340d-fe27-43b3-99b9-14478386f6f0)

![1736190970610](https://github.com/user-attachments/assets/f9ef7112-7ec7-4857-b6e7-9225e6e27f99)

![1736190999080](https://github.com/user-attachments/assets/2d6429c1-87ff-46ac-bec9-3671890e4b22)

![1736190999080](https://github.com/user-attachments/assets/2d6429c1-87ff-46ac-bec9-3671890e4b22)


## **4. Setting up GitHub Repository**
- Create GitHub Repository: Create a new repository on GitHub, ensuring to set the desired name and visibility (public/private).
- Push App Files Using Git Bash: Initialize a local Git repository, add the GitHub repository as a remote, commit your changes, and push the app files to the GitHub repository.

![1736191516616](https://github.com/user-attachments/assets/cc1fea7d-bd38-4b68-b2c5-003219ebfbca)

## **5. Deploying the Application**

- Checked the status of the deployed pods using kubectl commands.
- Used kubectl port-forward to forward the product page service port for easy local access, making the application available at http://127.0.0.1/productpage.
- Integrated ArgoCD to enable automatic redeployment, ensuring seamless updates every time changes are pushed to the GitHub repository.
  
![Capture1](https://github.com/user-attachments/assets/2e5d93dc-9e3c-4575-a7ba-be9b7cb1cce6)
![Capture2](https://github.com/user-attachments/assets/d6a46d5a-982f-4123-a567-e5b522c671d2)
![Capture3](https://github.com/user-attachments/assets/7388ffa6-ecc7-4bc0-9234-0ce0f2216a21)
![1736192097226 (1)](https://github.com/user-attachments/assets/4bd4abeb-7786-4e21-b43e-07f22e2d9a21)
![1736192131139](https://github.com/user-attachments/assets/a554c2f5-0968-4623-887b-ed9660e41449)

## **6. Installing and Configuring Istio**

- Installed Istio using the demo profile with istioctl for a quick and easy setup.
- Enabled Istio sidecar injection for the necessary namespaces and configured traffic flow management through the Bookinfo gateway.
- Exposed the application to the outside world by setting up an AWS load balancer for external access.

![1git](https://github.com/user-attachments/assets/acb7deaf-7c03-40d0-b095-16bb9fbc9773)
![8istioctl](https://github.com/user-attachments/assets/30d6b970-e80d-4365-8e67-3f0eafacff95)

- Namespace creation.

![2git](https://github.com/user-attachments/assets/f14536bb-a9b8-426a-aa77-aa0ba27f1191)
![12istio](https://github.com/user-attachments/assets/e26a7225-30cf-4605-b49b-fb6b178767c8)






