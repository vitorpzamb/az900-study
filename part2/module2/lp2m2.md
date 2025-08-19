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

- PaaS
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

---

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

---

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

---

## Azure Network

Virtual networks and virtual subnets **enable Azure resources**, such as VMs, web apps, and databases, **to communicate with each other, with users on the internet, and with your on-premises client computers**.

### Capabilities
- Isolation & segmentation: Organize and separate resources safely.
- Internet communications: Control what’s exposed publicly.
- Azure ↔️ Azure communication: Connect services securely.
- On-premises communication: Extend your office network to Azure.
- Routing: Decide where traffic goes.
- Filtering: Control what’s allowed.
- VNet peering: Connect networks privately (even worldwide).

### Public and Private Endpoints
*enable communication between external or internal resources with other internal resources*
- Public endpoints have a public IP address and can be accessed from anywhere in the world.
- Private endpoints exist within a virtual network and have a private IP address from within the address space of that virtual network.

### Internet communications
**Enable incoming connections from the internet** by **assigning a public IP address to an Azure resource**, or **putting the resource behind a public load balancer**

### Communicate between Azure resources
- **Virtual networks** 
  - **can connect** not only VMs but **other Azure resources**, such as the **App Service Environment for Power Apps, Azure Kubernetes Service, and Azure virtual machine scale sets**.
- **Service endpoints** 
  - **can connect to other Azure resource types**, such as **Azure SQL databases and storage accounts**. This approach enables you to **link multiple Azure resources to virtual networks to improve security and provide optimal routing** between resources.

## Summarized on-premises
- `Point-to-Site VPN:` one computer connects to Azure.
- `Site-to-Site VPN:` your whole office network connects to Azure over the internet.
- `ExpressRoute:` a private, super secure, high-speed connection that avoids the internet.

### Communicate with on-premises resources
*you can create a network that spans both your local and cloud environments*
- **Point-to-site virtual private network connections** 
  - from a computer outside your organization back into your corporate network. In this case, the client computer initiates an encrypted VPN connection to connect to the Azure virtual network.
- **Site-to-site virtual private networks** 
  - link your on-premises VPN device or gateway to the Azure VPN gateway in a virtual network. In effect, the devices in Azure can appear as being on the local network. The connection is encrypted and works over the internet.
- **Azure ExpressRoute** 
  - provides a dedicated private connectivity to Azure that doesn't travel over the internet. ExpressRoute is useful for environments where you need greater bandwidth and even higher levels of security.

## Summarized Route
- `Route Tables:` define custom rules for traffic.
- `BGP (Border Gateway Protocol):` automatically shares routes between your office and Azure.

### Route network traffic
*Azure routes traffic between subnets on any connected virtual networks, on-premises networks, and the internet. You also can control routing and override those settings*
- **Route tables** 
  - allow you to define rules about how traffic should be directed. You can create custom route tables that control how packets are routed between subnets.
- **Border Gateway Protocol (BGP)** 
  - works with Azure VPN gateways, Azure Route Server, or Azure ExpressRoute to propagate on-premises BGP routes to Azure virtual networks.

## Summarized Filter
- `NSGs (Network Security Groups):` simple allow/deny rules (like: “allow HTTP, block everything else”).
- `NVAs (Network Virtual Appliances):` advanced tools like firewalls or intrusion detection.

### Filter network traffic
*enable you to filter traffic between subnets*
- **Network security groups (NSG)** 
  - resources that can contain multiple inbound and outbound security rules.
- **Network virtual appliances** 
  - specialized VMs that can be compared to a hardened network appliance. A network virtual appliance carries out a particular network function, such as running a firewall or performing wide area network (WAN) optimization.

## Connect Virtual Networks
- `VNet Peering:` link two Azure networks so they act like one. Works across regions, traffic stays private.
- `UDRs (User-Defined Routes):` extra control of how traffic flows between networks/subnets.

---

## Virtual Private Networks (VPN)
*secure, encrypted tunnel that lets two private networks communicate over an untrusted network (like the internet).*
- It protects data from being seen or attacked while in transit.
- Companies use VPNs to share sensitive information safely.

