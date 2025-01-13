# About Dataset
Here's everything this dataset includes about Paris Olympics summer games 2024:
all results (updated asap or daily)
venues,teams,medals, total_medals. Based on the datasets on kaggle I did drop some tables. It's fror learning purpose.
here is the link: https://www.kaggle.com/datasets/sajkazmi/paris-olympics-2024-games-dataset-updated-daily
License
CC BY-NC-SA 4.0


**Paris 2024 Olympic Azure Data Engineering Project**

**Project Overview**  
This project demonstrates a complete data engineering pipeline using various Azure tools. The goal is to ingest, store, transform, and analyze data related to the Paris 2024 Olympics. The final output is visualized using Power BI.

**Data Set**  
The dataset consists of multiple tables containing information about athletes, teams, events, and medals. The data is available in CSV format and can be accessed through the following links:

- Athletes.csv
- coaches.csv
- Teams.csv
- Medals.csv
- Total_medals.csv


**Tools Used**  
The project leverages the following Azure services:

- **Azure Data Factory**: Used for data ingestion and orchestration.
- **Azure Data Lake Storage Gen2**: Used for storing raw and transformed data.
- **Azure Databricks**: Used for data transformation and processing.
- **Azure Synapse Analytics**: Used for data analysis and querying.
- **Power BI**: Used for data visualization and creating dashboards.

**Project Workflow**  

1. **Data Ingestion**:  
   - Data is ingested from the data source using Azure Data Factory.  
   - The ingested data is stored in Azure Data Lake Storage Gen2 as raw data.

2. **Data Transformation**:  
   - Raw data is transformed using Azure Databricks.  
   - The transformed data is then stored back in Azure Data Lake Storage Gen2.

3. **Data Analysis**:  
   - Transformed data is analyzed using Azure Synapse Analytics.  
   - Basic charts and analyses are performed in Azure Synapse Analytics.

4. **Data Visualization**:  
   - The analyzed data is visualized using Power BI to create interactive dashboards.

**Notebook**  
The Azure Databricks notebook used for basic data transformation is included in this repository:

- **Paris-Olympics-Data.ipynb**

**Example Query**  
An example SQL query used in Azure Synapse Analytics for analyzing the data:

```sql
WITH a AS 
(
    SELECT 
        a.Name AS AthleteName,
        COUNT(a.Name) AS Total_Number_of_Athletes,
        e.Event AS Event
    FROM 
        athletes a
    JOIN 
        events e ON a.Event_ID = e.Event_ID
    GROUP BY 
        a.Name, e.Event
)
SELECT 
    a.AthleteName AS Athlete
FROM 
    a;
```

**Conclusion**  
This project showcases a comprehensive data engineering pipeline using Azure services. From data ingestion to transformation and visualization, each step demonstrates the power and flexibility of Azure for handling complex data workflows. 
