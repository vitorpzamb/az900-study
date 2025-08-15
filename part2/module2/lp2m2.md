# Describe Azure compute and networking services

## VM - Virtual Machine
- Kind of IaaS (Infrastructure as a Service)
- Just like a physical computer, you can customize all of the software running on your VM

- Ideal choice when you need:
  1. Total control over the operating system (OS)
  2. The ability to run custom software
  3. To use custom hosting configurations
- Gives you the flexibility of virtualization without having to buy and maintain the physical hardware that runs the VM

**You still need to configure, update, and maintain the software that runs on the VM**

### Scale
- you can group VMs together to provide high availability, scalability, and redundancy

### Virtual machine scale sets
- let you create and manage a group of identical, load-balanced VMs

### Virtual machine availability sets
- designed to ensure that VMs stagger updates and have varied power and network connectivity, preventing you from losing all your VMs with a single network or power failure

### When to use VMs

- **During testing and development**. VMs provide a quick and easy way to create different OS and application configurations. Test and development personnel can then easily delete the VMs when they no longer need them.
- **When running applications in the cloud**. The ability to run certain applications in the public cloud as opposed to creating a traditional infrastructure to run them can provide substantial economic benefits. For example, an application might need to handle fluctuations in demand. Shutting down VMs when you don't need them or quickly starting them up to meet a sudden increase in demand means you pay only for the resources you use.
- **When extending your datacenter to the cloud**: An organization can extend the capabilities of its own on-premises network by creating a virtual network in Azure and adding VMs to that virtual network. Applications like SharePoint can then run on an Azure VM instead of running locally. This arrangement makes it easier or less expensive to deploy than in an on-premises environment.
- **During disaster recovery**: As with running certain types of applications in the cloud and extending an on-premises network to the cloud, you can get significant cost savings by using an IaaS-based approach to disaster recovery. If a primary datacenter fails, you can create VMs running on Azure to run your critical applications and then shut them down when the primary datacenter becomes operational again.

### VM Resources
- Size (purpose, number of processor cores, and amount of RAM)
- Storage disks (hard disk drives, solid state drives, etc.)
- Networking (virtual network, public IP address, and port configuration)

## Virtual Desktop

- Paas
- VM that you customize/configure so people can only log in and do their work

## Virtual Machines (VMs) vs. Containers vs. Virtual Desktops: A Comparison

### Overview
Virtual Machines (VMs), Containers, and Virtual Desktops are virtualization technologies used to support different workloads in Azure. This comparison highlights their key differences, relevant to the AZ-900 exam.

### Key Differences

| **Aspect**              | **Virtual Machines (VMs)**                              | **Containers**                                        | **Virtual Desktops**                                  |
|-------------------------|-------------------------------------------------------|-----------------------------------------------------|-----------------------------------------------------|
| **Architecture**        | Full virtualized OS with hypervisor, running a complete guest OS (e.g., Windows, Linux). | Lightweight, shares host OS kernel, includes app and dependencies. | Virtualized desktop environment (e.g., Windows) hosted in the cloud, accessed remotely. |
| **Resource Usage**      | High resource consumption (CPU, memory, storage) due to full OS. | Low resource usage, shares host OS kernel.          | Moderate to high, depends on desktop OS and user sessions. |
| **Startup Time**        | Slower (minutes) due to booting entire OS.             | Fast (seconds) as only app and libraries load.     | Moderate (seconds to minutes), depending on session initialization. |
| **Portability**         | Less portable; tied to specific hypervisor and OS configurations. | Highly portable via container images (e.g., Docker). | Not portable; tied to desktop environment and user configurations. |
| **Isolation**           | Strong isolation via hypervisor, ideal for multi-tenant scenarios. | Lighter isolation via OS-level namespaces and cgroups. | Strong isolation for user sessions, managed at the desktop level. |
| **Scalability**         | Scales by adding VMs, but slower and resource-intensive. | Scales quickly, ideal for microservices.           | Scales by adding sessions or hosts, optimized for user concurrency. |
| **Management in Azure**  | Managed via Azure Virtual Machines, supports diverse workloads. | Managed via Azure Kubernetes Service (AKS) or Azure Container Instances (ACI). | Managed via Azure Virtual Desktop (AVD), supports remote desktop access. |
| **Use Cases**           | Legacy apps, full OS control, or strict isolation needs. | Microservices, cloud-native apps, DevOps, CI/CD pipelines. | Remote work, virtualized desktop apps, secure access to corporate resources. |

### Azure Context
- **VMs**: Use Azure Virtual Machines for workloads requiring full OS control, such as legacy applications or specific software configurations.
- **Containers**: Use Azure Container Instances (ACI) for quick, serverless container deployment or Azure Kubernetes Service (AKS) for orchestrating containerized microservices.
- **Virtual Desktops**: Use Azure Virtual Desktop (AVD) to provide secure, remote desktop and app access for employees, supporting hybrid work environments.

