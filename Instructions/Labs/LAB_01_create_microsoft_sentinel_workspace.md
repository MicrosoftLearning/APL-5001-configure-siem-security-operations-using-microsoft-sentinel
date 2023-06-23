---
lab:
    title: 'Exercise 01: Create and configure a Microsoft Sentinel workspace'
    module: 'Guided Project - '
---

We are currently evaluating the existing security posture or our corporate environment. We need your help in setting up a security information and event management (SIEM) solution to help identify future and ongoing cyber-attacks..

## Architecture diagram
![Diagram with one storage account](../Media/task-1.png)

## Skilling tasks
- . 
- . 

## Exercise instructions

### Create a Log Analytics workspace

1. Create and configure a Microsoft Sentinel workspace. Learn more about [resource groups](https://learn.microsoft.com/azure/azure-resource-manager/management/manage-resource-groups-portal).
    - In the Azure portal, search for and select `Resource groups`.
    - Select **+ Create**.
    - Give your resource group a **name**. For example, `storagerg`.
    - Select a **region**. Use this region throughout the project. 
    - Select **Review and create** to validate the resource group.
    - Select **Create** to deploy the resource group.

1. Create and deploy a storage account to support testing and training. Learn more about the [types of storage accounts](https://learn.microsoft.com/azure/storage/common/storage-account-overview#types-of-storage-accounts).
    - In the Azure portal, search for and select  `Storage accounts`. 
    - Select **+ Create**.
    - On the **Basics** tab, select your **Resource group**.
    - Provide a **Storage account name**. The storage account name must be unique in Azure. 
    - Set the **Performance** to **Standard**. 
    - Select **Review**, and then **Create**. 
    - Wait for the storage account to deploy and then **Go to resource**.  

### Configure simple settings in the storage account.

1. The data in this storage account doesn't require high availability or durability. A lowest cost storage solution is desired. Learn more about [storage account redundancy](https://learn.microsoft.com/azure/storage/common/storage-redundancy#locally-redundant-storage).
    - In your storage account, in the **Data management** section, select the **Redundancy** blade.
    - Select **Locally-redundant storage (LRS)** in the **Redundancy** drop-down. 
    - Be sure to **Save** your changes. 
    - Refresh the page and notice the content only exists in the primary location. 

1. The storage account should only accept requests from secure connections. Learn more about [requiring secure transfer from secure connections](https://learn.microsoft.com/azure/storage/common/storage-require-secure-transfer)
    - In the **Settings** section, select the **Configuration** blade.
    - Ensure **Secure transfer required** is **Enabled**. 

1. Developers would like the storage account to use at least TLS version 1.2. Learn more about [transport layer security (TLS)](https://learn.microsoft.com//azure/storage/common/transport-layer-security-configure-minimum-version?tabs=portal).
    - In the **Settings** section, select the **Configuration** blade.
    - Ensure the **Minimal TLS version** is set to **Version 1.2**.  


1. Until the storage is needed again, disable requests to the storage account. Learn more about [disabling shared keys](https://learn.microsoft.com/azure/storage/common/shared-key-authorization-prevent?tabs=portal#disable-shared-key-authorization).
    - In the **Settings** section, select the **Configuration** blade.
    - Ensure **Allow storage account key access** is **Disabled**.
    - Be sure to **Save** your changes. 

1. Ensure the storage account allows public access from all networks.  
    - In the **Security + networking** section, select the **Networking** blade.
    - Ensure **Public network access** is set to **Enabled from all networks**.
    - Be sure to **Save** your changes. 

>**Note**: For additional practice complete the [Create an Azure Storage Account](https://learn.microsoft.com/training/modules/create-azure-storage-account/) module. The module has a sandbox where you can practice creating a storage account.
