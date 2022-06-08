# Project Operations Dashboard

This feature will be in Dynamics 365 Project Operations application, the dashboards throgh which the customers will be able to visualize the data of Project Operations Application in Power BI and get insights from it.

# How to use

## Flow from Micrososft Dataverse (CDS) to Azure Data Lake Storage (ADLS)

The data flow from Microsoft Dataverse to ADLS is automatated. there are few steps we need to follow to get this working.

1) Go to this link https://make.preview.powerapps.com/environments, you can see something like this.
![Time line view](https://github.com/anjali030500/Dynamics365-Project-Operations-PowerApps/blob/main/images/PowerApps.png?raw=true)




## SQL SCripts in Azure Synapse Studio to create the views

Under This directory we have SQL-Scripts folder, in that many folders are there in which SQL Scripts are there.
To start with when we will run these scripts views will be generated.

1) To create the database run the query that is in Createdatabase folder in Azure Synapse Studio.
2) As the database has been created from the above step, we will create the views that are required to create the visualizations in Power BI.
3) To create the views run the SQL Scripts that are present in Common, Health and Product directory.
4) if you want to drop all the views then you can use Teardown directory and run the script that is present in it.