### Summary
- **VMs**: Best for heavy, isolated workloads with full OS control but are resource-heavy and slower to scale.
- **Containers**: Lightweight, portable, and ideal for modern, scalable, cloud-native applications but offer less isolation.
- **Virtual Desktops**: Optimized for delivering secure, remote desktop experiences, balancing resource use and user-specific needs.

## Azure Container Instances (ACI) vs. Azure Container Apps (ACA) vs. Azure Kubernetes Service (AKS)

### Overview
ACI, ACA, and AKS are Azure services for running containerized applications, each suited for different use cases based on complexity, scalability, and management needs.

### Comparison Table

| **Aspect**             | **Azure Container Instances (ACI)** | **Azure Container Apps (ACA)** | **Azure Kubernetes Service (AKS)** |
|------------------------|------------------------------------|--------------------------------|------------------------------------|
| **Description**        | Serverless, single-container hosting with minimal setup. | Serverless platform for microservices with built-in scaling. | Fully managed Kubernetes for complex, orchestrated workloads. |
| **Management**         | Fully managed, no orchestration.   | Fully managed, Kubernetes-based, abstracts cluster management. | Managed Kubernetes, user manages some cluster configurations. |
| **Scaling**            | Manual scaling, no auto-scaling.   | Auto-scaling (KEDA), supports scale-to-zero. | Manual or auto-scaling (HPA, Cluster Autoscaler). |
| **Use Cases**          | Short-lived tasks, prototyping, simple apps. | Microservices, event-driven apps, background jobs. | Complex, enterprise-grade apps with custom orchestration. |
| **Complexity**         | Low, no Kubernetes knowledge needed. | Medium, simplified Kubernetes features. | High, requires Kubernetes expertise. |
| **Azure Integration**  | Basic integration with Azure services. | Strong integration (e.g., Dapr, Envoy). | Extensive integration with Kubernetes ecosystem. |

### Summary
- **ACI**: Simplest, for lightweight, short-lived tasks with no orchestration.
- **ACA**: Ideal for serverless microservices with auto-scaling and minimal management.
- **AKS**: Best for complex, scalable workloads requiring full Kubernetes control.

## Azure Functions

- No need to manage OS or anything
- Event driven 
- Auto scalable
- Support many languages
- Keyworks: API, REST, CRUDE

## Azure App Service

- Service to build and host Web Apps
- Runs on the programming language of your choice without managing infrastructure
- Offers automatic scaling and high availability
- Support Windows or Linux
- Enables automated deployments from GitHub, Azure DevOps, or any Git repo

Azure App Service is an HTTP-based service for hosting web applications, REST APIs, and mobile back ends. It supports multiple languages, including .NET, .NET Core, Java, Ruby, Node.js, PHP, or Python. It also supports both Windows and Linux environments.

## Azure Web Apps vs. API Apps vs. WebJobs vs. Mobile Apps

### Overview
Azure Web Apps, API Apps, WebJobs, and Mobile Apps are part of Azure App Service, each designed for specific application hosting and processing needs.

### Comparison Table

| **Aspect**          | **Web Apps**                          | **API Apps**                         | **WebJobs**                          | **Mobile Apps**                      |
|---------------------|---------------------------------------|--------------------------------------|--------------------------------------|--------------------------------------|
| **Description**     | Hosts web applications and websites.  | Hosts RESTful APIs for apps.         | Runs background tasks and scripts.   | Hosts mobile app backends.           |
| **Primary Use**     | Web UIs, front-end apps (e.g., ASP.NET, Node.js). | API endpoints for apps (e.g., REST, Swagger). | Scheduled or triggered tasks (e.g., data processing). | Mobile app services (e.g., push notifications, auth). |
| **Scaling**         | Auto-scaling, manual scaling.         | Auto-scaling, manual scaling.        | Scales with App Service plan.         | Auto-scaling, manual scaling.        |
| **Execution**       | Continuous, user-driven.              | Continuous, API-driven.              | Scheduled or triggered (continuous or on-demand). | Continuous, mobile-driven.           |
| **Use Cases**       | Websites, web apps, e-commerce.       | Microservices, API integrations.     | Batch jobs, queue processing.        | Mobile app backends, offline sync.   |
| **Azure Integration**| App Service, supports multiple frameworks. | App Service, API Management integration. | App Service, triggered by Azure services (e.g., queues). | App Service, mobile SDKs, auth.      |

### Summary
- **Web Apps**: Best for hosting web applications and user-facing interfaces.
- **API Apps**: Ideal for building and exposing APIs for various clients.
- **WebJobs**: Suited for background tasks, such as data processing or scheduled jobs.
- **Mobile Apps**: Designed for mobile app backends with features like push notifications and authentication.

PARAMOS AQUI https://learn.microsoft.com/en-us/training/modules/describe-azure-compute-networking-services/8-virtual-network

---

