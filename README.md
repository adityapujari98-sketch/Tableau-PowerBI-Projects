# Data Professional Survey – Power BI Dashboard
## Project Objective
Build an interactive dashboard from a real-world survey of data professionals (≈600–700 respondents) to explore roles, salaries, tools, satisfaction, and entry difficulty—so learners and recruiters can quickly understand trends and compare segments (e.g., by country or job title).

## Dataset Used
- <a href="https://github.com/adityapujari98-sketch/Tableau-PowerBI-Projects/blob/main/Power%20BI%20-%20Final%20Project.xlsx">Dataset</a> 

## Key Questions (KPIs)
- Average **salary by job title** (Analyst, Engineer, Architect, Scientist, Student, Other)
- **Favorite programming language** overall and by role
- **Country distribution** and its impact on salary
- **Happiness with Salary** and **Work–Life Balance** (0–10)
- **Entry difficulty** into data (Very Easy → Very Difficult)
- **Gender split** and **average salary** by gender

## Process

### Data Preparation (Power Query)
- Dropped unneeded metadata columns (e.g., browser/referrer).
- Standardized “**Other (…)**” free-text responses by splitting on delimiters and collapsing into **Other** for:
  - **Job Title** → canonical categories + *Other*
  - **Favorite Programming Language** → canonical + *Other*
  - **Country/Industry** → canonical + *Other*
- Converted **salary ranges** like `106–125k` to a **numeric average**:  
  - Split into `Low` and `High`, stripped symbols (`k`, `-`, `+`)  
  - Treated `225k+` as `225k` for averaging  
  - Created `AverageSalary = (Low + High) / 2`
- Fixed **data types** (numeric/text/date).

## Dashboard
![Screenshot (495)](https://github.com/adityapujari98-sketch/Tableau-PowerBI-Projects/blob/main/PowerBI%20dashboard.png)

### Modeling / Measures
- Used implicit measures:
  - `Average of [AverageSalary]`
  - Count of unique respondents
- Friendly field/visual labels (e.g., “Count of Survey Takers”).


## Insights (from this sample)

- **Salary by Role:** Data Scientists tend to have the highest average; Analysts lower than Engineers/Architects; Students/Other lowest.  
- **Language Preference:** **Python** is the clear overall favorite; Java/JS/C++/R follow; long tail under “Other.”  
- **Country Effects:** Salaries vary strongly by country (e.g., U.S. averages trend higher than India due to COL and currency).  
- **Satisfaction:**  
  - **Work–Life Balance** ≈ mid-to-upper range (around 5–6/10).  
  - **Salary Happiness** typically trails WLB.  
- **Entry Difficulty:** Plurality around **Neither/Difficult**, with smaller tails at extremes.  
- **Gender & Pay:** In this respondent set, **average female salary ≈ male (slightly higher)** — interpret cautiously (sample size, mix of roles/countries).






