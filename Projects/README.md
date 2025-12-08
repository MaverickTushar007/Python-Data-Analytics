

# 📊 U.S. Data Job Market Analysis — Focus on Data Analyst Roles

This project analyzes the **U.S. data job market** with a focus on **Data Analyst** roles.  
Using a real-world dataset from **[Luke Barousse’s Python course](https://lukebarousse.com/python)**, it explores:

- The **most in-demand skills**  
- How skill demand **changes over time**  
- **Salary distributions** across common data roles  
- The **optimal skills** that are both **high-paying** and **high-demand**

The goal is to understand what the market truly rewards, and how a Data Analyst can prioritize their skill development.

---

## 🎯 Key Questions

1. **What are the most in-demand skills for the top 3 data roles?**  
2. **How are in-demand skills trending for Data Analysts throughout 2023?**  
3. **How well do different roles and skills pay for Data Analysts?**  
4. **Which skills are both high-paying and high-demand (optimal skills)?**

Each question is tackled in a dedicated notebook.

---

## 🛠 Tools & Technologies

- **Python** — core language for analysis  
  - **Pandas** — data manipulation & aggregation  
  - **Matplotlib** — visualizations  
  - **Seaborn** — advanced plots & styling  
  - **ast / datasets** — parsing & loading dataset  
- **Jupyter Notebooks** — interactive exploration  
- **VS Code** — editing and workflow  
- **Git & GitHub** — version control and sharing  

---

## 🧹 Data Preparation & Cleanup

### Import & Initial Cleanup

```python
import ast
import pandas as pd
import seaborn as sns
from datasets import load_dataset
import matplotlib.pyplot as plt  

# Load dataset
dataset = load_dataset('lukebarousse/data_jobs')
df = dataset['train'].to_pandas()

# Basic cleanup
df['job_posted_date'] = pd.to_datetime(df['job_posted_date'])
df['job_skills'] = df['job_skills'].apply(lambda x: ast.literal_eval(x) if pd.notna(x) else x)
Data_Job_Market_Analysis/
│
├── Images/
│   ├── Likelihood_of_Skills_Requested_in_US_Job_Postings.png
│   ├── Trending_Top_Skills_for_Data_Analysts_in_the_US.png
│   ├── Salary_Distributions_of_Data_Jobs_in_the_US.png
│   ├── Highest_Paid_and_Most_In_Demand_Skills_for_Data_Analysts_in_the_US.png
│   ├── Most_Optimal_Skills_for_Data_Analysts_in_the_US.png
│   └── Most_Optimal_Skills_for_Data_Analysts_in_the_US_with_Coloring_by_Technology.png
│
├── Notebooks/
│   ├── 1_Data_Preparation.ipynb
│   ├── 2_Skill_Demand.ipynb
│   ├── 3_Skills_Trend.ipynb
│   ├── 4_Salary_Analysis.ipynb
│   └── 5_Optimal_Skills.ipynb
│
├── requirements.txt
└── README.md
