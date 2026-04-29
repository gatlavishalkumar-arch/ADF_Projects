# 🚀 Azure End-to-End ETL Data Engineering Projects

A collection of **production-ready ETL pipelines** built with **Azure Data Factory**
covering two complete end-to-end data engineering workflows using
**MySQL** and **PostgreSQL** as sources, following **Medallion Architecture**.

---

## 📁 Projects Included

| Project | Source | Destination | Layers |
|---------|--------|-------------|--------|
| Project 1 | MySQL | Azure SQL Database | Bronze → Silver → Gold |
| Project 2 | PostgreSQL | Azure SQL Database | Bronze → Silver → Gold |

---

# 🗂️ PROJECT 1 — MySQL to Azure SQL Database

## 🏗️ Architecture Flow
---

## 📌 Pipeline 1 — MySQL to ADLS Gen2 (Ingestion)

| Property             | Value                        |
|----------------------|------------------------------|
| **Source**           | MySQL Database               |
| **Sink**             | Azure Data Lake Storage Gen2 |
| **Region**           | East Asia                    |
| **Status**           | ✅ Succeeded                 |
| **Rows Read**        | 100                          |
| **Rows Written**     | 100                          |
| **Data Read**        | 19 KB                        |
| **Data Written**     | 8.365 KB                     |
| **Copy Duration**    | 16 seconds                   |
| **Throughput**       | 6.333 KB/s                   |
| **Parallel Copies**  | 1                            |
| **Start Time**       | 4/28/2026, 4:27:09 PM        |

### 🖼️ Pipeline 1 Screenshot
<img width="1441" height="815" alt="MySQL_ADLS_Silver" src="https://github.com/user-attachments/assets/205688a8-b5e7-46ea-91a8-83117585f231" />

---

## 📌 Pipeline 2 — ADF Mapping Data Flow (Transformation)

**Pipeline:** `Mysql_Silver_Gold` → `Data flow1`
**Data Flow Status:** ✅ Success
**Cluster Startup Time:** 4m 13s
**Number of Transformations:** 5

### 🔁 Data Flow Steps
### ⚙️ Transformation Details

| Step                 | Type            | Purpose                             |
|----------------------|-----------------|-------------------------------------|
| `sourceSilverMySQL`  | Source          | Read data from ADLS Gen2 Silver Layer |
| `DateColumnFormat`   | Derived Column  | Standardize date formats            |
| `removeDecimal`      | Derived Column  | Strip unwanted decimal values       |
| `PurchaseColumn`     | Derived Column  | Apply purchase business logic       |
| `sinkMysqlSQLDB`     | Sink            | Write cleansed data to SQL Database |

### 🖼️ Pipeline 2 Screenshot
<img width="1520" height="402" alt="MySQL_ADLS_Silver_Transform_ADLSGold" src="https://github.com/user-attachments/assets/87f5602f-a710-472a-9abb-54edf9e27f47" />

---

## 📌 Pipeline 3 — ADLS Gen2 to Azure SQL Database (Final Load)

| Property              | Value                        |
|-----------------------|------------------------------|
| **Source**            | Azure Data Lake Storage Gen2 |
| **Sink**              | Azure SQL Database           |
| **Region**            | East Asia                    |
| **Status**            | ✅ Succeeded                 |
| **Files Read**        | 1                            |
| **Rows Read**         | 100                          |
| **Rows Written**      | 100                          |
| **Data Read**         | 10.938 KB                    |
| **Data Written**      | 21.8 KB                      |
| **Copy Duration**     | 12 seconds                   |
| **Throughput**        | 3.646 KB/s                   |
| **DIUs Used**         | 4                            |
| **Start Time**        | 4/28/2026, 4:36:23 PM        |

### 🖼️ Pipeline 3 Screenshot
<img width="1452" height="861" alt="MySQL_ADLSGold_AzureSQL" src="https://github.com/user-attachments/assets/73318858-06ef-4ec6-8113-0c632f57b9c6" />

---

## 🏆 Project 1 — Pipeline Summary

| Pipeline | Source        | Sink                 | Rows | Duration | Status |
|----------|--------------|----------------------|------|----------|--------|
| 1        | MySQL         | ADLS Gen2 (Bronze)   | 100  | 16 sec   | ✅     |
| 2        | ADLS Gen2     | Data Flow Transform  | 100  | 4m 13s   | ✅     |
| 3        | ADLS Gen2     | Azure SQL Database   | 100  | 12 sec   | ✅     |

---
---

# 🗂️ PROJECT 2 — PostgreSQL to Azure SQL Database

## 🏗️ Architecture Flow
---

## 📌 Pipeline 1 — PostgreSQL to ADLS Gen2 (Ingestion)

