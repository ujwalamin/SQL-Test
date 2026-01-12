# Data Job Analysis SQL Project

## Introduction
Dive into the data job market focusing on data analyst roles. This project explores top paying jobs, in-demand skills, and where high demand meets high salary in data analytics.

SQL queries check them out more here: [project_sql](/project_sql)

## Background
Driven by a desire to better understand the data science job market, this project was born from an effort to pinpoint the most lucrative and in-demand skills for Data Analysts.

The data is sourced from Luke Barousse's [SQL Course](https://lukebarousse.com/sql). It contains detailed information on job titles, salaries, locations, and essential skills.

### The questions I wanted to answer through my SQL queries were:
1. What are the top paying data analyst jobs?
2. What skills are required for these top-paying jobs?
3. What are the most in-demand skills for data analysts?
4. Which skills are associated with higher salaries?
5. What are the most optimal skills to learn?

## Tools I Used
For my deep dive into the data analyst job market, I harnessed the power of several key tools:
- **SQL:** The backbone of my analysis, allowing me to query the database and unearth critical insights.
- **PostgreSQL:** The chosen database management system, ideal for handling the job posting data.
- **Visual Studio Code:** My go-to IDE for database management and executing SQL queries.
- **Git & GitHub:** Essential for version control and sharing my SQL scripts and analysis, ensuring collaboration and project tracking.

## The Analysis
Each query for this project was designed to investigate specific aspects of the data analyst job market.

### 1. Top Paying Data Analyst Jobs
To identify the highest-paying roles, I filtered for Data Analyst positions by average yearly salary and focused on remote jobs.

```sql
SELECT
    job_id,
    job_title_short,
    job_location,
    job_schedule_type,
    salary_year_avg,
    job_posted_date,
    name AS company_name
FROM
    job_postings_fact
LEFT JOIN company_dim ON job_postings_fact.company_id = company_dim.company_id
WHERE
    job_title_short = 'Data Analyst' AND
    job_location = 'Anywhere' AND
    salary_year_avg IS NOT NULL
ORDER BY
    salary_year_avg DESC
LIMIT 10;
```

![Top Paying Skills](assets\Top_Paying_Skills.png)
*Bar graph visualizing the average salary for the top skills; ChatGPT generated this grapgh from my SQL query results*

## What I Learned

Throughout this project, I have deepened my understanding of the data analyst job market and enhanced my technical proficiency in SQL:

* **Advanced Query Crafting**: Mastered complex joins and merged multiple tables to retrieve multi-dimensional insights.
* **Data Aggregation**: Proficiently used `GROUP BY` and aggregate functions like `COUNT()` and `AVG()` to summarize large datasets.
* **Analytical Wizardry**: Improved my ability to transform raw data into professional, actionable insights for portfolio presentation.

---

## Conclusions

### Insights
From the analysis, several key findings emerged:

* **Top Paying Jobs**: Remote Data Analyst positions are highly lucrative, with some roles offering average salaries exceeding $600,000.
* **In-Demand Skills**: Core technical skills like SQL and Python remain the most frequently requested across the majority of job postings.
* **Optimal Skills**: High-paying and high-demand skills often involve specialized tools like Snowflake, Azure, and AWS, representing the "sweet spot" for career growth.

### Closing Thoughts
This project served as a comprehensive exercise in data storytelling. By combining technical SQL queries with clear documentation and visualizations, I can now better navigate the data job market and demonstrate my value to potential employers.
