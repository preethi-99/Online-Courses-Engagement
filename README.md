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

##📊 Key Visualizations
1. User Conversion Funnel

Tracks user progression:

Registered → Viewed → Explored → Certified
2. KPI Metrics
Total Users (~641K)
Completion Rate (~2.7%)
Avg Grade of Certified Users (~84%)
3. Engagement Comparison

Analyzes behavioral differences:

Certified users show significantly higher engagement (events)
📈 Key Insights
🔻 Massive drop-off in user journey
Only ~2.7% of users complete the course
📉 Biggest gap occurs between "Viewed" and "Explored"
Indicates lack of deeper engagement
📊 Certified users show significantly higher activity
Strong correlation between engagement and completion
🎯 High performance among completers (~84% avg grade)
Suggests content is effective
💡 Business Recommendations
Improve early-stage engagement (post-registration experience)
Introduce nudges or incentives to encourage exploration
Optimize onboarding and content discovery
Focus on retention rather than content redesign
🧠 Key Learnings
Importance of defining correct KPIs (avoiding misleading averages)
Using DAX to create meaningful business metrics
Combining Python (EDA) + Power BI (visualization) for end-to-end analysis
Translating data into actionable insights
📌 Project Outcome

This project demonstrates:

End-to-end data analysis workflow
Dashboard design for business decision-making
Ability to identify and explain user behavior patterns

🚀 Future Improvements
Add cohort analysis
Track user behavior over time
Build predictive model for churn/completion
Deploy dashboard using Power BI Service
👩‍💻 Author

Preethi Ranganathan
MS in Computer Science, George Mason University
