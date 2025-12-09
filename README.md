# 📊 Fitbit Wellness Case Study  
### Google Data Analytics Professional Certificate – Capstone Project  
**Ask → Prepare → Process → Analyze → Share → Act**

![Visitors](https://visitor-badge.laobi.icu/badge?page_id=abdullahahmadd.fitbit-wellness-case-study)
![R](https://img.shields.io/badge/Tool-R-blue?logo=r)
![SQL](https://img.shields.io/badge/Tool-MySQL-orange?logo=mysql)
![Excel](https://img.shields.io/badge/Tool-Excel-green?logo=microsoft-excel)
![License](https://img.shields.io/badge/License-CC0_1.0-lightgrey)
![Repo Size](https://img.shields.io/github/repo-size/abdullahahmadd/fitbit-wellness-case-study)
![Stars](https://img.shields.io/github/stars/abdullahahmadd/fitbit-wellness-case-study?style=social)

---

# 📑 Table of Contents  
- [📌 Project Overview](#-project-overview)  
- [🏁 Business Task](#-business-task)  
- [🧭 1 Ask Phase](#-1-ask-phase)  
- [📥 2 Prepare Phase](#-2-prepare-phase)  
- [🧹 3 Process Phase](#-3-process-phase)  
- [🗄️ 4 Analyze Phase](#️-4-analyze-phase)  
  - [A. SQL Analysis](#a-sql-analysis-mysql)  
  - [B. R Analysis](#b-r-analysis-rstudio)  
- [📤 5 Share Phase](#-5-share-phase)  
- [🚀 6 Act Phase](#-6-act-phase)  
- [📂 Repository Contents](#-repository-contents)  
- [🙌 Acknowledgments](#-acknowledgments)  
- [👤 Author](#-author)  

---

## 📌 Project Overview  
This case study explores smart-device usage data from Fitbit-style trackers to understand user behavior related to **daily activity, sleep, calories, intensity, and heart rate**.  
The goal is to uncover valuable patterns that help a wellness technology company (e.g., **Bellabeat**) optimize product strategy and marketing decisions.

This project follows the complete six-phase Google Data Analytics Framework and uses **Excel, MySQL, and RStudio** for data cleaning, processing, analysis, and visualization.

---

## 🏁 Business Task  
Bellabeat leadership wants insights on **how consumers use smart devices** to improve product design, user engagement, and marketing strategy.

### Key Questions:
1. What are the main trends in activity, sleep, calories, intensity, and heart rate among smart-device users?  
2. How do these trends relate to user behavior and healthy habits?  
3. How can these insights improve targeted marketing and device recommendations?

---

# 🧭 1. Ask Phase  
- Defined business problem  
- Identified stakeholders (Bellabeat executive team)  
- Clarified key questions  

---

# 📥 2. Prepare Phase  
### Tools Used: **Excel**

- Dataset: **Fitbit Fitness Tracker Data (Public Domain)**  
- Selected **7 CSV files** for analysis  
- Main issues discovered:  
  - Inconsistent date/time formats  
  - Missing sleep data  
  - Heart rate outliers  
  - Very large row counts (minute/second-level data)

### Actions Performed:  
- Imported raw datasets into Excel  
- Cleaned and standardized column names  
- Split datetime columns  
- Rounded numeric values  
- Removed invalid heart rate values  
- Created **one consolidated file**: `Tranformed_Fitbit_Dataset.xlsx`

---

# 🧹 3. Process Phase  
### Tools Used: **Excel**

- Addressed inconsistencies  
- Created new calculated fields:  
  - `day_of_week`  
  - `week_number`  
  - `sleep_hours`  
- Verified dataset integrity  
- Prepared final dataset for MySQL and RStudio

---

# 🗄️ 4. Analyze Phase  
### Tools Used: **MySQL Workbench & RStudio**

---

## 🔷 A. SQL Analysis (MySQL)  
SQL was used to:

- Create structured tables for each dataset  
- Import and clean all 7 sheets  
- Aggregate metrics:
  - daily sleep  
  - hourly → daily steps  
  - hourly → daily calories  
  - daily intensity  
  - heart rate summaries  
- Build a **Daily Master Table**  
- Generate insights on:
  - Activity patterns  
  - Sleep correlations  
  - Sedentary behavior  
  - Heart rate trends  
  - Most active users  
  - Activity by day of week  

📂 **SQL results and screenshots:**  
👉 [`Fitbit_analysis_results`](./Fitbit_analysis_results)

📄 **SQL Code File:**  
👉 [`fitbit_analysis.sql`](./fitbit_analysis.sql)

---

## 🔷 B. R Analysis (RStudio)  
RStudio was used to:

- Import transformed dataset  
- Clean and transform using `tidyverse` and `lubridate`  
- Aggregate:
  - daily steps  
  - sleep minutes  
  - daily heart rate  
  - daily calories  
  - intensity metrics  
- Generate **all visualizations**

📂 **R Project Folder:**  
👉 [`fitbit_analysis_R`](./fitbit_analysis_R)

### Visualizations Produced:
- Sleep Hours vs Daily Steps  
- Calories Burned vs Active Minutes  
- Average Heart Rate Trend  
- Steps by Hour of Day  
- Steps by Day of Week  

All exported visuals:  
👉 [`Fitbit_analysis_results`](./Fitbit_analysis_results)

---

# 📤 5. Share Phase  
### Tools Used: **RStudio (ggplot2)**  

Visualizations created to clearly communicate trends:

- 🔹 Daily steps trend  
- 🔹 Calories vs intensity  
- 🔹 Sedentary patterns  
- 🔹 Sleep vs activity  
- 🔹 Heart rate cycles  
- 🔹 Weekly activity profile  

---

# 🚀 6. Act Phase  
### ✔ High-Level Insights  
**1. Activity Patterns**  
- Peak movement between **7 AM – 10 AM**  
- Wednesday highest activity day  

**2. Sleep Behavior**  
- Users average **5–7.5 hours**  
- Better sleep = more steps  

**3. Intensity & Calories**  
- Very active minutes highly correlated with calorie burn  

**4. Sedentary Behavior**  
- More sedentary → fewer steps  

**5. Heart Rate Trends**  
- Afternoon peaks common across users  

---

## ✔ Recommendations for Bellabeat  
### **Marketing Strategy**
- Schedule morning engagement notifications  
- Mid-week challenges (activity high on Wednesday)  
- Sedentary reminders  

### **Product Enhancements**
- Improve sleep tracking  
- Add stress scoring via heart rate  
- Personalized intensity-based goals  

### **User Engagement**
- Weekly wellness summaries  
- Gamified step challenges  
- Balanced sleep–activity suggestions  

---

# 📂 Repository Contents  
| Folder / File | Description |
|---------------|-------------|
| **Fitbit_analysis_results/** | SQL results + R visualization screenshots |
| **fitbit_analysis_R/** | RStudio project files |
| **Tranformed_Fitbit_Dataset.xlsx** | Final cleaned dataset |
| **fitbit_analysis.sql** | MySQL analysis script |
| **README.md** | This documentation |

---

# 🙌 Acknowledgments  
Dataset: **Fitbit Fitness Tracker Data (Public Domain – Mobius / Kaggle)**  
Part of the **Google Data Analytics Professional Certificate**

---

# 👤 Author  
**Abdullah Ahmad**  
Data Analyst | SQL | R | Excel | BI  

🔗 GitHub: https://github.com/abdullahahmadd  
🔗 LinkedIn: *(Add your link)*  

---
