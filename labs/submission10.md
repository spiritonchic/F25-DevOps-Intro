# Lab 10 — Cloud Computing Fundamentals

## Task 1 — Artifact Registries Research

### Service Name and Details for Each Cloud Provider

#### AWS – Amazon Elastic Container Registry (ECR)
- **Supported Artifacts:** Docker / OCI container images  
- **Key Features:** Private & public repos, IAM access control, encryption at rest & in transit, pull-through cache, cross-region replication  
- **Integration:** Works with AWS ECS, EKS, Fargate, CodePipeline, and other AWS services  
- **Pricing Model:** Pay per GB stored per month and per GB data transferred; additional charges for cross-region replication  
- **Common Use Cases:** Store container images for microservices, CI/CD pipelines, serverless applications  

#### GCP – Google Cloud Artifact Registry
- **Supported Artifacts:** Docker / OCI images, Maven, npm, Python packages, and others  
- **Key Features:** Multi-format support, IAM access control, regional & multi-regional repos, remote & virtual repos, vulnerability scanning  
- **Integration:** Cloud Build, GKE, Cloud Run, App Engine, and other GCP services  
- **Pricing Model:** Pay per GB stored and per GB egress; different rates for regional vs multi-regional storage  
- **Common Use Cases:** Unified artifact storage for multi-language projects, container image hosting, dependency management  

#### Azure – Azure Container Registry (ACR)
- **Supported Artifacts:** Docker / OCI images, Helm charts, OCI artifacts  
- **Key Features:** Geo-replication, build & patch automation (ACR Tasks), RBAC via Entra ID, pull-through cache, VNet integration  
- **Integration:** AKS, App Service, Azure DevOps, and other Azure services  
- **Pricing Model:** Tiered pricing (Basic, Standard, Premium) based on storage, operations, and geo-replication  
- **Common Use Cases:** Container image storage for AKS, CI/CD pipelines, multi-region deployments  

### Comparison Table

| Cloud Provider | Registry Service        | Supported Artifact Types       | Key Features                                                        | Integration                                   | Pricing Model                         | Common Use Cases                                       |
|----------------|------------------------|-------------------------------|---------------------------------------------------------------------|-----------------------------------------------|--------------------------------------|-------------------------------------------------------|
| AWS            | Amazon Elastic Container Registry (ECR) | Docker / OCI                  | Private & public repos, IAM, encryption, pull-through cache, cross-region replication | ECS, EKS, Fargate, CodePipeline              | Pay per GB stored and transferred     | Container images for microservices, CI/CD, serverless apps |
| GCP            | Google Cloud Artifact Registry | Docker/OCI, Maven, npm, Python | Multi-format, IAM, regional/multi-regional, remote/virtual repos, vulnerability scanning | Cloud Build, GKE, Cloud Run, App Engine      | Pay per GB stored and egress          | Unified artifact storage, multi-language projects, container images |
| Azure          | Azure Container Registry (ACR) | Docker/OCI, Helm charts, OCI artifacts | Geo-replication, ACR Tasks, RBAC, pull-through cache, VNet integration | AKS, App Service, Azure DevOps              | Tiered: Basic, Standard, Premium      | Container images for AKS, CI/CD, multi-region deployments |

### Analysis: Which registry service would you choose for a multi-cloud strategy and why?
For a multi-cloud strategy, **GCP Artifact Registry** is the most flexible choice. It supports multiple artifact types (Docker/OCI, Maven, npm, Python), making it suitable for projects with mixed technology stacks. Its regional and multi-regional capabilities simplify replication across clouds, and it integrates well with CI/CD tools like Cloud Build and GKE. While AWS ECR and Azure ACR are strong within their ecosystems, GCP’s multi-format support and centralization of artifacts provide greater interoperability for multi-cloud deployments.

---

## Task 2 — Serverless Computing Platform Research

### AWS – AWS Lambda
- **Key Features & Capabilities:** Event-driven compute service, automatic scaling, integrated logging & monitoring via CloudWatch, triggers from 200+ AWS services  
- **Supported Runtimes / Languages:** Node.js, Python, Java, Go, Ruby, .NET Core  
- **Pricing Model:** Pay per request and duration; free tier includes 1M requests and 400,000 GB-seconds per month  
- **Performance Characteristics:** Highly available, low-latency execution; cold start latency possible; scales to zero when idle  
- **Common Use Cases:** REST API backends, data processing pipelines, scheduled tasks, IoT event processing  

### GCP – Google Cloud Functions
- **Key Features & Capabilities:** Event-driven, deep integration with Google Cloud services, automatic scaling & load balancing  
- **Supported Runtimes / Languages:** Node.js, Python, Go, Java  
- **Pricing Model:** Pay per request & compute time; free tier includes 2M invocations and 400,000 GB-seconds per month  
- **Performance Characteristics:** Fast scaling; cold starts possible but optimized for HTTP triggers; low operational overhead  
- **Common Use Cases:** Microservices, APIs, real-time data processing, event-driven automation  

### Azure – Azure Functions
- **Key Features & Capabilities:** Event-driven, triggers from Azure services, durable functions for stateful workflows, auto-scaling  
- **Supported Runtimes / Languages:** C#, JavaScript/Node.js, Python, PowerShell, Java  
- **Pricing Model:** Consumption plan (pay per execution) or Premium plan (reserved resources)  
- **Performance Characteristics:** Automatic scaling, high availability; cold start latency varies; supports long-running workflows  
- **Common Use Cases:** Serverless APIs, webhooks, scheduled jobs, event-driven data transformations  

### Comparison Table

| Cloud Provider | Service Name       | Key Features & Capabilities                          | Supported Runtimes / Languages        | Pricing Model                        | Performance Characteristics                  |
|----------------|-----------------|----------------------------------------------------|--------------------------------------|--------------------------------------|----------------------------------------------|
| AWS            | AWS Lambda       | Auto-scaling, event-driven, integrated monitoring | Node.js, Python, Java, Go, Ruby, .NET | Pay per request & duration            | Low-latency, highly available, scales to zero |
| GCP            | Cloud Functions  | Event-driven, integrates with Google services     | Node.js, Python, Go, Java             | Pay per request & compute time       | Fast scaling, low cold start for HTTP triggers |
| Azure          | Azure Functions  | Event-driven, triggers from Azure services        | C#, JavaScript, Python, PowerShell    | Consumption plan: pay per execution | Scales automatically, supports durable functions |

### Analysis: Which serverless platform would you choose for a REST API backend and why?
For a REST API backend, **AWS Lambda** is the strongest option due to mature integrations with API Gateway, DynamoDB, and other AWS services. Its extensive runtime support, high scalability, and robust ecosystem make it ideal for production workloads in microservices architecture.

### Reflection: What are the main advantages and disadvantages of serverless computing?

**Advantages:**  
- No server management  
- Automatic scaling  
- Pay-per-use pricing reduces cost  
- Fast deployment and CI/CD integration  

**Disadvantages:**  
- Cold start latency for some runtimes  
- Limited execution time per function  
- Vendor lock-in risks  
- Complexity increases with many functions
