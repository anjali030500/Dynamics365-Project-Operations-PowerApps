# Project Operations Dashboard

Through these Power BI reports customers will be able to visualize the data of Project Operations Application in Power BI and get insights from it.

# How to use

## Prerequisites for using Export to Data Lake Service 

1) You must create and configure an Azure data lake Gen2 account.
2) We can follow the steps mentioned here to create the Storage account https://docs.microsoft.com/en-us/azure/storage/common/storage-account-create?tabs=azure-portal.
3) Set your storage as Storagev2 (general purpose v2).
4) The storage account must have the Hierarchical Name Space feature enabled.
5) You must be granted an Owner role on the storage account.
6) The storage account must be created in the same Azure AD tenant as your PowerApps tenant.
7) It is recommended that the storage account is created in the same region as the PowerApps environment you plan to use it in.
8) It is recommended to set replication setting to Read-access geo-redundant storage (RA-GRS).

## Flow from Micrososft Dataverse (CDS) to Azure Data Lake Storage (ADLS)

The data flow from Microsoft Dataverse to ADLS is automatated. there are few steps we need to follow to get this working.

1) Go to this link https://make.preview.powerapps.com/environments, you can see something like this.

![Power Apps](../images/power-apps.jpg)

2) Now click on GO to home page, you will be redirected here.

![Power Apps Preview](../images/power-apps-preview.jpg)

3) Click on Dataverse in the right panel under that go to Azure Synapse Link.

![Azure Synapse Link](../images/create-azure-synapse.jpg)

4) Create an Azure Synapse Link (formerly known as Export to Data Lake) so that Dataverse can be connected with Azure Data Lake storage.

5) After creation of Azure Synapse link we will manage the tables that we want to sync from dataverse to ADLS, we will go to manage tables.

![Manage Tables](../images/manage-tables-azure-synapse-link.jpg)

6) Now sync these tables that are shown in the image.
* If the tables are not available when you try to sync then we need to make some changes in the dataverse platform.

*  Go to dataverse platform.

![Dataverse Platform](../images/project-operations-dashboard.jpg)

* Go to Settings->Advanced Settings->Settings->Customizations 

* This page will be displayed now.

![Settings  Dataverse](../images/settings-project-operations.jpg)

* Select the option customize the system, we will be redirected here.

![Settings  Dataverse](../images/settings2-dataverse.jpg)

* Under components that is on left side, under the entities choose the table that was not visible during creation of Azure Synapse Link, now enable the "Change Tracking" option.

![Change Tracking option](../images/change-tracking.jpg)

* Now save and publish the changes through the upper ribbon on the plaform.

* Now the tables will be visible in the manage tables option and we can sync that.

## SQL SCripts in Azure Synapse Studio to create the views

Under this directory we have SQL-Scripts folder, in that many folders are there in which SQL Scripts are there.
To start with, when we will run these scripts views will be generated.

1) To create the database run the query that is in Createdatabase folder in Azure Synapse Studio.
2) As the database has been created from the above step, we will create the views that are required to create the visualizations in Power BI.
3) To create the views run the SQL Scripts that are present in Common, Health and Product directory.
4) if you want to drop all the views then you can use Teardown directory and run the script that is present in it.

## Connection between Power BI and Serverless SQL Database

1) Download the Power BI report from here https://microsoftapc-my.sharepoint.com/:u:/g/personal/t-asewani_microsoft_com/EXtQibSUH8JBp3RnQ6AN0goBakGRfeKNRe5Y7H7aMsMrFQ?e=aJOdPB.
2) Connect it with your Data source by selecting "Get Data" option and then with "Azure Synapse Analytics SQL".
3) Enter the link and the Power BI will be connected to the data through Direct Query mode.


















