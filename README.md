# 🏨 Hotel Analytics Dashboard

## 📖 Project Overview
This project transforms raw and inconsistent hotel booking data into an interactive **Streamlit dashboard** hosted directly within **Snowflake**.  

By building a structured cloud-based data pipeline, the dashboard provides stakeholders with real-time insights into:

- Revenue performance
- Booking behavior
- Guest trends
- Geographic analytics

---

## ⚙️ Technical Architecture

The project follows a modern **Medallion Architecture** workflow:

1. **Raw Layer** → Initial ingestion of source files into Snowflake  
2. **Clean Layer** → Data cleaning, formatting, and null handling  
3. **Business Layer** → Analytics-ready datasets  
4. **Visualization Layer** → Interactive Streamlit dashboard using Python  

<p align="center">
  <img src="https://raw.githubusercontent.com/wisemansg/hotel_booking_analytics/main/assets/ARCHITECTURE%20DIAGRAM.jpeg" width="900"/>
</p>

---

## ⚡ Live Dashboard Features

✔️ Real-time dashboard updates  
✔️ Dynamic filtering by city, room type, and dates  
✔️ Interactive KPI monitoring  
✔️ Snowflake-hosted Streamlit application  
✔️ Business-ready visual analytics  

---

## 📊 Dashboard Overview

<p align="center">
  <img src="https://raw.githubusercontent.com/wisemansg/hotel_booking_analytics/main/assets/FULL%20DASHBOARD.png" width="950"/>
</p>

---

## 📈 Executive KPIs

| KPI | Value |
|---|---|
| Total Revenue | 577,347 |
| Total Bookings | 1,729 |
| Total Guests | 5,072 |
| Average Booking Value | 334.11 |

---

## 🔗 Live Application

