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

PARAMOS AQUI https://learn.microsoft.com/en-us/training/modules/describe-azure-compute-networking-services/3-exercise-create-azure-virtual-machine

---

Compute services and Networking services

Compite -> pocessing power
Networking -> connecting services

Test will focus on:
- Compare compute types (ACI - Azure Container Instances, VM - Virtual Machines, Azure Functions)
- Compare VM options
- Comprate hosting choices
- Understand networking concepts

## Compute Types

### Virtual Machines
VM in the cloud running a OS and apps. You manage the OS AND the apps.

### Container instances
Isolated environments without managing servers. Packages apps without its dependencies (code, libraries).
Key words: Docker image, you set CPU and Memory allocation and port mapping

### Azure Functions
Serverless. Run small pieces of code in the language you want. Can be triggered by HTTP requests, timers and maybe others. Returns HTTP code and payload if available.

| **Type**            | **Control**       | **Management**       | **Use Case**                     | **Azure Service**          |
|--------------------|-------------------|---------------------|---------------------------------|---------------------------|
| Virtual Machines   | Full (OS, apps)   | You manage OS       | Custom apps, legacy systems     | Azure Virtual Machines    |
| Containers         | App + dependencies| Azure manages OS    | Microservices, portable apps    | Azure Container Instances |
| Functions          | Just code         | Azure manages all   | Event-driven tasks, automation  | Azure Functions           |

Know when to use each: VMs for control, Containers for portability, Functions for automation.

---

## VM Options

### VM Scale Sets
Just like auto scale concept. Group of identical VMs scaling based on demand.
*Use cases: Apps or services needing to handle varying loads*

### VM Availability Sets
VMs are spread accross across different Availability Zones to prevent downtime if on server fails

### Azure Virtual Desktop
A remote Windows desktop

**Memorization Tip**
*Scale Sets = “Grow/shrink VMs.”*
*Availability Sets = “Stay online.”*
*Virtual Desktop = “Work from anywhere.”*

## VM Resources

- OS Disks -> Windows or Linux OS installed in the VM
- Data Disk -> HD or SSD installed in the BM
- NIC - Network Interface Card -> Connects VM to a Virtual Networs (VNet)
- Virtual Network -> A private network for the BM to communcate securely
- Public IP (optional) -> For external access (e.g. web traffic)
- Resource Group -> Logical azure group to organize resources

### Key Configuration Fields

- Disk Type (SSD for speed, HDD for cost)
- Subnet (part of the VNet for the NIC - Network Interface Card)
- Security Group -> firewall rules for the NIC

Remember: in the last module, when we creted the first resource (the VM), several other resources were added/created in the RG (Resource Group) because all those were required for the VM to work properly.