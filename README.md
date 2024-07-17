# Azure Data Challenge

## Overview
This repository contains the solution for the Azure Data Challenge. The goal is to build a scalable and efficient data solution using Azure Data Services to handle large data volumes in a production environment.

## Challenge Steps

1. **Setup Environment**:
   - Copy `CustomerData.csv` to `C:\Kaits\Inbox\`.
   - Install the gateway to import `CustomerData.csv` to the Azure cloud container.
   - Create folders in Azure Data Lake Gen2:
     - `Kaits\Inbox`
     - `Kaits\Processed`
   - Create an `Kaits` database in Azure SQL Database.
   - Execute scripts to create tables `DimCustomers` and `DimGeography`:
     - `Tables_SQL2012.sql` or
     - `Tables_SQL2014.sql`
   - Ensure `DimGeography` has 655 records and `DimCustomers` is empty.

2. **Data Processing**:
   - Load `CustomerData.csv` into the `DimCustomers` table using a pipeline.
   - Map `City` and `CountryRegionCode` to `GeographyKey` in `DimGeography`.
   - Implement SCD1 logic in the pipeline.
   - Move the processed file to `Kaits\Processed`.

## Validation Criteria
1. First pipeline execution should insert the same number of records as in the file into `DimCustomers`.
2. Second execution with the same file should result in no new records if no changes are made.
3. Modify the file and run the pipeline to update the modified record.
4. Ensure the file is moved to the `Processed` folder after each execution.

## Bonus Points
- Implement the solution using additional Azure data services like Azure Databricks.


