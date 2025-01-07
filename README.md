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


- Istio pods.

![15istio](https://github.com/user-attachments/assets/7e1b1de8-a024-4ccb-b8b4-440b7bbd6160)
![10istioctl](https://github.com/user-attachments/assets/e783c33d-55ed-480a-8c98-821717cc0ea3)


- Gateway between Istio and Default Namespace.

![3git](https://github.com/user-attachments/assets/06031391-53de-40c1-ad20-ecf7c2f1e7d9)
![11istio](https://github.com/user-attachments/assets/05fe786a-248f-44bf-aa3e-f8777db64ac7)


- Default pods restarted.

![14istio](https://github.com/user-attachments/assets/b82a5554-8ad1-4b43-9e9c-4d8287e09dea)


- Product page (bookinfo).

![6](https://github.com/user-attachments/assets/bfc24872-c0f6-4fdd-aec5-847bdfb06d11)



## **7. Traffic Monitoring, Management and Logs**

- Deployed Istio add-ons such as Prometheus, Grafana, and Kiali to enable robust and comprehensive monitoring of traffic and application performance.
- Going in my "Environment variable PATH" in my istio file/samples/addons.

![4git](https://github.com/user-attachments/assets/4ad440bb-0833-4579-b5f9-978b9d7145d0)
![17](https://github.com/user-attachments/assets/3db9ce4c-9a59-42bf-9867-117d624c525f)


- Checked the status of the add-on components by running kubectl get pods -n istio-system to ensure they were running correctly.

![5git](https://github.com/user-attachments/assets/d057ca0b-1f44-4bb4-9008-7cdf0b6038ba)
![18](https://github.com/user-attachments/assets/7c3a6147-d281-4cf5-a4ce-7c1fe277ceff)


- Assessed the Kiali dashboard to visualize and get information about service mesh and traffic flow.

![6git](https://github.com/user-attachments/assets/3de56af0-2820-4ba4-a3f1-a9675e6baa12)
![21](https://github.com/user-attachments/assets/7d436052-3052-4a9a-a9f1-ff6e84006ce5)
![19](https://github.com/user-attachments/assets/b197242c-f9c4-4154-af51-b018285b90f1)
![20](https://github.com/user-attachments/assets/54f60518-0fd9-417b-ba10-6e22a36e56e1)

- Enabled Prometheus for collecting performance metrics and Grafana for visualizing the data, offering valuable insights into system performance, including response times and error rates.

![7git](https://github.com/user-attachments/assets/87f3c85b-8640-4f2c-8266-2c9e762460dc)
![Screenshot 2025-01-06 175738](https://github.com/user-attachments/assets/21916740-7dd2-46c9-96b1-3deaf9f84d7a)

- Grafana Dashboard.

![8git](https://github.com/user-attachments/assets/38cef476-d8c2-4cdd-a20d-2fcc0598c4d8)

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


## **DevOps-Driven Microservices Architecture with GitOps, Istio, and Advanced Monitoring Tools**

In today's rapidly evolving software landscape, ensuring efficient deployment, management, and monitoring of microservices is essential. In this post, I’ll walk you through how we built a robust, scalable microservices architecture using modern DevOps practices, leveraging AWS EKS, ArgoCD, Istio, and advanced monitoring tools.

## **8. Key Technologies in the Workflow:**

- **AWS & eksctl:** We used AWS and eksctl to provision and manage our EKS clusters, providing a reliable infrastructure for containerized applications.
- **Kubernetes & kubectl:** Kubernetes handles orchestration, while kubectl is used for managing the cluster and deploying our applications.
- **GitHub & ArgoCD:** GitHub serves as our version control system, and ArgoCD ensures continuous deployment by syncing the Kubernetes cluster state with the GitHub repository using GitOps.
- **Istio:** We implemented Istio to manage traffic routing, enforce security policies, and monitor service interactions within the Kubernetes cluster.
- **Monitoring Tools (Prometheus, Grafana, Kiali):** These tools provide real-time monitoring, traffic visualization, and detailed insights into the health of the microservices.

## **9. The Architecture:**
The application follows a microservices architecture, with each service performing a distinct function:

- **Productpage (Python):** Displays the product details to users.
- **Details (Ruby):** Fetches detailed information about the products.
- **Reviews (Java):** Provides product reviews, with multiple versions available for canary deployments.
- **Ratings (Node.js):** Retrieves product ratings from the database.



Architecture:

![pixelcut-export](https://github.com/user-attachments/assets/e67ec0b2-66e4-41ac-a045-860759b6ec3c)

## **10.  Communication Flow:**

- External traffic is routed through the Istio Gateway, ensuring secure and efficient ingress.
- Internal communication between services is managed through Kubernetes private load balancers, with Istio ensuring seamless service-to-service interactions.

Traffic Flow:

![pixelcut-export (1)](https://github.com/user-attachments/assets/d995d036-205b-4dd7-9304-7a354db09287)

## **11. Key Features:**

- **GitOps:** With ArgoCD, continuous deployment ensures that the state of the Kubernetes cluster always mirrors the GitHub repository, promoting seamless updates.
- **Service Mesh:** Istio enables intelligent traffic management, robust security, and monitoring across microservices, ensuring optimal communication.
- **Real-time Monitoring:** Prometheus collects performance metrics, while Grafana visualizes them for actionable insights. Kiali offers detailed views of the service mesh traffic and interactions, and Jaeger helps with tracing.
- **Scalable Microservices:** Each service is independently scalable and deployable, ensuring flexibility and resilience as the application grows.

## **12. Future Enhancements:**
- **CI Pipeline:** We aim to automate the build and testing processes, ensuring that only the most reliable code gets deployed.
- **Enhanced Code Quality:** Integrating SonarQube checks into the CI/CD pipeline will further enforce best practices and prevent potential vulnerabilities (you can add SonarQube, I've not integrated it).
- **End-to-End Testing:** Automating reliability and robustness testing will improve efficiency and reduce manual intervention.

## **13. Workflow Overview:**
- **Code Deployment:** Developers push updates to GitHub.
- **ArgoCD:** ArgoCD detects changes in the GitHub repository and automatically redeploys the application to the Kubernetes cluster.
- **Istio Traffic Management:** Istio controls the traffic flow and supports canary deployments for smoother rollouts.
- **Monitoring:** Prometheus collects metrics on application performance, which Grafana visualizes for easy interpretation.
- **Troubleshooting:** Kiali and Jaeger are used to diagnose and resolve any issues within the service mesh.
- **Code Quality:** Before deployment, SonarQube ensures the code adheres to best practices and is free from vulnerabilities (you can add SonarQube, I've not integrated it).

## **Conclusion:**
This project showcases how integrating AWS EKS, ArgoCD, Istio, and monitoring tools like Prometheus, Grafana, and Kiali can create a scalable, reliable, and efficient microservices deployment. The use of GitOps ensures smooth and automated deployments, while Istio and monitoring tools provide control, visibility, and security for service interactions.

The end result is a system that not only scales efficiently but also maintains high performance and reliability with minimal manual intervention. 
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
I'm still learning DevOps & AWS Cloud services at core level. Please feel free to share your thoughts and experiences with me. I'd be glad to hear your opinions on this project.