| Property              | Value                          |
|-----------------------|--------------------------------|
| **Source**            | PostgreSQL                     |
| **Sink**              | Azure Data Lake Storage Gen2   |
| **Region**            | East Asia                      |
| **Status**            | ✅ Succeeded                   |
| **Rows Read**         | 100                            |
| **Rows Written**      | 100                            |
| **Data Read**         | 19.062 KB                      |
| **Data Written**      | 16.328 KB                      |
| **Files Written**     | 1                              |
| **Copy Duration**     | 14 seconds                     |
| **Throughput**        | 6.354 KB/s                     |
| **Parallel Copies**   | 1                              |
| **Start Time**        | 4/28/2026, 12:34:17 PM         |

### 🖼️ Pipeline 1 Screenshot
<img width="1506" height="881" alt="Postgre_ADLS_Silver" src="https://github.com/user-attachments/assets/140222d7-d7a2-4d62-acdf-9fddc5ae44b8" />

---

## 📌 Pipeline 2 — Postgre_SilverLake_GoldLake (Data Flow Transformation)

**Pipeline:** `Postgre_SilverLake_GoldLake`
**Data Flow Status:** ✅ Success
**Cluster Startup Time:** 2m 26s
**Number of Transformations:** 4

### 🔁 Data Flow Steps
### ⚙️ Transformation Details

| Step               | Type            | Purpose                                    |
|--------------------|-----------------|--------------------------------------------|
| `sourceSilverLake` | Source          | Read data from ADLS Gen2 Silver Layer      |
| `EditDateColumns`  | Derived Column  | Standardize date formats for analytics     |
| `PurchaseColumn`   | Derived Column  | Apply business rules on purchase columns   |
| `sinkToGold`       | Sink            | Load clean data to Gold Layer              |

### 🖼️ Pipeline 2 Screenshot
<img width="1443" height="403" alt="Postgre_SilverLake_GoldLake" src="https://github.com/user-attachments/assets/3baf9fc4-e5b9-427b-a09f-cb7f008fe48d" />

---

## 📌 Pipeline 3 — ADLS Gen2 Gold to Azure SQL Database (Final Load)

| Property              | Value                        |
|-----------------------|------------------------------|
| **Source**            | Azure Data Lake Storage Gen2 |
| **Sink**              | Azure SQL Database           |
| **Region**            | East Asia                    |
| **Status**            | ✅ Succeeded                 |
| **Files Read**        | 1                            |
| **Rows Read**         | 100                          |
| **Rows Written**      | 100                          |
| **Data Read**         | 11.74 KB                     |
| **Data Written**      | 21.862 KB                    |
| **Copy Duration**     | 14 seconds                   |
| **Throughput**        | 2.935 KB/s                   |
| **DIUs Used**         | 4                            |
| **Start Time**        | 4/28/2026, 4:24:07 PM        |

### 🖼️ Pipeline 3 Screenshot
<img width="1457" height="876" alt="PGGold_AzureSQL" src="https://github.com/user-attachments/assets/10f45927-96ee-4149-966f-a361bd0e6438" />

---

## 🏆 Project 2 — Pipeline Summary

| Pipeline | Source              | Sink                 | Rows | Duration | Status |
|----------|--------------------|-----------------------|------|----------|--------|
| 1        | PostgreSQL          | ADLS Gen2 (Bronze)   | 100  | 14 sec   | ✅     |
| 2        | ADLS Gen2 (Silver)  | ADLS Gen2 (Gold)     | 100  | 2m 26s   | ✅     |
| 3        | ADLS Gen2 (Gold)    | Azure SQL Database   | 100  | 14 sec   | ✅     |

---
---

# 🛠️ Tech Stack (Both Projects)

- **Azure Data Factory** — Pipeline orchestration & monitoring
- **MySQL** — Relational source (Project 1)
- **PostgreSQL** — Relational source (Project 2)
- **Azure Data Lake Storage Gen2** — Bronze, Silver & Gold layers
- **ADF Mapping Data Flow** — Visual ETL transformation engine
- **Azure SQL Database** — Gold layer destination (Both Projects)
- **Azure Copy Activity** — Efficient data movement
- **Medallion Architecture** — Bronze → Silver → Gold pattern

---

# 📊 What This Demonstrates

- ✅ End-to-end **cloud data pipelines** on Azure
- ✅ **Medallion Architecture** (Bronze → Silver → Gold)
- ✅ **Multi-source ingestion** — MySQL & PostgreSQL
- ✅ **Data cleansing & transformation** using ADF Data Flows
- ✅ **Date formatting & business logic** application
- ✅ Real-world **pipeline execution metrics**
- ✅ Zero data loss — 100 rows in = 100 rows out

---

# 📁 Repository Structure
# 👨‍💻 Author

**Vishal Kumar Gatla**
Data Engineer | Azure Data Factory | MySQL | PostgreSQL | Medallion Architecture