👉 [Hotel Analytics Live Dashboard](https://app.snowflake.com/streamlit/sweden-central.azure/xf09284/#/apps/3ux4b4y5obk6caso6633)

---

## 🔍 Revenue & Booking Trends

### Monthly Revenue Trend

<p align="center">
  <img src="https://raw.githubusercontent.com/wisemansg/hotel_booking_analytics/main/assets/MONTHLY%20REVENUE%20TREND.png" width="850"/>
</p>

---

### Monthly Bookings Trend

<p align="center">
  <img src="https://raw.githubusercontent.com/wisemansg/hotel_booking_analytics/main/assets/MONTHLY%20BOOKINGS%20TREND.png" width="850"/>
</p>

---

## 🌍 City Performance Analysis

<p align="center">
  <img src="https://raw.githubusercontent.com/wisemansg/hotel_booking_analytics/main/assets/CITY%20PERFORMANCE%20BAR%20CHART.png" width="850"/>
</p>

---

## 🛏️ Booking Breakdown Analysis

### Room Type Distribution

<p align="center">
  <img src="https://raw.githubusercontent.com/wisemansg/hotel_booking_analytics/main/assets/BOOKING%20BREAKDOWN%20BY%20ROOM%20TYPE.png" width="850"/>
</p>

---

### Booking Status Distribution

<p align="center">
  <img src="https://raw.githubusercontent.com/wisemansg/hotel_booking_analytics/main/assets/BOOKING%20BREAKDOWN%20BY%20STATUS.png" width="850"/>
</p>

---

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| Snowflake | Cloud Data Platform |
| Streamlit | Frontend Dashboard |
| Python | Application Logic |
| SQL | Data Transformation |
| Pandas | Data Manipulation |

---

# 🚀 Real-Time Insurance Claims Data Pipeline

<p align="center">
  <img src="https://img.shields.io/badge/Snowflake-29B5E8?logo=snowflake&logoColor=white" />
  <img src="https://img.shields.io/badge/dbt-FF694B?logo=dbt&logoColor=white" />
  <img src="https://img.shields.io/badge/MongoDB-47A248?logo=mongodb&logoColor=white" />
  <img src="https://img.shields.io/badge/Airbyte-0097D8?logo=airbyte&logoColor=white" />
  <img src="https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/Power%20BI-F2C811?logo=powerbi&logoColor=black" />
</p>

---

## 📌 Project Overview

This project demonstrates a modern **real-time insurance claims data pipeline** built using cloud-native data engineering technologies.

The pipeline simulates live insurance claims data using Python, stores records in MongoDB, ingests data into Snowflake using Airbyte, transforms data with DBT, and visualizes insights in Power BI.

---

## 🏗️ Architecture Diagram

<p align="center">
  <img src="https://github.com/wisemansg/hotel_booking_analytics/blob/main/insurance/Project%20Pipeline.jpeg?raw=true" width="900"/>
</p>

---

## ⚙️ Tech Stack

| Technology | Purpose |
|---|---|
| MongoDB | NoSQL operational database |
| Airbyte | ELT data ingestion |
| Snowflake | Cloud data warehouse |
| DBT | Data transformations |
| Python | Data simulation |
| Power BI | Business intelligence |

---

## ✨ Key Features

✔️ Real-time insurance claims simulation  
✔️ MongoDB → Snowflake ELT workflow  
✔️ Automated Airbyte sync pipelines  
✔️ DBT transformation models  
✔️ Fraud analytics and reporting  
✔️ Interactive Power BI dashboards  

---

## 📂 Repository Structure

```bash
insurance-nosql-pipeline/
│
├── data-generator/
│   └── Simulator.py
│
├── ins_dbt/
│   └── models/
│       ├── claims_summary.sql
│       ├── source.yml
│       └── stg_claims.sql
│
└── README.md
```

---

## 🖼️ Project Screenshots

### MongoDB Collections

<p align="center">
  <img src="https://github.com/wisemansg/hotel_booking_analytics/blob/main/insurance/MongoDB.png?raw=true" width="850"/>
</p>

---

### Snowflake Warehouse

<p align="center">
  <img src="https://github.com/wisemansg/hotel_booking_analytics/blob/main/insurance/Snowflake.png?raw=true" width="850"/>
</p>

---

### Airbyte ELT Pipeline

<p align="center">
  <img src="https://github.com/wisemansg/hotel_booking_analytics/blob/main/insurance/Airflow.png?raw=true" width="850"/>
</p>

---

## 🚀 Getting Started

### 1️⃣ Clone Repository

```bash
git clone https://github.com/your-username/insurance-nosql-pipeline.git

cd insurance-nosql-pipeline
```

---

### 2️⃣ Install Dependencies

```bash
pip install faker pymongo
```

---

### 3️⃣ Configure MongoDB Atlas

Create:

- MongoDB Atlas cluster
- `insurance` database
- `customers` collection
- `claims` collection

---

### 4️⃣ Run Data Generator

```bash
python Simulator.py
```

---

## 🐍 Python Data Generator

```python
from faker import Faker
import random
import time
import pymongo

fake = Faker()

client = pymongo.MongoClient(
    "mongodb+srv://<username>:<password>@insurance.mongodb.net/"
)

db = client["insurance"]

customers_col = db["customers"]
claims_col = db["claims"]

while True:

    customer = {
        "customer_id": f"CUST-{random.randint(100,999)}",
        "name": fake.name(),
        "state": fake.state_abbr(),
        "policy_type": random.choice(
            ["Auto", "Home", "Health"]
        )
    }

    claim = {
        "claim_id": f"CLM-{random.randint(1000,9999)}",
        "customer_id": customer["customer_id"],
        "date": fake.date_between(
            start_date='-1y',
            end_date='today'
        ).isoformat(),
        "amount": round(
            random.uniform(100, 20000), 2
        ),
        "claim_type": random.choice(
            ["Accident", "Theft", "Fire"]
        ),
        "is_fraud": random.random() < 0.05
    }

    customers_col.insert_one(customer)
    claims_col.insert_one(claim)

    print(
        f"Inserted claim {claim['claim_id']} "
        f"for customer {customer['customer_id']}"
    )

    time.sleep(2)
```

---

## 🔄 Airbyte ELT Pipeline

1. Launch Airbyte locally using Docker  
2. Configure MongoDB source  
3. Configure Snowflake destination  
4. Create sync connection  
5. Schedule automatic ingestion jobs  

---

## ❄️ Snowflake Warehouse

Snowflake acts as the centralized analytics warehouse.

Example raw table:

```text
RAW.CLAIMS
```

---

## 🧱 DBT Transformations

### source.yml

```yaml
version: 2

sources:
  - name: snowflake
    database: insurance
    schema: raw

    tables:
      - name: CLAIMS
```

---

### stg_claims.sql

```sql
with raw as (

    select
        claim_id,
        customer_id,
        to_date(date) as claim_date,
        amount::float as amount,
        claim_type,
        is_fraud::boolean as is_fraud

    from {{ source('snowflake', 'CLAIMS') }}

)

select *
from raw
```

---

### claims_summary.sql

```sql
select
    date_trunc('month', claim_date) as month,
    claim_type,
    count(*) as claims_count,
    sum(amount) as total_amount,
    sum(
        case
            when is_fraud then 1
            else 0
        end
    ) as fraud_count

from {{ ref('stg_claims') }}

group by 1,2
order by 1
```

---

## 📊 Power BI Dashboard

Suggested analytics:

- Claims by month
- Fraud detection trends
- Claim type distribution
- Total claims amount
- Geographic claim analysis

---

## 📈 End-to-End Pipeline

```text
Python Simulator
        ↓
MongoDB Atlas
        ↓
Airbyte ELT
        ↓
Snowflake Warehouse
        ↓
DBT Transformations
        ↓
Power BI Dashboard
```

---

## ✅ Final Deliverables

✔️ Real-time insurance pipeline  
✔️ Cloud-based Snowflake warehouse  
✔️ Automated ELT workflows  
✔️ DBT transformation layer  
✔️ Interactive Power BI dashboard  

---

## 👨‍💻 Author

**Wiseman Siriro**  
Data Engineering • Cloud Analytics • Business Intelligence

---
