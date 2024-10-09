# Azure-end-to-end-project
Tools: SQL,Python,Azure Databricks, Azure data Factory, Azure Synapse Analytics
Project overview
![image](https://github.com/user-attachments/assets/fe7fceda-ba5f-4682-82c5-9884b222c70c)

Used SQL Server Management Studio (SSMS) to create and manage a database, then transferred the data to Azure Data Factory for data ingestion and processing.

![image](https://github.com/user-attachments/assets/c1cbc68e-fc0d-4ef4-a700-9528cd2c2e08)

Developed pipelines in azure data factory and stored data in date lake storage gen2.
![image](https://github.com/user-attachments/assets/d6d7ef4d-d4df-4913-b090-df3bec33353d)

Utilized Azure Databricks transform the RAW data to the most cleanest form of data.
https://github.com/mumar112/Azure-end-to-end-project/blob/main/Storagemount.ipynb
onfigs = {
  "fs.azure.account.auth.type": "CustomAccessToken",
  "fs.azure.account.custom.token.provider.class": spark.conf.get("spark.databricks.passthrough.adls.gen2.tokenProviderClassName")
}

# Optionally, you can add  to the source URI of your mount point.
dbutils.fs.mount(
  source = "abfss://bronze@datastoragegen2m.dfs.core.windows.net/",
  mount_point = "/mnt/bronze",
  extra_configs = configs)
     
Out[2]: True

dbutils.fs.ls("/mnt/bronze/SalesLT/")
     
Out[5]: [FileInfo(path='dbfs:/mnt/bronze/SalesLT/Address/', name='Address/', size=0, modificationTime=0),
 FileInfo(path='dbfs:/mnt/bronze/SalesLT/Customer/', name='Customer/', size=0, modificationTime=0),
 FileInfo(path='dbfs:/mnt/bronze/SalesLT/CustomerAddress/', name='CustomerAddress/', size=0, modificationTime=0),
 FileInfo(path='dbfs:/mnt/bronze/SalesLT/Product/', name='Product/', size=0, modificationTime=0),
 FileInfo(path='dbfs:/mnt/bronze/SalesLT/ProductCategory/', name='ProductCategory/', size=0, modificationTime=0),
 FileInfo(path='dbfs:/mnt/bronze/SalesLT/ProductDescription/', name='ProductDescription/', size=0, modificationTime=0),
 FileInfo(path='dbfs:/mnt/bronze/SalesLT/ProductModel/', name='ProductModel/', size=0, modificationTime=0),
 FileInfo(path='dbfs:/mnt/bronze/SalesLT/ProductModelProductDescription/', name='ProductModelProductDescription/', size=0, modificationTime=0),
 FileInfo(path='dbfs:/mnt/bronze/SalesLT/SalesOrderDetail/', name='SalesOrderDetail/', size=0, modificationTime=0),
 FileInfo(path='dbfs:/mnt/bronze/SalesLT/SalesOrderHeader/', name='SalesOrderHeader/', size=0, modificationTime=0)]

configs = {
  "fs.azure.account.auth.type": "CustomAccessToken",
  "fs.azure.account.custom.token.provider.class": spark.conf.get("spark.databricks.passthrough.adls.gen2.tokenProviderClassName")
}

# Optionally, you can add  to the source URI of your mount point.
dbutils.fs.mount(
  source = "abfss://silver@datastoragegen2m.dfs.core.windows.net/",
  mount_point = "/mnt/silver",
  extra_configs = configs)
     
Out[8]: True

configs = {
  "fs.azure.account.auth.type": "CustomAccessToken",
  "fs.azure.account.custom.token.provider.class": spark.conf.get("spark.databricks.passthrough.adls.gen2.tokenProviderClassName")
}

# Optionally, you can add  to the source URI of your mount point.
dbutils.fs.mount(
  source = "abfss://gold@datastoragegen2m.dfs.core.windows.net/",
  mount_point = "/mnt/gold",
  extra_configs = configs)
     
Out[9]: True
https://github.com/mumar112/Azure-end-to-end-project/blob/main/bronze%20to%20silver.ipynb

https://github.com/mumar112/Azure-end-to-end-project/blob/main/silver%20to%20gold.ipynb

Used Azure Synapse Analytics to load the clean data
![image](https://github.com/user-attachments/assets/cef959a4-f242-4f53-9d30-d0396947a9c1)

