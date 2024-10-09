# Azure-end-to-end-project
Tools: SQL,Python,Azure Databricks, Azure data Factory, Azure Synapse Analytics

The use case for this project is building an end to end solution by ingesting the tables from on-premise SQL Server database using Azure Data Factory and then store the data in Azure Data Lake. Then Azure databricks is used to transform the RAW data to the most cleanest form of data and then we are using Azure Synapse Analytics to load the clean data .Also, we are using Azure Active Directory (AAD) and Azure Key Vault for the monitoring and governance purpose. 


Project overview

![image](https://github.com/user-attachments/assets/fe7fceda-ba5f-4682-82c5-9884b222c70c)

Used SQL Server Management Studio (SSMS) to create and manage a database, then transferred the data to Azure Data Factory for data ingestion and processing.

![image](https://github.com/user-attachments/assets/c1cbc68e-fc0d-4ef4-a700-9528cd2c2e08)

Developed pipelines in azure data factory and stored data in date lake storage gen2.
![image](https://github.com/user-attachments/assets/d6d7ef4d-d4df-4913-b090-df3bec33353d)

Utilized Azure Databricks transform the RAW data to the most cleanest form of data.
https://github.com/mumar112/Azure-end-to-end-project/blob/main/Storagemount.ipynb

https://github.com/mumar112/Azure-end-to-end-project/blob/main/bronze%20to%20silver.ipynb

https://github.com/mumar112/Azure-end-to-end-project/blob/main/silver%20to%20gold.ipynb

Used Azure Synapse Analytics to load the clean data

![image](https://github.com/user-attachments/assets/cef959a4-f242-4f53-9d30-d0396947a9c1)

