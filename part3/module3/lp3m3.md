# Managing and Deploying Resources

## How to interact with Azure
- Azure portal
- Azure PowerShell
- Azure Command Line Interface (CLI)

## Azure Cloud Shell
*a terminal inside azure portal, just like your machine terminal*

## Azure Arc
- Manage your entire environment together by projecting your existing non-Azure resources into ARM.
- Manage multi-cloud and hybrid virtual machines, Kubernetes clusters, and databases as if they are running in Azure.
- Use familiar Azure services and management capabilities, regardless of where they live.
- Continue using traditional ITOps while introducing DevOps practices to support new cloud and native patterns in your environment.
- Configure custom locations as an abstraction layer on top of Azure Arc-enabled Kubernetes clusters and cluster extensions.

### What Arc can Manage outside Azure
- Servers
- Kubernetes clusters
- Azure data services
- SQL Server
- Virtual machines (preview)

## Azure Resource Manager (Arm)
- Manage your infrastructure through declarative templates rather than scripts. A Resource Manager template is a JSON file that defines what you want to deploy to Azure.
- Deploy, manage, and monitor all the resources for your solution as a group, rather than handling these resources individually.
- Re-deploy your solution throughout the development life-cycle and have confidence your resources are deployed in a consistent state.
- Define the dependencies between resources, so they're deployed in the correct order.
- Apply access control to all services because RBAC is natively integrated into the management platform.
- Apply tags to resources to logically organize all the resources in your subscription.
- Clarify your organization's billing by viewing costs for a group of resources that share the same tag.

### ARM template benefits
- Declarative syntax
- Repeatable results
- Orchestration
- Modular files
- Extensibility

## Bicep
*a language that uses declarative syntax to deploy Azure resources*