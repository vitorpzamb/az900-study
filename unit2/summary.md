**https://learn.microsoft.com/en-us/training/paths/azure-fundamentals-describe-azure-architecture-services/**

# Azure Virtual Machines Summary for AZ-900

## Overview of Azure Virtual Machines (VMs)
- **Definition**: Azure VMs provide Infrastructure as a Service (IaaS) by offering virtualized servers in the cloud, functioning like physical computers.
- **Customization**: Full control over the operating system (OS), ability to run custom software, and configure custom hosting setups.
- **Flexibility**: Virtualization without managing physical hardware, but you must configure, update, and maintain the VM’s software.
- **Provisioning**: Rapidly create VMs using preconfigured images (templates with OS and software like development tools or web hosting environments).

## Scaling VMs in Azure
- **Single VMs**: Suitable for testing, development, or small tasks.
- **Grouping Options**: Azure provides tools like scale sets and availability sets to enhance scalability, availability, and redundancy.

### Virtual Machine Scale Sets
- **Purpose**: Manage and create groups of identical, load-balanced VMs.
- **Automation**: Azure automates configuration, updates, and load balancing.
- **Scaling**: Automatically adjusts VM instances based on demand or a set schedule.
- **Use Cases**: Ideal for large-scale compute, big data, and container workloads.

### Virtual Machine Availability Sets
- **Purpose**: Ensure high availability and resilience by distributing VMs across update and fault domains.
- **Update Domains**: Group VMs that can reboot together, with a 30-minute recovery period before the next group updates.
- **Fault Domains**: Group VMs by shared power and network resources, defaulting to up to three domains to protect against failures.
- **Cost**: No additional cost for availability sets; you only pay for VM instances.

## Use Cases for Azure VMs
- **Testing and Development**: Quickly create and delete VMs with various OS and application configurations.
- **Running Cloud Applications**: Cost-effective for applications with fluctuating demand, as VMs can be started or stopped as needed.
- **Datacenter Extension**: Extend on-premises networks to Azure using virtual networks, enabling applications like SharePoint to run on VMs.
- **Disaster Recovery**: Use VMs for cost-efficient disaster recovery by running critical applications during primary datacenter failures.
- **Lift and Shift**: Migrate physical servers to the cloud by hosting their images in VMs with minimal changes, though OS and software maintenance is required.

## VM Resources
- **Size**: Choose purpose, processor cores, and RAM.
- **Storage**: Select hard disk drives (HDDs), solid-state drives (SSDs), etc.
- **Networking**: Configure virtual networks, public IP addresses, and ports.