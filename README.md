# 🤖 AI Automation Pipeline using n8n, Supabase & Quadratic

This project demonstrates an end-to-end AI-powered data automation workflow that:

1. **Fetches data automatically from Gmail (as CSV attachments)**  
2. **Ingests the data into a PostgreSQL database hosted on Supabase**  
3. **Connects to the PostgreSQL database via Quadratic for spreadsheet-style analysis**

---

## 🔧 Tools Used

| Tool        | Purpose                                  |
|-------------|------------------------------------------|
| [n8n](https://n8n.io/)         | No-code automation platform for building workflows |
| [Supabase](https://supabase.com/) | Cloud-hosted PostgreSQL + API backend           |
| [Quadratic](https://quadratichq.com/) | AI-powered spreadsheet for querying databases   |

---

## 📸 Project Overview

### 📍 Step 1: Automated Workflow in n8n

- Connects to a Gmail account.
- Monitors incoming emails for specific CSV attachments (e.g., sales reports, user data).
- Extracts the CSV content from the email.
- Parses and inserts the data into a Supabase PostgreSQL table using an HTTP or PostgreSQL node.

> 📷 _visual of the n8n workflow_

![Screenshot 2025-06-15 031054](https://github.com/user-attachments/assets/8795a6e1-5090-46c5-9b66-b62b06ba38d5)

---

### 📍 Step 2: PostgreSQL Setup via Supabase

- A Supabase project was created to host the database.
- The table schema matches the incoming CSV structure (e.g., columns for date, sales, product, etc.).
- n8n sends data into the Supabase DB in real time or on a schedule.

> 📷 _Supabase UI and table_

![Screenshot 2025-06-15 031137](https://github.com/user-attachments/assets/04b5be0d-d258-4396-96e9-414181ff3631)

---

### 📍 Step 3: Data Analysis in Quadratic AI

- Quadratic connects directly to the Supabase PostgreSQL instance via connection credentials.
- Queries are written in the spreadsheet or using AI to summarize, visualize, and clean the data.
- Acts as an AI-augmented BI layer for analysis.

> 📷 _Quadratic interface_

![Screenshot 2025-06-15 031252](https://github.com/user-attachments/assets/dd61513b-9add-425d-bc4e-6f0cb073c538)

---

## 🚀 How to Run This Project

### 🔹 1. Set Up Supabase PostgreSQL
- Create a free [Supabase](https://supabase.com/) account.
- Create a new project and note your DB credentials.
- Use the SQL Editor to create your table structure based on your CSV format.

```sql
CREATE TABLE sales_data (
  id SERIAL PRIMARY KEY,
  date DATE,
  product TEXT,
  quantity INTEGER,
  price NUMERIC
);
````

---

### 🔹 2. Build the n8n Workflow

* Host n8n locally or on cloud ([setup guide](https://docs.n8n.io/hosting/overview/))
* Create a new workflow:

  * Gmail node → download CSV attachments
  * CSV node → parse
  * PostgreSQL node or HTTP node → insert data into Supabase
* Test the workflow manually or automate via triggers (e.g., new email)

---

### 🔹 3. Connect Quadratic to Supabase

* Go to [Quadratic](https://quadratichq.com/)
* Add a database connection (host, db name, user, password, port)
* Start writing queries or use the AI features to explore your dataset
* You can generate visualizations or pivot-style tables from your live data

---

## 📦 Folder Structure

```
📦 ai-automation-pipeline
├── 📁 assets/
│   ├── n8n_workflow.png
│   ├── supabase_view.png
│   └── quadratic_analysis.png
│
├── 📁 sql/
│   └── create_sales_table.sql         # SQL schema for Supabase
│
├── 📁 docs/
│   └── workflow_overview.md           # In-depth explanation of workflow
│
├── 📁 n8n/
│   └── n8n_workflow.json              # Exported workflow file from n8n
│
├── 📁 quadratic/
│   └── sample_queries.md              # Some sample analysis queries
│
├── .gitignore
├── README.md
└── LICENSE


📄 README.md
```

---

## 🌐 Use Cases

* Marketing teams auto-analyzing campaign data from email exports
* Sales teams ingesting periodic reports into a cloud DB for live analytics
* Any process that turns manual CSV handling into a smart pipeline
* Auto-analysis of daily/weekly sales reports from vendors
* Data aggregation from multiple departments via email
* AI-powered dashboards without needing Excel or BI tools
* Ideal for startups, analysts, or marketers needing hands-free reporting

---

## 🙌 Credits

* Built using [n8n](https://n8n.io), [Supabase](https://supabase.com), and [Quadratic](https://quadratichq.com)
* Author: **John David**

---

## 📬 Contact

For issues, suggestions or collaborations, open an issue or contact me via [LinkedIn](https://www.linkedin.com/in/yourprofile/).
