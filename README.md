# 📊 Southern California Economic Indicators Data Pipeline

> An automated end-to-end ETL pipeline for collecting, transforming, storing, and analyzing regional economic indicators from the U.S. Bureau of Labor Statistics (BLS).

---

## 📖 Project Overview

The **Southern California Economic Indicators Data Pipeline** is an end-to-end **ETL (Extract, Transform, Load)** system designed to automate the collection of regional macroeconomic data.

The pipeline focuses primarily on **Orange County** and selected areas of **Los Angeles**, using data retrieved directly from the **Bureau of Labor Statistics (BLS) API**.

The system automatically:

- 🔎 **Extracts** economic data from the BLS API
- 🧹 **Transforms** and cleans raw API responses
- 🗄️ **Loads** processed data into MariaDB/MySQL
- 📊 **Prepares** data for business intelligence and economic forecasting
- 🔄 **Updates** existing records without creating duplicates

### 🎯 Business Objective

The primary objective is to eliminate the **manual data-gathering bottleneck**.

Using the **Theory of Constraints (TOC)** framework, this project focuses on improving the throughput of the most restrictive part of the workflow: **manual data collection and spreadsheet management**.

Instead of repeatedly:

`Download → Copy → Paste → Clean → Format → Update Excel`

the pipeline automates the process:

`BLS API → Python ETL → SQL Database → BI Dashboard`

This allows analysts to spend more time on higher-value activities such as:

- 📈 Economic forecasting
- 🔮 Scenario analysis
- 🧠 Business strategy

---

# 🏗️ Data Architecture & Flow

The pipeline follows a modern ETL architecture:


