# AdventureWorks2017LT Azure Migration Project

## Overview
This project demonstrates the end-to-end migration of the **AdventureWorks2017LT** dataset from an on-premises SQL Server database to the Microsoft Azure cloud. The architecture leverages Azure Data Factory (ADF) for data ingestion, Azure Data Lake Storage Gen2 for data storage, Azure Databricks for data transformation, and Azure Synapse Analytics for advanced querying and reporting. The transformed data is visualized using Power BI for insights.

![image](https://github.com/user-attachments/assets/33af88b1-47ce-4d27-82e2-2dc629aea9d9)

## Architecture
The solution follows the **medallion architecture**, consisting of Bronze, Silver, and Gold layers to manage data at various stages of processing:
- **Bronze Layer**: Raw ingested data stored in Azure Data Lake Gen2.
- **Silver Layer**: Cleaned and enriched data processed using Azure Databricks.
- **Gold Layer**: Aggregated and analytics-ready data for querying and reporting.

### Components Used:
1. **Azure Data Factory**: Ingests data from the on-premises SQL Server into Azure Data Lake.
2. **Azure Data Lake Storage Gen2**: Serves as the primary data storage solution.
3. **Azure Databricks**: Performs data transformations, including cleaning and aggregation.
4. **Azure Synapse Analytics**: Enables querying and data modeling for reporting purposes.
5. **Power BI**: Provides reporting and visualization capabilities.
6. **Azure Active Directory**: Ensures secure access control.
7. **Azure Key Vault**: Manages sensitive connection strings and secrets.

## Steps to Reproduce

### Prerequisites
1. **Azure Subscription**: Ensure you have an active Azure subscription.
2. **AdventureWorks2017LT Dataset**: Download the on-prem SQL Server dataset.
3. **Power BI Desktop**: For visualizing the data.

### Implementation
#### 1. Data Ingestion
- Use **Azure Data Factory** self-hosted IR to connect to the on-premises SQL Server.
- Create a pipeline to move the dataset to the **Bronze Layer** in Azure Data Lake Gen2.
![image](https://github.com/user-attachments/assets/f38a1536-50b9-4fb5-9d13-5cbfaf37a1b3)

#### 2. Data Transformation
- Use **Azure Databricks** notebooks for:
  - Cleaning raw data.
  - Enriching and processing data into the **Silver Layer**.
  - Generating business metrics and aggregations in the **Gold Layer**.

#### 3. Data Loading
- Load the processed data into **Azure Synapse Analytics**.
- Create Serverless External Tables.
![image](https://github.com/user-attachments/assets/37fcbe96-19cc-4781-92f8-187bf5d1653e)


#### 4. Security & Governance
- Implement **Microsoft Entra ID** for user authentication.
- Secure sensitive data with **Azure Key Vault**.

## Key Highlights
- **Cost-Efficient Design**: Utilizes scalable Azure resources to handle enterprise data efficiently.
- **Secure Data Management**: Incorporates Azure-native security tools like Active Directory and Key Vault.
- **Scalable Pipeline**: Supports large-scale data processing with Azure Databricks and Synapse Analytics.


## License
This project is licensed under the MIT License.

---
## Acknowledgments
- This use case is taken from 'Mr. K Talks Tech' youtube channel, Big thanks to him.
- Feel free to explore and adapt this solution for your own use cases! Feedback and contributions are welcome.
