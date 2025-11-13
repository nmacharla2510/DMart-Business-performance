# 🛒 DMart E-Commerce Business Performance & Customer Engagement Analysis

## 📌 Project Overview

DMart, a mid-sized retail business, is facing increased competition and requires deeper insights into customer behavior, sales trends, inventory management, online engagement, and product sentiment. This project delivers a unified analytics solution using structured and unstructured data to drive strategic decisions and improve customer satisfaction.

---

## 🎯 Objective

Leverage structured (transactional, inventory) and unstructured (social media, reviews, web logs) data to build a scalable analytics pipeline using the Medallion architecture. The solution tracks key business KPIs and supports actionable insights.

---

## 🗂️ Data Sources

- **Structured Data**: GitHub-hosted JSON files
- **Unstructured Data**: Social media, reviews, web logs
- **Connection Setup**:
  - Raw link: `https://raw.githubusercontent.com/nmacharla2510/DMart-Business-performance`
  - Connection name: `DMartStructuredDatalinkBronze`
  - Relative path: `refs/heads/main/DMart_StructuredData/{json_variable}`

---

## 🏗️ Pipeline Architecture

![Alt text](https://github.com/nmacharla2510/DMart-Business-performance/blob/main/pictures/Medallion%20Task.png)

### 🔹 Bronze Layer

- Created pipelines for both structured and unstructured data
  
  ![Alt text](https://github.com/nmacharla2510/DMart-Business-performance/blob/main/pictures/pipeline%20for%20Struct%26unstruct.png)
  
- Activities:
  - `Lookup`: Retrieves JSON file paths
  - `Foreach`: Iterates over JSON values
  - `Delete`: Removes existing files dynamically
  - `Copy`: Uses parameterized source/destination paths

   ![Alt text](https://github.com/nmacharla2510/DMart-Business-performance/blob/main/pictures/foreach.png)
    
- Output: JSON files copied to Bronze Lakehouse
  
  ![Alt text](https://github.com/nmacharla2510/DMart-Business-performance/blob/main/pictures/Blayerfiles.png)

### 🔸 Silver Layer

- Created Silver Lakehouse
- Referenced Bronze files via shortcuts
- Used PySpark notebooks to: 📓 [View DMart Analysis Sliver Notebook](https://github.com/nmacharla2510/DMart-Business-performance/blob/main/pyspark_notebook/DMart_Silver_Transformation.ipynb))
  - Clean and join dataframes
  - Write clean data as Parquet files to Silver Lakehouse
    
![Alt text](https://github.com/nmacharla2510/DMart-Business-performance/blob/main/pictures/Slayerfilewithshortcuts.png)

### 🟡 Gold Layer

- Created Gold Lakehouse
- Referenced Silver files via shortcuts
- Used notebooks to: 📓 [View DMart Analysis Gold Notebook](https://github.com/nmacharla2510/DMart-Business-performance/blob/main/pyspark_notebook/DMart_Gold_Transformation.ipynb))
  - Perform aggregations
  - Write final output to Gold Lakehouse
    
![Alt text](https://github.com/nmacharla2510/DMart-Business-performance/blob/main/pictures/Glayerfiles.png)
---

## 📊 Data Modeling & Visualization

- Converted Gold layer Parquet files to Delta tables
- Created semantic model with relationships
- Built custom Date table for time intelligence
- Developed Power BI dashboards:
  - **DMart Overall Task Flow**
  - **DMart Project Lineage**
    
    ![Alt text](https://github.com/nmacharla2510/DMart-Business-performance/blob/main/pictures/ProjectLineage.png)
    ![Alt text](https://github.com/nmacharla2510/DMart-Business-performance/blob/main/pictures/PowerBi.png)

---

## ✅ Final Execution

- Created and executed a master pipeline integrating all stages
- Delivered a complete analytics solution with full lineage and visualization
![Alt text](https://github.com/nmacharla2510/DMart-Business-performance/blob/main/pictures/MasterPipeline.png)
---

## 📎 Tools & Technologies

- Microsoft Fabric (Lakehouse, Pipelines, Notebooks)
- PySpark
- GitHub (source hosting)
- Power BI (semantic modeling and dashboards)

---

## 📌 Author

**Naveen Macharla**  
Azure Data Engineer | Workflow Optimization Specialist  
📍 Based in Canada | Open to new opportunities  
🔗 [LinkedIn](https://www.linkedin.com/in/naveen-macharla-pmp-4454b5292) | [GitHub](https://github.com/nmacharla2510/nmacharla2510)
