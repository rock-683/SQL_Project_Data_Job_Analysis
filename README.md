# Introduction 
Dive into the data job market! Focusing on data analyst roles, this project explores top-paying jobs, in-demand skills, and where high demand meets high salary in data analytics.

SQL queeries? Check them out here: [project_sql folder](/project_sql/).

# Background
Driven by a quest to navigate the data analyst job market more effectively, this project was born form a desire to pinpoint top-paid and in-demand skills, streamlining others work to find optimal jobs. 

Data hails from by [SQL Course](https://lukebarousse.com/sql). It's packed with insights on job titles, salaries, locations, and essential skills. 

### The questions I wanted to answer through my SQL queries were:

1. What are the top-paying jobs for my role?
2. What are the skills required for these top-paying roles?
3. What are the most in-demand skills for my role?
4. What are the top skills based on salary for my role?
5. What are the most optimal skills to learn? (Optimal: High Demand AND High Paying)

# Tools I Used
For my deep dive into the data analyst job market, I harnessed the power of several key tools:

- **SQL**: The backbone of my analysis, allowing me to query the database and unearth critical insights. 

- **PostgreSQL**: The chosen database management system, ideal for handling the job posting data.

- **Visual Studio Code**: My go-to for database management and executing SQL queries. 

- **Git & GitHub**: Essential for version control and sharing my SQL scripts and analysis, ensuring collaboration and project racking. 

# The Analysis
Each query for this project aimed at investingating specific aspects of the data analyst job market. Here's how I approached each question:

### 1. Top Paying Data Analyst Jobs
To identify the highest-paying roles, I filtered data analyst positions by average yearly salary and location, focusing on remote jobs. This query highlights the high paying opportunities in the field. 

```sql
SELECT
    job_id,
    job_title,
    job_location,
    job_schedule_type,
    salary_year_avg,
    job_posted_date,
    jpf.company_id,
    cd.name AS company_name
FROM
    job_postings_fact AS jpf
LEFT JOIN
    company_dim AS cd
    ON jpf.company_id = cd.company_id
WHERE 
    job_title_short = 'Data Analyst'
    AND job_location = 'Anywhere'
    AND salary_year_avg IS NOT NULL
ORDER BY
    salary_year_avg DESC
LIMIT 10; 
```
Here's the breakdown of the top data analyst jobs in 2023:
- **Wide Salray Range:** Top 10 paying data analyst roles span from $184,000 to $650,000, indicating significant salary potential in the field. 
- **Diverse Employers:** Companies like SmartAsset, Meta, and AT&T are among thos offering high salaries, showing a broad interest across different industries. 
- **Job Title Variety:** There's a high diversity in job titles, from Data Anayst to Director of Analytics, reflecting varied roles and specializations within data analytics. 

![Top Skills](assets\top_skills.png)
*Bar graph visualizing the salary for the top 10 salaries for data analysts; 

# What I Learned


# Conclusions
From the analysis, several general insights emerge:

1. **Top-Paying Data Analyst Jobs**: The highest-paying jobs for data analysts that allow remote work offere a wide range of salaries, the highest at $650,000!
2. **Skills for Top_Paying Jobs**: High-paying data analyst jobs require advanced proficiecy in SQL, suggestin git's a critical skill for earning a top salary. 

