**Describe Azure compute and networking services**

**https://learn.microsoft.com/en-us/training/modules/describe-azure-compute-networking-services/**

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