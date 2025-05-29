# 📊 Employment Opportunities for International Students in California

This repository presents a comprehensive data engineering project focused on processing and analyzing employment data in California to support international student workforce initiatives. The project involved setting up scalable data infrastructure, cleaning raw datasets, and executing SQL queries across distributed systems to identify employment trends by industry and time period.

## 👥 Team Members

- Deepthimai Potla  
- Abda Fatima Syeda  
- Thulsi Buyyankar  
- Sharanya Chinnigari  
- Mohammed Shaik Afroz  
- Tanaya Dutt  

## 🧾 Project Overview

**Objective:**  
To collect, store, clean, and analyze employment data across California counties and years, enabling data analysts to extract valuable insights for international student employment strategy.

**Datasets:**  
Three datasets sourced from:
- [California Open Data Portal](https://data.ca.gov/)
- [Data.gov](https://data.gov)

**Tools & Technologies:**
- Google Cloud Platform (GCP)
- Hadoop & Spark (via Dataproc)
- OpenRefine
- BigQuery
- Hive & Spark SQL

## 📁 Workflow Summary

### 1. Data Storage & Infrastructure Setup
- Created GCP project and storage bucket (`CES2024`)
- Uploaded static datasets for 2002–2013, 2014–2024, and 2023–2025
- Configured clusters using Dataproc with 1 manager and 2 worker nodes

### 2. Data Cleaning
- Used OpenRefine to handle missing values, convert data types, and remove irrelevant columns
- Verified consistency across datasets

### 3. Data Warehousing & Analysis
- Ingested cleaned datasets into BigQuery
- Performed SQL-based exploratory queries on hospital employment trends and overall employment distribution

### 4. Distributed Query Processing
- Created external tables in Hive and Spark
- Executed comparative queries to evaluate response time and performance between Hive and Spark
- Spark consistently demonstrated better performance than Hive

## 📈 Key Insights

- Identified top 5 and top 10 industries with highest employment across different time periods
- Significant industry trends emerged in the hospital and services sectors
- Spark proved more efficient in query execution across large datasets

## 📊 Query Examples

```sql
-- Example: Total hospital employment from 2002 to 2013
SELECT Year, Month, Industry_Title, SUM(Current_Employment) AS Total_Employment
FROM ces2024group2.ces202401.ces2024table1
WHERE Industry_Title = 'Hospitals'
GROUP BY Year, Month, Industry_Title
ORDER BY Year, Month
LIMIT 50;
```

## 📌 Performance Comparison (Hive vs Spark)

| Query | Hive Time | Spark Time |
|-------|-----------|------------|
| SELECT * LIMIT 1 | 13.99s     | 6.74s      |
| SELECT * LIMIT 5 | 6.39s      | 0.42s      |
| Top 10 industries | 7.74s      | 4.91s      |

## 📅 Project Timeline & Milestones

- GCP Setup: April 13–20, 2024
- Data Cleaning: April 13–20, 2024
- Query Execution: April 20–27, 2024
- Report Completion & Presentation: April 27, 2024

## 📚 References

- [California Employment Statistics Dataset](https://data.ca.gov/dataset/current-employment-statistics-ces-2)
- [Short-Term Industry Employment Projections](https://catalog.data.gov/dataset/short-term-industry-employment-projections)
- [Google Cloud Documentation](https://cloud.google.com/gcp)

---

This project demonstrates an end-to-end data engineering workflow using cloud infrastructure and distributed computing to support meaningful employment analytics for international students in California.
