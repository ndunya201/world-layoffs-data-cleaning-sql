# World Layoffs Data Cleaning with SQL

![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-025E8C?style=for-the-badge)
![Data Cleaning](https://img.shields.io/badge/Data-Cleaning-success?style=for-the-badge)
![GitHub](https://img.shields.io/badge/Portfolio-Project-blue?style=for-the-badge)

---

##  Project Overview

This project demonstrates an end-to-end SQL data cleaning workflow using a real-world global layoffs dataset.

The objective was to improve data quality by removing duplicate records, standardizing inconsistent values, handling missing data, and preparing the dataset for exploratory data analysis.

---

##  Objectives

- Create a staging table
- Remove duplicate records
- Standardize text values
- Convert date formats
- Handle missing values
- Remove unnecessary records
- Produce an analysis-ready dataset

---

##  Technologies Used

- MySQL
- SQL
- Git
- GitHub

---

##  Dataset

The dataset contains worldwide company layoffs including:

- Company
- Industry
- Country
- Location
- Date
- Total Laid Off
- Percentage Laid Off
- Funding Raised
- Company Stage

---

##  Data Cleaning Steps

### 1. Create a staging table

Copied the raw dataset into a staging table to preserve the original data.

---

### 2. Remove duplicate records

Used `ROW_NUMBER()` to identify duplicate rows before deleting them.

#### Handling Duplicate Removal (CTE Limitation in MySQL)

During the data cleaning process, duplicates were identified using a `ROW_NUMBER()` window function within a CTE.

However, MySQL does not allow direct deletion from a CTE. To resolve this limitation, a secondary staging table (`layoffs_staging2`) was created, which included the computed `row_num` column.

Duplicates were then removed by deleting rows where `row_num > 1`.

---

### 3. Standardize the data

- Trimmed company names
- Standardized industries
- Corrected country names
- Converted dates into SQL DATE format

---

### 4. Handle missing values

- Converted blank values to NULL
- Populated missing industries using self joins
- Removed rows with insufficient information

---

### 5. Final cleanup

Removed helper columns used during cleaning.

---

##  Project Structure

```text
world-layoffs-data-cleaning-sql
│
├── data
├── sql
├── screenshots
└── README.md
```

---

## 📷 Screenshots

### Raw Dataset

<img width="833" height="505" alt="image" src="https://github.com/user-attachments/assets/57a6aab6-8aba-4e91-b571-c83026282f51" />

---

### Duplicate Removal

<img width="936" height="560" alt="image" src="https://github.com/user-attachments/assets/d347ca73-9cad-4208-8beb-27779199f040" />

---

### Final Cleaned Dataset

<img width="892" height="654" alt="image" src="https://github.com/user-attachments/assets/686336a9-91d9-4130-80eb-5d170377c5dd" />


---

## 🚀 Skills Demonstrated

- SQL
- MySQL
- Data Cleaning
- Window Functions
- CTEs
- Joins
- Data Transformation
- Data Validation
- Database Management
