# Student Performance Analysis

An exploratory data analysis (EDA) of 5,000 student records to identify which 
academic, lifestyle, and demographic factors are most strongly associated with 
exam performance.

---

## Overview

This project analyzes the **Student Academic Performance Dataset** (5,000 records, 
21 features) using Python. The goal is to understand which factors actually 
influence exam scores — and which commonly assumed factors (like screen time or 
gaming) don't.

The analysis moves from basic data cleaning → individual feature relationships → 
a full correlation heatmap → group-wise comparison across demographics and 
situational factors.

---

## Key Findings

### Strongest predictors of exam score
| Feature | Correlation (r) |
|---|---|
| Productivity Score | **+0.886** |
| Focus Index | **+0.750** |
| Mental Health Score | **+0.547** |
| Study Hours | **+0.513** |
| Burnout Level | **−0.408** |

### Group-wise insights
- **Part-time job:** Students without one score ~3.6 marks higher on average.
- **Upcoming deadline:** Students without one score ~5.2 marks higher on average 
  — the largest gap found in the analysis.
- **Gender & academic level:** No meaningful difference in exam scores.

### Weak / negligible predictors
Gaming hours, screen time, social media hours, self-study hours, online class 
hours, age, and caffeine intake all showed little to no relationship with 
exam performance.

### Data quality
- 5,000 rows, 21 columns
- No missing values
- No duplicate records
- Exam scores are right-skewed (range 1–64, not a standard 0–100 scale)
- A few outliers present but retained as genuine observations

### Multicollinearity note
`focus_index` and `productivity_score` are highly correlated with each other, 
meaning they likely measure overlapping traits. This is worth keeping in mind 
for any future modeling work.

---

## Dataset

- **Name:** Student Academic Performance Dataset
- **Source:** [Kaggle](https://www.kaggle.com/datasets/ayeshasiddiqa123/student-perfirmance)
- **Records:** 5,000
- **Features:** 21

---

## Tools Used

- **Python**
- **Pandas** — data loading, cleaning, grouping
- **NumPy** — numerical operations
- **Matplotlib** — all visualizations (scatter plots, boxplots, histogram, heatmap)

---

## Project Structure
student-performance-analysis/
│
├── data/
│ └── student_performance.csv
│
├── notebooks/
│ └── student_performance_eda.ipynb
│
└── README.md

---

## What's Inside the Notebook

1. **Dataset Overview** — shape, data types, summary statistics
2. **Data Cleaning** — missing values, duplicates
3. **Exploratory Data Analysis** — 11 scatter plots exploring each feature 
   against exam_score
4. **Distribution Analysis** — histogram of exam scores
5. **Correlation Heatmap** — full feature-to-feature correlation matrix
6. **Outlier Detection** — boxplots of key features
7. **Correlation Ranking** — features ranked by strength of relationship 
   with exam_score
8. **Group-Wise Analysis** — exam scores compared across academic level, 
   gender, part-time job status, and upcoming deadline
9. **Final Conclusion** — summary of findings
10. **Limitations & Future Work**

---

## Limitations

- Correlation does not imply causation.
- The dataset appears synthetic; findings may not generalize to real student 
  populations.
- Exam score scale (1–64) is unusual and not directly comparable to standard 
  0–100 grading systems.
- `focus_index` and `productivity_score` are collinear, which may inflate their 
  apparent importance when considered separately.

---

## Future Work

- Cluster students by lifestyle and study habits to identify distinct profiles.
- Investigate the collinearity between `focus_index` and `productivity_score` 
  and possibly combine them into a single composite feature.
- Extend the analysis by building a regression model using the top predictors 
  identified here (productivity, focus, mental health, study hours, burnout).

---

## Author

**Kaushani Sen**

This project was built as part of a learning journey into data analysis with 
Python, using a real-world-style dataset and a question-driven approach.
