# 🧼 Layoffs Data Cleaning & Analysis (MYSQL Project)

This project focuses on cleaning and analyzing a real-world dataset of global tech and non-tech layoffs from **2023 to March 2025**. The original dataset was sourced from [Kaggle](https://www.kaggle.com/datasets/happyude/world-layoffs?select=layoffs.csv) and contains raw records with inconsistencies, missing values, and formatting issues.

---

## 🧾 Dataset Overview

The original dataset contains the following columns:

- `company`: Company name
- `location`: Office location(s)
- `industry`: Industry sector
- `total_laid_off`: Number of employees laid off
- `percentage_laid_off`: Proportion of total workforce affected
- `stage`: Company growth stage (e.g., Seed, Series A, IPO)
- `country`: Country of operation
- `funds_raised`: Total capital raised
- `date`: Layoff date (timestamp format)

---
## 📋 Data Quality Assessment (DQA)

Before data cleaning, I conducted a structured assessment to identify issues such as blanks, formatting inconsistencies, and unclean values. This process is documented in a tracker used to decide what can be fixed and what needs to be acknowledged.

👉 [View Data Cleaning Tracker (Google Sheets)][(https://your-link-here)](https://docs.google.com/spreadsheets/d/1NNZJWQno_U9dFFm1f18Wg5Pw5XtRt5RqfB-u9HJzqFo/edit?usp=sharing)

This tracker helps:
- Identify column-level issues
- Quantify affected rows and % impact
- Document resolutions or limitations
---

## 🧹 Data Cleaning Steps

Performed using MySQL to ensure data is structured and analysis-ready.

### 1. Duplicate Removal
- Used `ROW_NUMBER()` with `PARTITION BY` to identify and remove duplicate records.

### 2. Data Standardization
- Trimmed extra spaces from text fields.
- Cleaned `location` values to remove inconsistent formatting (e.g., `[‘City’, 'Non-U.S.']`).
- Converted `date` values from text to date `YYYY-MM-DD`.
- Rounded and cleaned `percentage_laid_off` values.

### 3. Handling Null & Blank Values
- Replaced empty `industry` with `'Other'`.
- Replaced missing `stage` with `'Unknown'`.
- Removed or NULL-ed invalid percentage values (e.g., `0%`).

### 4. Column Cleanup
- Removed intermediate columns used for transformation (`row_num`, raw `date`).

---

## 📊 Exploratory Data Analysis (EDA)

📈 Layoff Trends & Key Insights

After cleaning and exploring the data, I dug deeper to uncover what the numbers were saying. 
Here's a breakdown of the most notable patterns based on 1,288 layoff events recorded between 2020 and March 2025.

🔢 General Stats
- Total layoffs recorded: 440,030 employees
- Largest single layoff event: 15,000 people
- That means the average layoff per event is around 342 employees.
- These layoffs spanned various industries, countries, and company stages, with some clear patterns emerging.

📆 When Did Layoffs Peak?
- Layoffs hit their highest point in Q1 2023, with 167,574 employees laid off — that’s nearly 38% of the total dataset. 
- The second-largest spike occurred a year later, in Q1 2024, with 57,269 layoffs, representing ~13%.
- These two quarters alone account for over half of all layoffs recorded, likely reflecting major macroeconomic shifts, market corrections, or company-wide restructuring during those periods.

🏢 Companies with the Most Layoff Events
Some companies show a repeated pattern of downsizing.
The top 5 with multiple rounds of layoffs are:
- Google — 7 events
- Amazon and Microsoft — 6 events each
- Spotify and Cue Health — 5 events each
Even the biggest players weren’t spared — and some had to restructure more than once.

📊 Total Laid Off by Company
In terms of total employees affected:
- Amazon leads with over 17,500 layoffs, representing nearly 4% of the dataset.
- Microsoft, Meta, and Google follow, but with lower totals.

📍 Where Were the Layoffs Concentrated?
The San Francisco Bay Area saw the largest impact, with more than 145,000 layoffs — that’s roughly 33% of the global total. 
A clear indicator of how concentrated layoffs were in tech-heavy regions.

🏭 Industry Breakdown
Top 5 most-affected industries:
- Hardware
- Consumer
- Retail
- Transportation
- Finance
These five sectors alone make up over 60% of all layoffs — industries that are often heavily reliant on funding, scaling, and operational efficiency.

🌍 Country Breakdown
The United States accounts for more than 300,000 layoffs, or about 68% of the total. 
Layoffs in other countries are far lower in comparison, showing the U.S.'s central role in this trend, especially in tech.

🚀 Stage of Company
Companies in the post-IPO stage laid off the most employees, followed by those in later funding stages. 
At the other end, Series I startups saw the fewest layoffs, likely due to smaller team sizes and lower burn rates.

📝 TL;DR Summary
📌 1,288 events — 440K layoffs

🏆 Amazon laid off the most; Google had the most layoff rounds

🌁 SF Bay Area alone: 145K+ layoffs (33%)

🗓️ Q1 2023: 167K+ layoffs; Q1 2024: 57K+

🏭 Top sectors hit: Hardware, Consumer, Retail

🇺🇸 US accounts for 68% of global layoffs

💼 Post-IPO companies had the highest total layoffs

---

## 📂 Project Structure

- SQL script for data cleaning
- SQL script for exploratory data analysis
- `README.md` — Project documentation (this file)

---

## 🛠️ Tools Used

- **MySQL**
- SQL Window Functions (`ROW_NUMBER()`, `PARTITION BY`, `OVER`)
- Date manipulation, CTEs, and conditional logic

---

## 👨‍💻 Author

**Daniel Siregar**  


---
