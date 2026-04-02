# 📊 User Engagement & Conversion Analysis Dashboard

## 🚀 Overview
This project analyzes user behavior in an online learning platform to identify engagement patterns, conversion bottlenecks, and learning outcomes.

The goal was to understand:
- How users move through the learning funnel
- Where users drop off
- Whether low completion is due to poor performance or low engagement

---

## 🎯 Problem Statement
Despite a large number of users registering for courses, completion rates remain low.

This project aims to:
- Analyze the user journey (Registered → Viewed → Explored → Certified)
- Measure conversion rates across stages
- Evaluate engagement differences between certified and non-certified users
- Provide actionable insights to improve retention

---

## 🧰 Tech Stack

- **Python (Pandas, Seaborn, Matplotlib)** → Data cleaning & exploratory analysis  
- **Power BI** → Dashboarding & KPI visualization  
- **DAX** → Custom metric creation  

---

## 📂 Dataset
- ~641,000 user records
- Includes user activity, engagement metrics, and course outcomes

Key fields:
- `registered`, `viewed`, `explored`, `certified`
- `nevents`, `ndays_act`, `nchapters`
- `grade`

---

## ⚙️ Data Processing

### Python (Preprocessing)
- Handled missing values
- Standardized data types
- Exported cleaned dataset (`cleaned_data.csv`)

### Power BI (Modeling)
Created custom measures:
```DAX
CompletionRate = DIVIDE(SUM(certified), COUNT(Random))

AvgGrade_Certified =
AVERAGEX(
    FILTER(cleaned_data, cleaned_data[certified] = 1),
    cleaned_data[grade]
)

```
## 📊 Key Visualizations

### 1. User Conversion Funnel
Tracks user progression across stages:

Registered → Viewed → Explored → Certified

- Highlights drop-off at each stage
- Helps identify where users disengage

---

### 2. KPI Metrics
Key performance indicators derived from the dataset:

- **Total Users:** ~641K  
- **Completion Rate:** ~2.7%  
- **Avg Grade (Certified Users):** ~84%

---

### 3. Engagement Comparison (Certified vs Non-Certified)
Analyzes behavioral differences between user groups:

- Certified users show **significantly higher engagement**
- Metrics compared:
  - Number of events
  - Active days
  - Chapters explored

---

## 📈 Key Insights

- 🔻 **Massive drop-off in user journey**
  - Only ~2.7% of users complete the course

- 📉 **Largest drop occurs between "Viewed" → "Explored"**
  - Indicates low deep engagement

- 📊 **Engagement strongly correlates with completion**
  - Certified users have significantly higher activity levels

- 🎯 **High performance among completers (~84%)**
  - Suggests content quality is not the issue

---

## 💡 Business Recommendations

- Improve **early-stage engagement** after registration
- Introduce **nudges/reminders** to encourage exploration
- Optimize **content discovery and onboarding flow**
- Focus on **retention strategies rather than content redesign**

---

## 🧠 Key Learnings

- Importance of defining **correct KPIs** (avoiding misleading averages)
- Using **DAX for business metrics** in Power BI
- Combining **Python (EDA) + Power BI (visualization)** effectively
- Translating raw data into **actionable insights**

---

## 📌 Project Outcome

This project demonstrates:

- End-to-end data analysis workflow  
- Strong data storytelling and visualization  
- Ability to identify user behavior patterns  
- Business-oriented thinking with actionable insights  

---

---

## 🚀 Future Improvements

- Add cohort analysis (user retention over time)
- Build predictive model for course completion
- Perform segmentation (user personas)
- Deploy dashboard using Power BI Service

---

## 👩‍💻 Author

Preethi Ranganathan  
MS in Computer Science, George Mason University  
