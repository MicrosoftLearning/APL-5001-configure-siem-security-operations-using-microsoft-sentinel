---
lab:
    title: 'Exercise 02: Ingest Windows Security event data'
    module: 'Guided Project - Deploy Microsoft Sentinel Content Hub solutions and data connectors'
---

>**Note**: This lab builds on Lab 01. To complete this lab, you will need an [Azure subscription.](https://azure.microsoft.com/free/?azure-portal=true) in which you have administrative access.

## General guidelines

- When creating objects, use the default settings unless there are requirements that require different configurations.
- Only create, delete, or modify objects to achieve the stated requirements. Unnecessary changes to the environment may adversely affect your final score.
- If there are multiple approaches to achieving a goal, always choose the approach the requires the least amount of administrative effort.

We need configure Microsoft Sentinel to ingest data by using Microsoft Sentinel solutions.

## Architecture diagram

![Diagram of Content Hub data connectors](../Media/apl-5001-lab-diagrams-lab02.png)

## Skilling tasks

You need to deploy Content Hub solutions in the Microsoft Sentinel workspace and meet the following requirements:

- Install the following solutions:
  - Windows Security Events.
  - Azure Activity connector.
  - Microsoft Defender for Cloud.
- Configure the data connector for Azure Activity to apply all new and existing resources in the subscription.
- Configure the data connector for Microsoft Defender for Cloud to connect to the Azure subscription and ensure that only bi-directional sync is enabled.
- Enable an analytics rule based on the Suspicious number of resource creation or deployment activities template. The rule should run every hour and only lookup data for that last hour.
- Ensure that the Azure Activity workbook is available in My workbooks.

## Exercise instructions

>**Note**: In the following tasks, to access `Microsoft Sentinel`, select the `workspace` you created in Lab 01.

### Task 1 - Deploy a Microsoft Sentinel Content Hub solution

Deploy a Content Hub solution and configure Data connectors. Learn more about [Content Hub solutions](https://learn.microsoft.com/azure/sentinel/sentinel-solutions).

1. In `Microsoft Sentinel`, go to the `Content management` menu section and select **Content Hub**
1. Search for and select **Windows Security Events**
1. Select the link for **View details**
1. Select Windows Security Events plan, and select **Create**
1. Select the `RG2` resource group that includes the Microsoft Sentinel workspace, and select the `Workspace`.
1. Select **Next** to the  Data Connectors tab (solution will deploy 2 data connectors)
1. Select **Next** to the Workbooks tab (solution installs workbooks)
1. Select **Next** to the Analytics tab (solutions installs analytics rules)
1. Select **Next** to the Hunting queries tab (solution instals hunting queries)
1. Select **Review + create**
1. Select **Create**

1. Repeat these steps for the `Azure Activity` and the `Microsoft Defender for Cloud` solutions.

### Task 2 - Set up the data connector for Azure Activity

Configure the data connector for Azure Activity to apply all new and existing resources in the subscription. Learn more about [Microsoft Sentinel data connectors](https://learn.microsoft.com/azure/sentinel/connect-data-sources).

  1. In `Microsoft Sentinel`, go to the `Content management` menu section and select **Content Hub**.
  1. In the `Content hub`, filter `Status` for Installed solutions.
  1. Select the `Azure Activity` solution and select **Manage**.
  1. Select the `Azure Activity` Data connector and select **Open connector page**.
  1. In the `Configuration` area under the `Instructions` tab, scroll down to `2. Connect your subscriptions...`, and select **Launch Azure Policy Assignment Wizard>**.
  1. In the **Basics** tab, select the ellipsis button (...) under **Scope** and select your subscription from the drop-down list and click **Select**.
  1. Select the **Parameters** tab, choose your workspace from the **Primary Log Analytics workspace** drop-down list.
  1. Select the **Remediation** tab and select the **Create a remediation task** checkbox.
  1. Select the **Review + Create** button to review the configuration.
  1. Select **Create** to finish.
  
### Task 3 - Set up the for Defender for Cloud data connector

Configure the data connector for Microsoft Defender for Cloud and ensure that that only incident management is configured.

  1. In `Microsoft Sentinel`, go to the `Content management` menu section and select **Content Hub**.
  1. In the `Content hub`, filter `Status` for Installed solutions.
  1. Select the `Microsoft Defender for Cloud` solution and select **Manage**.
  1. Select the `Subscription-based Microsoft Defender for Cloud (Legacy)` Data connector and select **Open connector page**
  1. In the `Configuration` area under the `Instructions` tab, scroll down to your subscription and move the slider in the `Status` column to **Connected**.
  1. Make sure `Bi-directional sync` is **Enabled**.

### Task 4 - Create an analytics rule

Create an analytic rule based on the Suspicious number of resource creation or deployment activities template. The rule should run every hour and only lookup data for that last hour. Learn more about [Using Microsoft Sentinel Analytic rule templates](https://learn.microsoft.com/azure/sentinel/detect-threats-built-in).

  1. In `Microsoft Sentinel`, go to the `Configuration` menu section and select **Analytics**.
  1. In the `Rule templates` tab, search for **Suspicious number of resource creation or deployment activities**.
  1. Select the **Suspicious number of resource creation or deployment activities**, and select **Create rule**.
  1. Leave the defaults on the `General` tab and select **Next: Set rule logic >**.
  1. Leave the default `Rule query` and configure `Query scheduling` using the table:

     |Setting |Value|
     |---|---|
     |Run query every|1 Hours|
     |Lookup data from the last|1 Hours|

  1. Select **Next: Incident settings >**.
  1. Leave the defaults and select **Next: Automated response >**.
  1. Leave the defaults and select **Next: Review and create >**.
  1. Select **Save**.

### Task 5 - Ensure that the Azure Activity workbook is available in My workbooks

  1. In `Microsoft Sentinel`, go to the `Content management` menu section and select **Content Hub**.
  1. In the `Content hub`, filter `Status` for Installed solutions.
  1. Select the `Azure Activity` solution and select **Manage**.
  1. Select the `Azure Activity` workbook `checkbox`, and then select **Configuration**.
  1. Select the `Azure Activity` workbook and select **Save**.
  1. Choose the `Azure Region` for your `Microsoft Sentinel` workspace.  
