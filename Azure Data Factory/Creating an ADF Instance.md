# Creating an Azure Data Factory Instance
Azure Data Factory (ADF) is Microsoft’s cloud-native service for managing batch data integration workloads. ADF is an example of a serverless cloud service – you use it to create your own ETL applications, but you don’t have to worry about infrastructure like operating systems or servers or how to manage changes in demand.

## Explore the Azure Portal
The Azure portal is where you manage all your Azure resources. Three features are always present:

1. In the top left of the home page, you will find a Create a resource button (“plus” icon). This option is also available from the portal menu, accessed using the hamburger button in the top left.
2. In the top right, the email address you used to sign in is displayed.
3. Immediately below your email address is your current directory. If you are using a free trial subscription, this will say DEFAULT DIRECTORY.

<img width="1845" height="777" alt="image" src="https://github.com/user-attachments/assets/ae264f00-48a3-4e28-8f66-56511ee08f61" />

Your directory, commonly called a tenant, is an instance of **Microsoft Entra ID**, formerly known as **Azure Active Directory (AAD)**. “Default Directory” is the default name of a new tenant. If you are already using Azure in your job, you will probably be using a tenant that represents your company or organization – often, all of an organization’s Azure resources and users are defined in the same single tenant.
A **tenant** contains one or more subscriptions. A **subscription** identifies a means of payment for Azure services – the cost of using any Azure resource is billed to the subscription with which it is associated. **Management Group** is a	High-level governance, policy enforcement, cost reporting across multiple subscriptions.
```SQL
Management Group
   └── Subscription
         └── Resource Group
               └── Resources (VMs, Databricks, Storage, etc.)
```

>Example: A Data Warehouse team can have multiple subscriptions, possibly **TEST** and **PRODUCTION**

## Create a Resource Group
Instances of Azure services are referred to generally as resources. An instance of Azure Data Factory is an example of a resource. **Resources** belonging to a subscription are organized further into resource groups. A **resource group** is a logical container used to collect together related resources – for example, all the resources that belong to a data warehousing or analytics platform.

<img width="1713" height="806" alt="image" src="https://github.com/user-attachments/assets/dd972be1-db04-4764-8fd1-04f0563e3876" />

## Create an Azure Data Factory

1.	Go back to the Azure portal home page and click Create a resource, in the same way you did when creating your resource group.
2.	In the Search services and marketplace box on the Create a resource blade, enter “data factory”. When “data factory” appears as an item in the dropdown menu, select it.
3.	Find the Data Factory tile in the marketplace search results, then select Data Factory from the tile’s Create dropdown.
4.	The Basics tab of the Create Data Factory blade is displayed, select the Subscription and Resource group you created earlier, then choose the Region that is geographically closest to you.
5.	Choose a Name for your ADF instance. Data factory names can only contain alphanumeric characters and hyphens and must be globally unique across Azure – your choice of name will not be available if someone else is already using it. I use data factory names ending in “-adf” to make it easy to see what kind of Azure resource this is.
6.	Version is set automatically to “V2.” (It is no longer possible to create instances of ADF V1, and this book is concerned exclusively with Azure Data Factory V2).
7.	Click the Next button, then on the Git configuration tab, ensure that the Configure Git later check box is ticked.
8.	Finally, click Review + create, check the factory settings you provided in steps 4 to 7, then click Create to start deployment. (I am purposely bypassing the three remaining tabs – Networking, Advanced, and Tags – and accepting their default values).
