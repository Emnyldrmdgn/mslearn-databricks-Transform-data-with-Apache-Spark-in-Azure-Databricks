# mslearn-databricks-Transform-data-with-Apache-Spark-in-Azure-Databricks
Azure Databricks is a Microsoft Azure-based version of the popular open-source Databricks platform. Azure Databricks is built on Apache Spark, and offers a highly scalable solution for data engineering and analysis tasks that involve working with data in files.

# Transform Data with Apache Spark in Azure Databricks

This guide provides the steps to transform data using Apache Spark in Azure Databricks. Follow these steps to complete the lab exercise:

## Steps

1. **Provision Azure Databricks Workspace**
   - Open Azure Cloud Shell in PowerShell mode.
   - Clone the repo and run the setup script:
     ```powershell
     rm -r mslearn-databricks -f
     git clone https://github.com/MicrosoftLearning/mslearn-databricks
     ./mslearn-databricks/setup.ps1
     ```

2. **Create a Cluster**
   - Open the Databricks workspace.
   - Create a new cluster with:
     - Runtime: 13.3 LTS or higher
     - Node Type: Standard_D4ds_v5
     - Mode: Single Node
     - Terminate after 20 mins of inactivity

3. **Create a Notebook**
   - Name: `Transform data with Spark`
   - Connect it to the cluster

4. **Ingest Data**
   - Run the following shell commands to download CSV files:
     ```bash
     %sh
     rm -r /dbfs/spark_lab
     mkdir /dbfs/spark_lab
     wget -O /dbfs/spark_lab/2019.csv https://raw.githubusercontent.com/MicrosoftLearning/mslearn-databricks/main/data/2019_edited.csv
     wget -O /dbfs/spark_lab/2020.csv https://raw.githubusercontent.com/MicrosoftLearning/mslearn-databricks/main/data/2020_edited.csv
     wget -O /dbfs/spark_lab/2021.csv https://raw.githubusercontent.com/MicrosoftLearning/mslearn-databricks/main/data/2021_edited.csv
     ```

5. **Load Data with Schema**
   - Define schema and load CSVs into a DataFrame.

6. **Clean the Data**
   - Remove duplicates.
   - Replace nulls in `Tax` column with `UnitPrice * 0.08` and cast to float.

7. **Filter Data**
   - Filter to view distinct customers and those who ordered a specific product.

8. **Aggregate and Group Data**
   - Group by `Item` to sum quantities.
   - Group by year to count orders.

9. **Run SQL Queries**
   - Create a temp view of the DataFrame.
   - Use `%sql` magic to run SQL and analyze revenue by year.

10. **Clean Up**
   - Terminate the cluster.
   - Delete resources to avoid extra costs.

---

For more details, refer to the [Azure Databricks documentation](https://learn.microsoft.com/en-us/azure/databricks/).

## Screenshots

![lab3databricks](https://github.com/user-attachments/assets/898719ac-b826-48d0-8e48-e605861986a7)
![lab3databricks2](https://github.com/user-attachments/assets/cee0e510-adcc-4807-8b76-754f9005865a)
![lab3databricks3](https://github.com/user-attachments/assets/93100bf7-80b2-4d97-b694-4d460ca20416)
![lab3databricks3_2](https://github.com/user-attachments/assets/637752e8-b6e7-4a56-8b37-4e80b78fcfed)
![lab3databricks3_3](https://github.com/user-attachments/assets/2c0f595d-e845-449c-aede-6b3d4d8411b1)
![lab3databricks3_4](https://github.com/user-attachments/assets/449b741f-6828-4475-85cb-a91f18e95585)
![lab3databricks3_5](https://github.com/user-attachments/assets/97ef41a5-1c8e-4214-8f8d-6c30b7a28f49)
![lab3databricks3_6](https://github.com/user-attachments/assets/559034c7-01e6-4d56-828b-ff8cacfafcb6)
![lab3databricks4sql](https://github.com/user-attachments/assets/073dcd49-4dcb-44eb-9d75-6dd1029d9e4a)
![lab3databricks5](https://github.com/user-attachments/assets/300a2c3d-8ac8-460c-9e20-821327f17154)
