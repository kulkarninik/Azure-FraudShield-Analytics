# Azure-FraudShield-Analytics
# 🛡️ FraudShield - Real-Time Fraud Detection Analytics

![Azure](https://img.shields.io/badge/Azure-0078D4?style=for-the-badge&logo=microsoft-azure&logoColor=white)
![Databricks](https://img.shields.io/badge/Databricks-FF3621?style=for-the-badge&logo=databricks&logoColor=white)
![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Apache Spark](https://img.shields.io/badge/Apache_Spark-E25A1C?style=for-the-badge&logo=apachespark&logoColor=white)

An end-to-end **fraud detection analytics platform** built on Azure cloud, processing financial transactions through a medallion data architecture and delivering real-time insights via interactive Power BI dashboards.

---

## 📊 **Project Overview**

FraudShield is a complete data engineering and business intelligence solution that demonstrates:

- **Data Pipeline Development** using Azure Databricks and PySpark
- **Medallion Architecture** (Bronze-Silver-Gold layers)
- **Delta Lake** for ACID transactions and data versioning
- **Real-time Analytics** with Power BI DirectQuery
- **Cloud Infrastructure** on Microsoft Azure

### **Key Achievements**
- 📈 Processed **20,000+ transactions** with fraud detection
- 🎯 Achieved **15% fraud detection rate**
- 💰 Identified **$2M+** in potential fraudulent activity
- 📊 Built **5 interactive dashboards** with 40+ visualizations
- ⚡ **<2 minute** end-to-end pipeline execution

## 🏗️ **Architecture**
<img width="464" height="296" alt="image" src="https://github.com/user-attachments/assets/2ae1317a-e10c-4a89-acf2-98ec622052a0" />


### **Medallion Architecture**

| Layer | Purpose | Transformations |
|-------|---------|----------------|
| **🥉 Bronze** | Raw data ingestion | None (source of truth) |
| **🥈 Silver** | Cleansed & validated | Deduplication, quality checks, feature engineering |
| **🥇 Gold** | Business aggregations | Metrics by merchant, country, customer risk profiling |

---

## 🛠️ **Technology Stack**

### **Cloud & Infrastructure**
- **Microsoft Azure** - Cloud platform
- **Azure Data Lake Gen2** - Scalable storage
- **Azure Databricks** - Data processing engine

### **Data Engineering**
- **Apache Spark (PySpark)** - Distributed computing
- **Delta Lake** - ACID transactions, time travel
- **SQL** - Data querying

### **Business Intelligence**
- **Power BI Desktop** - Dashboard development
- **DAX** - Calculated measures
- **DirectQuery** - Real-time connectivity

### **Development Tools**
- **Python** - Data generation, transformations
- **Git** - Version control
- **Databricks Notebooks** - Interactive development

---

## 📁 **Project Structure**
<img width="484" height="291" alt="image" src="https://github.com/user-attachments/assets/29024bc6-a9b4-4753-95fc-0fb99224451f" />

---

## 🚀 **Features**

### **Data Pipeline**
✅ Automated data generation with realistic fraud patterns  
✅ Multi-layer processing (Bronze-Silver-Gold)  
✅ Data quality validation and cleansing  
✅ Feature engineering (18+ derived features)  
✅ ACID-compliant Delta Lake storage  

### **Fraud Detection**
✅ Rule-based fraud scoring (0-100 scale)  
✅ Multi-factor risk assessment  
✅ Customer risk profiling (Critical/High/Medium/Low)  
✅ Geographic fraud hotspot identification  
✅ Merchant category risk analysis  

### **Analytics & Dashboards**
✅ **Executive Summary** - High-level KPIs and trends  
✅ **Fraud Deep Dive** - Detailed pattern analysis  
✅ **High-Risk Customers** - Customer profiling and alerts  
✅ **Geographic Analysis** - Location-based insights  
✅ **Performance Monitoring** - System metrics  

---

## 📊 **Dashboard Preview**

### Page 1: Executive Summary
![Executive Dashboard](docs/dashboard_screenshots/page1_executive_summary.png)

### Page 3: High-Risk Customers
![Customer Analysis](docs/dashboard_screenshots/page3_high_risk_customers.png)

> *Add your screenshots to `docs/dashboard_screenshots/` folder*

---

## 🎯 **Key Metrics**

| Metric | Value | Description |
|--------|-------|-------------|
| **Total Transactions** | 20,000 | Synthetic transaction dataset |
| **Fraud Detection Rate** | 15.2% | Percentage of fraudulent transactions |
| **High-Risk Customers** | 847 | Customers with fraud history |
| **Amount at Risk** | $2.1M | Total value of flagged transactions |
| **Processing Time** | <2 min | End-to-end pipeline execution |
| **Dashboard Pages** | 5 | Interactive Power BI pages |
| **Visualizations** | 40+ | Charts, tables, KPIs |

---

## ⚙️ **Setup & Installation**

### **Prerequisites**
- Azure subscription (free tier works)
- Power BI Desktop
- Basic knowledge of Azure, SQL, Python

### **Quick Start**

1. **Clone the repository**
```bash
git clone https://github.com/yourusername/Azure-FraudShield-Analytics.git
cd Azure-FraudShield-Analytics

2. **Deploy Azure resources**
# Create Resource Group
az group create --name rg-fraudshield-prod --location eastus

# Create Storage Account
az storage account create \
  --name dlfraudshieldprod \
  --resource-group rg-fraudshield-prod \
  --location eastus \
  --sku Standard_LRS \
  --enable-hierarchical-namespace true

# Create Databricks Workspace
az databricks workspace create \
  --name dbw-fraudshield-prod \
  --resource-group rg-fraudshield-prod \
  --location eastus \
  --sku premium
3. **Import Databricks notebooks**
Upload notebooks from databricks_notebooks/ folder
Update configuration in 0_Config.py with your storage account key
Run notebooks in sequence: 0 → 1 → 2 → 3
4. **Open Power BI Dashboard**
Open powerbi/FraudShield_Dashboard.pbix
Update data source connection to your Databricks cluster
Refresh data
📖 Detailed setup guide: docs/setup_guide.md

🎓 Learning Outcomes
By exploring this project, you'll understand:

✅ How to design and implement medallion architecture
✅ Working with Delta Lake for data reliability
✅ PySpark transformations and aggregations
✅ Data quality and validation techniques
✅ Building interactive Power BI dashboards
✅ Azure cloud resource management
✅ End-to-end data pipeline orchestration
📈 Data Flow
text

1️⃣ DATA GENERATION
   ↓ Generate 20K transactions with fraud indicators
   
2️⃣ BRONZE LAYER
   ↓ Raw ingestion → Delta Lake
   
3️⃣ SILVER LAYER
   ↓ Cleanse → Validate → Engineer Features
   
4️⃣ GOLD LAYER
   ↓ Aggregate by Merchant, Country, Customer
   
5️⃣ POWER BI
   ↓ DirectQuery → Interactive Dashboards
🔍 Fraud Detection Rules
The system evaluates transactions using 6 fraud indicators:

High-Risk Merchants (+25 points)

Crypto exchanges, Gambling, Wire transfers
Amount Anomalies (+30 points)

Transactions > $3,000 or < $5
Geographic Risk (+20 points)

High-risk countries (Nigeria, China, etc.)
Temporal Patterns (+15 points)

Late-night transactions (11 PM - 4 AM)
New Account Risk (+20 points)

Accounts < 90 days old with high amounts
Transaction Velocity (+15 points)

Multiple transactions in 24 hours
Fraud Score: 0-100 (>50 = Flagged as fraud)

🔮 Future Enhancements
 Add Machine Learning model (Random Forest, XGBoost)
 Implement real-time streaming with Azure Event Hubs
 Add Azure Data Factory orchestration
 Integrate MLflow for model tracking
 Deploy REST API for real-time scoring
 Add automated alerts via Azure Functions
 Implement incremental loading with watermarks
📝 Sample Code
Bronze to Silver Transformation (PySpark)
Python

from pyspark.sql.functions import *

# Read Bronze layer
bronze_df = spark.read.format("delta").load(bronze_path)

# Apply transformations
silver_df = (bronze_df
    .filter(col("amount") > 0)
    .dropDuplicates(["transaction_id"])
    .withColumn("transaction_date", to_date("timestamp"))
    .withColumn("is_weekend", when(dayofweek("timestamp").isin(1, 7), 1).otherwise(0))
    .withColumn("risk_category",
        when(col("fraud_score") >= 70, "High")
        .when(col("fraud_score") >= 40, "Medium")
        .otherwise("Low")
    )
)

# Save to Silver layer
silver_df.write.format("delta").mode("overwrite").save(silver_path)
Power BI DAX Measure
dax

Fraud Rate % = 
DIVIDE(
    SUM(fraud_dashboard[fraud_count]),
    SUM(fraud_dashboard[total_transactions]),
    0
) * 100
🤝 Contributing
Contributions are welcome! Feel free to:

Report bugs
Suggest features
Submit pull requests
Improve documentation
📧 Contact
Your Name
📧 Email: your.email@example.com
💼 LinkedIn: linkedin.com/in/yourprofile
🌐 Portfolio: yourportfolio.com

📄 License
This project is licensed under the MIT License - see the LICENSE file for details.

🙏 Acknowledgments
Microsoft Azure Documentation
Databricks Community Edition
Power BI Community
Delta Lake Open Source Project
⭐ Show Your Support
If this project helped you learn or build something cool, please give it a ⭐!

Built with ❤️ using Azure, Databricks, and Power BI

text


---

## 📝 **Additional Files to Create**

### **1. LICENSE File**

Create `LICENSE` file:
MIT License

Copyright (c) 2024 [Your Name]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

text


---

### **2. .gitignore File**

Create `.gitignore`:
Power BI
*.pbix.tmp
*.pbix.backup

Python
pycache/
*.py[cod]
*$py.class
*.so
.Python
env/
venv/

Databricks
.databricks/

Secrets
*.key
*.secret
config.json
secrets.yml

OS
.DS_Store
Thumbs.db

IDE
.vscode/
.idea/
*.swp
*.swo

Azure
*.publishsettings

text


---

### **3. docs/setup_guide.md** (Brief)

```markdown
# Setup Guide

## Azure Resources

1. **Resource Group:** rg-fraudshield-prod-eastus
2. **Storage Account:** dlfraudshieldprod
3. **Databricks Workspace:** dbw-fraudshield-prod

## Steps

1. Create Azure resources (see main README)
2. Create 3 containers: bronze, silver, gold
3. Import Databricks notebooks
4. Update `0_Config.py` with your storage key
5. Run notebooks: 0 → 1 → 2 → 3
6. Connect Power BI to Databricks
7. Refresh dashboard

**Detailed instructions:** See main documentation
📂 Folder Structure to Create
text

Your-Local-Folder/
├── databricks_notebooks/
│   ├── 0_Config.py
│   ├── 1_Generate_Data.py
│   ├── 2_Silver_Transformation.py
│   └── 3_Gold_Analytics.py
│
├── powerbi/
│   ├── FraudShield_Dashboard.pbix
│   └── DAX_Measures.txt
│
├── docs/
│   ├── dashboard_screenshots/
│   │   ├── page1_executive_summary.png
│   │   ├── page2_fraud_deepdive.png
│   │   ├── page3_high_risk_customers.png
│   │   ├── page4_geographic.png
│   │   └── page5_performance.png
│   ├── architecture_diagram.png
│   └── setup_guide.md
│
├── .gitignore
├── LICENSE
└── README.md
🚀 Publishing to GitHub
Commands:
Bash

# Initialize Git
git init

# Add all files
git add .

# Commit
git commit -m "Initial commit: FraudShield Analytics Platform"

# Create repository on GitHub (via website)
# Then link and push:
git remote add origin https://github.com/yourusername/Azure-FraudShield-Analytics.git
git branch -M main
git push -u origin main
✅ Before Publishing Checklist
 Replace [Your Name] with your actual name
 Replace your.email@example.com with your email
 Replace yourusername with your GitHub username
 Add screenshots to docs/dashboard_screenshots/
 Export Databricks notebooks as .py files
 Save Power BI file (without sensitive data)
 Remove any secrets/keys from code
 Test all links in README