### VPN Gateways
*connects networks*
- lives inside a dedicated subnet in your virtual network.
- All traffic is encrypted inside the tunnel.
- One VPN gateway per VNet, but it can connect to multiple locations.

`Site-to-Site:` your on-premises datacenter ↔️ Azure VNet.
`Point-to-Site:` a single device (like a laptop) ↔️ Azure VNet.
`VNet-to-VNet:` connect two Azure VNets together.

### VPN Types
- Policy-based VPN:
  - Uses fixed IP rules to decide what traffic goes through.
  - Less flexible.
- Route-based VPN:
  - Uses IP routing (static or dynamic) to decide where traffic goes.
  - Preferred option in Azure (better for scaling, subnets, and new connections).
  - Required for: VNet-to-VNet, Point-to-Site, multisite, ExpressRoute coexistence, and high availability.

### ⁠High Availability Options
- Active/Standby (default):
  - Two instances exist, but only one is active.
  - If the active one fails, the standby takes over automatically.
  - Failover takes a few seconds to ~90 seconds.
- Active/Active:
  - Both gateways are active, each with its own public IP.
  - Multiple tunnels are created → higher redundancy.
  - Works well with BGP routing.
- ExpressRoute Failover:
  - If your private ExpressRoute circuit fails, a VPN gateway can act as a backup connection over the internet.
- Zone-Redundant Gateways:
  - Gateways are deployed across multiple availability zones.
  - Protects from failures in a single datacenter zone.
  - Uses Standard public IPs instead of Basic.

---

## Azure ExpressRoute
*lets you extend your on-premises networks into the Microsoft cloud over a private connection*
*a private, dedicated connection between your on-premises network and Microsoft’s cloud (Azure, Microsoft 365, Dynamics 365).*
- Uses a connectivity provider (like a telecom/ISP) to set up this private circuit.
- Does NOT go over the public internet.
- Each office/datacenter needs its own ExpressRoute circuit.

### ⁠Benefits
- Direct access to Microsoft services: Office 365, Dynamics 365, Azure VMs, Azure Storage, Cosmos DB, etc.
- Global Reach: You can connect different sites worldwide (e.g., Asia office ↔️ Europe datacenter) using Microsoft’s backbone instead of the internet.
- Dynamic Routing via BGP: Automatically exchanges routes between your network and Microsoft, adapting if things change.
- Built-in Redundancy: Each connection point has backup devices to keep it highly available.

### ⁠Connectivity Models
ExpressRoute offers 4 main ways to connect your network to Azure:
- Colocation at a Cloud Exchange
  - If your datacenter/office is in the same building as a cloud exchange provider (like an ISP hub), you can connect directly via a virtual cross-connect.
- Point-to-Point Ethernet
  - A dedicated, direct Ethernet line between your facility and Azure.
- Any-to-Any (IP VPN / WAN integration)
  - Azure becomes just another “branch” in your corporate WAN (wide area network).
  - Offices and datacenters connect to Azure through your provider’s network.
- Direct from ExpressRoute Sites
  - You connect straight into Microsoft’s backbone at specific peering sites around the world.
  - ExpressRoute Direct provides massive bandwidth (10–100 Gbps) with Active/Active redundancy.

### ⁠Security Considerations
- Since it’s a private circuit, your data doesn’t travel over the public internet → less chance of interception or attack.
- BUT: Some services (like DNS queries, certificate checks, and CDN requests) still go through the internet even if you use ExpressRoute.

## Azure DNS (Domain Name System)
*Resolves works (https://google.com) in IP addresses for connection*

### Can be integrated with other Azure Resources for secutiry
- Azure role-based access control (Azure RBAC) to control who has access to specific actions for your organization.
- Activity logs to monitor how a user in your organization modified a resource or to find an error when troubleshooting.
- Resource locking to lock a subscription, resource group, or resource. Locking prevents other users in your organization from accidentally deleting or modifying critical resources.

---

