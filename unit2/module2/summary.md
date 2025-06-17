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

Compute Types

Virtual Machines
VM in the cloud running a OS and apps. You manage the OS AND the apps.

Container instances
Isolated environments without managing servers. Packages apps without its dependencies (code, libraries).
Key words: Docker image, you set CPU and Memory allocation and port mapping

Azure Functions
Serverless. Run small pieces of code in the language you want. Can be triggered by HTTP requests, timers and maybe others. Returns HTTP code and payload if available.

| **Type**            | **Control**       | **Management**       | **Use Case**                     | **Azure Service**          |
|--------------------|-------------------|---------------------|---------------------------------|---------------------------|
| Virtual Machines   | Full (OS, apps)   | You manage OS       | Custom apps, legacy systems     | Azure Virtual Machines    |
| Containers         | App + dependencies| Azure manages OS    | Microservices, portable apps    | Azure Container Instances |
| Functions          | Just code         | Azure manages all   | Event-driven tasks, automation  | Azure Functions           |

Exam Tip: Know when to use each: VMs for control, Containers for portability, Functions for automation.



