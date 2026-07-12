# 🚀 Azure Customer Support Data Pipeline

An end-to-end ETL (Extract, Transform, Load) pipeline built using **Azure Data Factory (ADF)** and **Azure Data Lake Storage Gen2 (ADLS Gen2)** to process customer support ticket data. The pipeline filters resolved tickets, calculates resolution time, enriches records with agent information, and stores the transformed dataset in Azure Data Lake Storage.

---

## 📌 Project Overview

This project demonstrates how Azure Data Factory can be used to build a scalable data engineering pipeline.

The pipeline performs the following operations:

- Reads customer support ticket data from Azure Data Lake Storage Gen2.
- Filters only **Resolved** support tickets.
- Calculates **Resolution Minutes** using CreatedDate and ResolvedDate.
- Joins ticket data with the Agents dataset using **AgentID**.
- Selects only required business columns.
- Writes the transformed output back to Azure Data Lake Storage as a CSV file.

---

# 🏗 Architecture

```
                Azure Data Lake Storage Gen2
                        │
        ┌───────────────┴───────────────┐
        │                               │
   Tickets CSV                    Agents CSV
        │                               │
        └───────────────┬───────────────┘
                        │
              Azure Data Factory
                        │
                  Filter (Resolved)
                        │
              Derived Column
         (Resolution Minutes)
                        │
                Inner Join (AgentID)
                        │
                 Select Columns
                        │
                     Sink
                        │
        resolved_tickets.csv (ADLS Gen2)
```

---

# ⚙️ Technologies Used

- Microsoft Azure
- Azure Data Factory
- Azure Data Lake Storage Gen2
- Mapping Data Flow
- Data Pipeline
- CSV Files

---

# 🔄 Pipeline Workflow

### Source

- TicketsDay1 Dataset
- Agents Dataset

### Transformations

- Filter resolved tickets
- Calculate Resolution Minutes
- Join with Agents dataset
- Select required columns

### Sink

- Export processed data to Azure Data Lake Storage
- Output format: CSV

---

# 📂 Repository Structure

```
azure-customer-support-data-pipeline/
│
├── README.md
├── LICENSE
│
├── datasets/
│   ├── agents.csv
│   ├── tickets_day1.csv
│   └── tickets_day2.csv
│
├── output/
│   └── resolved_tickets.csv
│
├── screenshots/
│   ├── 01_ADLS_Storage.png
│   ├── 02_Datasets.png
│   ├── 03_DataFlow.png
│   ├── 04_Pipeline.png
│   ├── 05_Pipeline_Run.png
│   └── 06_Output.png
│
├── architecture/
   └── architecture.png

```

---

# 📥 Input Datasets

| Dataset | Description |
|----------|-------------|
| agents.csv | Support agent details |
| tickets_day1.csv | Customer support tickets (Day 1) |
| tickets_day2.csv | Customer support tickets (Day 2) |

---

# 📤 Output

```
resolved_tickets.csv
```

Output contains:

- AgentID
- AgentName
- Email
- TeamLead
- Department
- Role
- TicketID
- CustomerID
- Status
- ResolutionTime
- Priority
- Category
- CreatedDate
- ResolvedDate
- ResolutionMinutes

---

# ✨ Features

- End-to-End ETL Pipeline
- Azure Data Factory Mapping Data Flow
- Data Filtering
- Derived Column Transformation
- Inner Join
- Azure Data Lake Storage Integration
- Automated Data Pipeline
- CSV Export

---

# 📸 Screenshots

The repository includes screenshots of:

- Azure Data Lake Storage
- Datasets
- Data Flow
- Pipeline
- Pipeline Execution
- Final Output

---

# 🎯 Learning Outcomes

- Azure Data Factory
- Mapping Data Flows
- Azure Data Lake Storage Gen2
- Data Transformation
- Data Integration
- ETL Pipeline Development
- Cloud Data Engineering

---

# 👨‍💻 Author

**Rahul Kumar**

Computer Science Engineering Student

Aspiring Data Engineer

---

## ⭐ If you found this project useful, consider giving this repository a star.
