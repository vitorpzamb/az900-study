## Azure Storage

| Type                     | Supported Services                                      | Redundancy Options          | Usage                                                                 |
|--------------------------|--------------------------------------------------------|-----------------------------|----------------------------------------------------------------------|
| Standard general-purpose v2 | Blob Storage (including Data Lake Storage), Queue Storage, Table Storage, Azure Files | LRS, GRS, RA-GRS, ZRS, GZRS, RA-GZRS | Standard storage account type for blobs, file shares, queues, and tables. Recommended for most scenarios using Azure Storage. If you want support for network file system (NFS) in Azure Files, use the premium file shares account type. |
| Premium block blobs       | Blob Storage (including Data Lake Storage)              | LRS, ZRS                    | Premium storage account type for block blobs and append blobs. Recommended for scenarios with high transaction rates or that use smaller objects or require consistently low storage latency. |
| Premium file shares       | Azure Files                                            | LRS, ZRS                    | Premium storage account type for file shares only. Recommended for enterprise or high-performance scale applications. Use this account type if you want a storage account that supports both Server Message Block (SMB) and NFS file shares. |
| Premium page blobs        | Page blobs only                                        | LRSx

### Redundance
*copies of your data to protect it from hardware failures, outages, or disasters.*
**Data in an Azure Storage account is always replicated three times in the primary region.**

Redundnace Options
- LRS (Locally Redundant Storage) – copies data within one datacenter.
- ZRS (Zone-Redundant Storage) – spreads data across multiple zones in one region.
- GRS (Geo-Redundant Storage) – copies data to another region.
- RA-GRS (Read-Access GRS) – like GRS, but with read access in secondary region.
- GZRS (Geo-Zone Redundant Storage) – combines ZRS + GRS (zones + another region).
- RA-GZRS (Read-Access GZRS) – same as GZRS with read access to secondary region.

Primary Region Options
- LRS (Locally Redundant Storage)
  - 3 copies in one datacenter.
  - Cheapest, 99.999999999% durability (11 nines).
  - Protects against server/rack failure, but not datacenter-wide disasters.
- ZRS (Zone-Redundant Storage)
  - 3 copies across different availability zones in the same region.
  - 99.9999999999% durability (12 nines).
  - Survives zone failure, keeps data available for read/write.
  - Recommended for high availability within one region.

Secondary Region Options
- GRS (Geo-Redundant Storage)
  - Like LRS in two regions: 3 copies in primary, 3 in secondary (asynchronous replication).
  - 99.99999999999999% durability (16 nines).
  - Secondary region is only usable after failover.
- GZRS (Geo-Zone-Redundant Storage)
  - Combines ZRS in primary + LRS in secondary.
  - Best option for maximum durability and disaster recovery.
  - 16 nines durability.
- Read-Access Options
  - RA-GRS = Read-Access Geo-Redundant Storage.
  - RA-GZRS = Read-Access Geo-Zone-Redundant Storage.

LRS → cheapest, protects only inside one datacenter.
ZRS → spreads across zones, protects against zone failures.
GRS → copies data to another region for disaster recovery.
GZRS → combines ZRS + secondary region for maximum protection.
RA-GRS / RA-GZRS → let you read from secondary region anytime.

## Storage Services
Azure Blobs: A massively scalable object store for text and binary data. Also includes support for big data analytics through Data Lake Storage Gen2.
Azure Files: Managed file shares for cloud or on-premises deployments.
Azure Queues: A messaging store for reliable messaging between application components.
Azure Disks: Block-level storage volumes for Azure VMs.
Azure Tables: NoSQL table option for structured, non-relational data.

Storage services are always
- Durable and highly available
- Secure
- Scalable
- Managed
- Accessible

- Blob Storage
Hot Tier 🔥
For frequently accessed data.
Storage = most expensive, but retrieval = cheapest and fastest.

Cool Tier ❄️
For infrequently accessed data (kept at least 30 days).
Storage = cheaper than hot, retrieval = a bit more expensive.

Cold Tier 🧊
For data accessed very rarely (kept at least 90 days).
Even cheaper storage, but higher access costs and lower availability.

Archive Tier 📦
For data you almost never access (kept at least 180 days).
Storage = cheapest of all, but data is kept offline → restoring it takes hours and costs more.

Key Considerations
Hot, Cool, Cold tiers → can be set at account level (all blobs) or blob level (specific file).
Archive tier → only at blob level, not at account level.

Trade-offs:
Cool/Cold: Lower availability SLA + higher read costs, but storage is cheaper.
Archive: Lowest cost to store, but highest cost and longest delay to read.

- Azure Files
A cloud-based file server managed by Azure.
How you use it: Works just like a normal network file share — you can connect using SMB (Windows/Linux/macOS) or NFS (Linux/macOS).
Extra: With Azure File Sync, you can cache files locally on Windows Servers for faster access near users.

- ⁠Azure Queues
A message storage service.
How you use it: Applications send messages into a queue, and other components read/process them later.
Capacity: Millions of messages, each up to 64 KB.

- ⁠Azure Disks
Cloud-based block storage (like virtual hard drives).
How you use it: Attach them to Azure VMs as their operating system disk or data disks.
Managed: Azure takes care of durability, backups, and performance.

- ⁠Azure Tables
A NoSQL datastore for structured, non-relational data.
How you use it: Store huge amounts of key-value or entity data, accessible via authenticated API calls.
Works across clouds: Can be used in hybrid or multicloud setups.

### Storage Services Summarized
Blobs: Any file
Files = Cloud file server (SMB/NFS shares).
Queues = Message system for async processing.
Disks = Virtual hard drives for VMs.
Tables = NoSQL structured storage.

## Data Migration Options

- Azure Migrate
helps you migrate from an on-premises environment to the cloud

### Integrated tools
- Azure Migrate: Discovery and assessment
  - Discover and assess on-premises servers running on VMware, Hyper-V, and physical servers in preparation for migration to Azure.
- Azure Migrate: Server Migration. 
  - Migrate VMware VMs, Hyper-V VMs, physical servers, other virtualized servers, and public cloud VMs to Azure.
- Data Migration Assistant. 
  - Data Migration Assistant is a stand-alone tool to assess SQL Servers. It helps pinpoint potential problems blocking migration. It identifies unsupported features, new features that can benefit you after migration, and the right path for database migration.
- Azure Database Migration Service. 
  - Migrate on-premises databases to Azure VMs running SQL Server, Azure SQL Database, or SQL Managed Instances.
- Azure App Service migration assistant. 
  - Azure App Service migration assistant is a standalone tool to assess on-premises websites for migration to Azure App Service. Use Migration Assistant to migrate .NET and PHP web apps to Azure.
- Azure Data Box. 
  - Use Azure Data Box products to move large amounts of offline data to Azure.

### File movement options
- AzCopy
  - Tool installed via `apt` or `brew`. Command line tool.
- Azure Storage Explorer
  - Downloadeble app. Works like an interface to manage your files.
- Azure File Sync
  - App/Tool for Windows Server that when installed syncs your data with Azure
