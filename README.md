# MySQL ETL Data Pipeline

## 📌 Project Overview
This project demonstrates an end-to-end **ETL (Extract, Transform, Load) pipeline** for handling e-commerce data. The pipeline extracts data from CSV files, processes it using **Python (Pandas, SQLAlchemy, MySQL Connector)**, and loads it into a MySQL relational database.

## 🚀 Key Features
- **Extract**: Read data from Excel/CSV files.
- **Transform**: Handle missing values, format inconsistencies, and enforce schema integrity.
- **Load**: Insert cleaned data into MySQL tables.
- **Analyze**: Perform SQL queries for business insights.

## 🛠️ Tech Stack
- **Python**: Pandas, SQLAlchemy, MySQL Connector
- **MySQL**: Database Management System
- **Matplotlib & Seaborn**: Data Visualization

---

## 📂 Data Processing Steps

### 1️⃣ Extract Data
- Source: `Data for ETL Assignment.xlsx`
- Tables: `Customers`, `Products`, `Orders`, `Payments`

### 2️⃣ Transform Data
- **Customers Table**
  - Converted `created_at` column to `datetime` format.
  - Cleaned `phone_number` format (removing special characters).

- **Products Table**
  - Handled missing values.
  - Verified data types for consistency.

- **Orders Table**
  - Checked for missing values.
  - Ensured `customer_id` integrity.

- **Payments Table**
  - Ensured `order_id` references valid `Orders`.
  - Converted `payment_date` to `datetime` format.

### 3️⃣ Load Data into MySQL
- Created **four relational tables** in MySQL:
  - `Customers (customer_id PRIMARY KEY)`
  - `Products (product_id PRIMARY KEY)`
  - `Orders (order_id PRIMARY KEY, customer_id FOREIGN KEY)`
  - `Payments (payment_id PRIMARY KEY, order_id FOREIGN KEY)`
- Loaded data using bulk inserts & SQL scripts.

### 4️⃣ Data Validation & Queries
- Checked referential integrity between tables.
- Ran analytical SQL queries:
  - Total orders per customer
  - Revenue analysis
  - Popular product categories
  - Unpaid orders detection

---

## 📊 Exploratory Data Analysis
✅ **Visualized trends** in sales, revenue, and customer behavior.  
✅ **Identified outliers** and patterns using `matplotlib` and `seaborn`.  
✅ **Correlated key metrics** like order frequency and payment success rates.

---

## 🏆 SQL Analysis Highlights
### Basic Queries
- Retrieve all customer details.
- List orders with total amounts & status.

### Intermediate Queries (Joins & Aggregations)
- Total orders placed by each customer.
- Completed payments & associated order details.

### Advanced Queries
- Top 5 customers by spending.
- Identify orders without successful payments.
- Calculate Average Order Value (AOV).

---

## 📜 How to Run
1️⃣ **Install Dependencies**
```bash
pip install pandas mysql-connector-python sqlalchemy matplotlib seaborn
```

2️⃣ **Set Up MySQL Database**
- Create a database (`ecommerce_db`).
- Execute `schema.sql` to set up tables.

3️⃣ **Run ETL Pipeline**
```bash
python etl_pipeline.py
```

4️⃣ **Execute SQL Queries**
- Open MySQL Workbench.
- Run `analysis_queries.sql` for insights.

---

## 🎯 Future Enhancements
- Automate ETL with Apache Airflow.
- Implement data validation rules.
- Optimize query performance with indexing.

---
