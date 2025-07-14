# Databricks Assignmnet
---

## Question 1: CSV ETL Pipeline

- **source_to_bronze/**
  - Loads raw CSV files (Employee, Department, Country)
  - Saves them to DBFS path `/df_write` as CSV

- **bronze_to_silver/**
  - Reads data using custom schema
  - Converts column names to snake_case
  - Adds `load_date`
  - Saves as Delta table to `/silver/Employee_info/dim_employee`

- **silver_to_gold/**
  - Reads silver Delta table and performs:
    - Total salary per department
    - Employee count by department and country
    - Department-country mapping
    - Average age per department
  - Adds `at_load_date`
  - Saves to `/gold/employee/` as Delta tables


## Question 2: API Data Ingestion

- Fetches user data from `https://reqres.in/api/users?page=n`
- Flattens JSON response
- Adds `site_address` and `load_date`
- Saves as Delta table to `/site_info/person_info`


