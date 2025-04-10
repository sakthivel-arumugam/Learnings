**Helm charts**
Helm Charts are a powerful tool in Kubernetes for managing and deploying applications. They act as a package manager for Kubernetes, simplifying the deployment of complex applications by bundling all the necessary Kubernetes resources into a single package.

What is a Helm Chart?
A Helm Chart is a collection of files that describe a set of Kubernetes resources.
It includes templates for Kubernetes manifests (like Deployments, Services, ConfigMaps, etc.) and configuration files.
Helm Charts allow you to define, install, and upgrade even the most complex Kubernetes applications with ease.

Key Components of a Helm Chart
Chart.yaml:
Contains metadata about the chart, such as its name, version, and description.
values.yaml:
Defines default configuration values for the chart. These values can be overridden during deployment.
templates/:
A directory containing Kubernetes manifest templates. These templates are rendered using the values provided in values.yaml.
charts/:
A directory for dependencies (other charts that this chart relies on).
README.md (optional):
Provides documentation about the chart.

Benefits of Using Helm Charts
Simplified Deployment:
Deploy an entire application stack with a single command.
Version Control:
Charts are versioned, allowing you to roll back to previous versions if needed.
Reusability:
Charts can be reused across different environments (e.g., dev, staging, production) with minimal changes.
Customizability:
Use values.yaml to customize deployments without modifying the chart itself.

![Image](https://github.com/user-attachments/assets/7b131f97-70a1-4414-bb7c-71a86a74191d)

**Using DTR with Kubernetes**
Docker Trusted Registry (DTR) is an enterprise-grade, private container image registry that allows teams to securely store, manage, and distribute Docker images. 
DTR can be integrated with Kubernetes to store and serve container images. Some key points:

Private Registry for Kubernetes – DTR acts as a private registry where Kubernetes nodes pull container images.
Security & Access Control – DTR provides role-based access control (RBAC), image scanning, and signing to ensure secure image deployment.
Helm Charts & Kubernetes Deployments – You can configure Kubernetes to pull images from DTR using imagePullSecrets.
Alternative to Public Registries – Instead of using Docker Hub or other public registries, enterprises use DTR to maintain control over their images.

![Image](https://github.com/user-attachments/assets/6dc3082d-3253-4961-8a3a-44065d67906b)

What Happens During a Spike?
Scenario: 1 lakh messages suddenly enter the queue
KEDA (Kubernetes Event-Driven Autoscaling). detects high queue length (>10,000 messages).
HPA scales consumer pods (e.g., from 2 → 20 pods).
If nodes are full, Cluster Autoscaler adds more nodes.
Pods consume messages, reducing queue size.
Once queue size stabilizes, extra pods and nodes are removed.

How KEDA Works?
Monitors External Event Sources
KEDA listens to event-driven triggers such as message queues, Kafka topics, or HTTP requests.
Activates the Deployment (Scale to 1 or More Pods)
If an event occurs, KEDA activates the Kubernetes deployment, scaling the pod count from zero to one or more.
Dynamically Adjusts Scaling
KEDA integrates with HPA to determine the required number of pods based on event intensity.
Scales Back to Zero
If no new events occur, KEDA scales the deployment back to zero to save resources.

![Image](https://github.com/user-attachments/assets/9dd03c5d-ac5a-4b32-bc79-b18890095d58)

https://sgithub.fr.world.socgen/Pegasus/nuvo-architecture/wiki/Helm-overview-and-usage

The **Service object** is what allows the application to be exposed internally: behind the scenes, it creates a VIP to access the service within Kubernetes that automatically load-balances traffic across all available pods. **The pods related to the service are identified using labels: all pods that have the label defined in the Service's configuration will be considered as pods that can accept traffic for the service**
The **Deployment object** defines, as the name suggests, how the application is supposed to be deployed. It lists the containers (init and main ones), the image they are to run, their resource allocation **(RAM and CPU), the amount of replicas, the volumes they need to mount, the various Kubernetes monitoring probes**, etc.
The **Ingress object** defines **the exposition of the application outside of Kubernetes:** since we expose web services to users within the SG network, it is necessary for us to make our services accessible from anywhere on the GBIS network that isn't necessarily part of the Kubernetes cluster
