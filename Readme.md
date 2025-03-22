
# Distributed Analysis of Automotive Businesses Using Yelp Data 🚗📊

This project leverages **Apache Spark**, **PySpark**, and **Hadoop** to perform scalable analysis of the **Yelp dataset**, focusing on the **automotive business category** in **Arizona**. It extracts insights about **business performance, customer sentiment, review trends**, and **user behavior** using distributed processing techniques.

---

## 🔧 Tech Stack

- **Apache Spark 3.1.1** + **Hadoop 3.2**
- **PySpark** on **Google Colab**
- **Spark SQL** for querying
- **Matplotlib** and **Seaborn** for visualizations
- **Google Drive** for data storage

---

## 🚀 Colab Setup Instructions

```python
# Set up Java and Spark
apt-get update
apt-get install openjdk-8-jdk-headless -qq > /dev/null
wget -q http://archive.apache.org/dist/spark/spark-3.1.1/spark-3.1.1-bin-hadoop3.2.tgz
tar xf spark-3.1.1-bin-hadoop3.2.tgz
pip install -q findspark
```

```python
# Mount Google Drive
from google.colab import drive
drive.mount('/content/gdrive')

# Set environment variables
import os
os.environ["JAVA_HOME"] = "/usr/lib/jvm/java-8-openjdk-amd64"
os.environ["SPARK_HOME"] = "/content/spark-3.1.1-bin-hadoop3.2"
DATASET_PATH = "/content/gdrive/MyDrive/Sem 3/DPS/Project/Milestone2/yelp_dataset"

# Initialize Spark
import findspark
findspark.init()

from pyspark.sql import SparkSession
spark = SparkSession.builder.appName("YelpDataAnalysis").getOrCreate()
```

---

## 📁 Dataset

The project uses the [Yelp Open Dataset](https://www.yelp.com/dataset), which includes:
- Business data
- User data
- Reviews and Tips

The dataset is **transformed from JSON to Parquet** format for optimized query performance.

---

## 📊 Analysis Overview

### 📍 Milestone 1: Business-Level Analysis

- **City Ratings**: Highest average ratings in Oro Valley and Tucson.
- **Review Trends**: Increasing monthly review count indicates rising engagement.
- **Service Ratings**: Highest satisfaction in "Home Window Tinting" and "Transmission Repair".
- **Sentiment Over Time**: Positive sentiment dominates throughout.
- **Business Hours**: Noon-opening businesses receive the best average ratings.

### 👥 Milestone 2: User-Level Analysis

- **Review Activity Distribution**: Majority of users wrote 1–10 reviews.
- **Most Reviewed Businesses**: Discount Tire, QuickTrip, Mister Car Wash.
- **Sentiment by User**: John, Michael, and David lead in positive reviews.
- **Engagement Metrics**:
  - Most **Funny Votes**: John
  - Most **Useful Votes**: John
  - Most **Compliments and Tips**: John
- **Monthly Activity Trends**: Peak in January, dip in November.

---

## ✅ Key Learnings

- Efficiently transformed and processed large-scale data using **distributed systems**.
- Gained insights into **customer satisfaction** and **user engagement** in the automotive service sector.
- Demonstrated value of **visual storytelling** using data visualizations.

---

## 📌 Future Work

- Extend analysis to other business categories and geographies.
- Incorporate ML-based sentiment scoring for deeper review analysis.
- Deploy dashboards for real-time data exploration.

---

## 📎 Project Reports

- [Milestone 1 Report – Business Analysis](./1229582226_Project_Milestone_1_report.pdf)
- [Milestone 2 Report – User Analysis](./1229582226_Project_Milestone_2_report.pdf)