# Job-Market-Analysis
This project explores the Data Analyst job market in India using real-world job posting data. It analyzes salary trends, skill demand, and technology relevance, helping job seekers understand what skills are most valued — and how they influence pay.

# Overview

Welcome to my analysis of the data job market, focusing on data analyst roles. This project was created out of a desire to navigate and understand the job market more effectively. It delves into the top-paying and in-demand skills to help find optimal job opportunities for data analysts.

The data sourced from [Luke Barousse's Python Course](https://lukebarousse.com/python) which provides a foundation for my analysis, containing detailed information on job titles, salaries, locations, and essential skills. Through a series of Python scripts, I explore key questions such as the most demanded skills, salary trends, and the intersection of demand and salary in data analytics.

# Background- Key Questions
With the rapid growth of data-driven decision-making across industries, the demand for skilled Data Analysts has surged.
However, salary expectations and skill requirements vary widely depending on tools, experience, and company type.
This project dives deep into those patterns, aiming to answer key questions such as:

1. What are the high demand jobs in Indian market?
2. Which tools and technologies are most in-demand for Data Analyst roles?
3. How do salaries fluctuate month-to-month?
4. Which skills provide the best return on learning investment?
5. Most hiring companies in India?
6. Salary distribution of Data jobs in India
   

# Tools I Used

For my deep dive into the data analyst job market, I harnessed the power of several key tools:

- **Python:** The backbone of my analysis, allowing me to analyze the data and find critical insights.I also used the following Python libraries:
    - **Pandas Library:** This was used to analyze the data. 
    - **Matplotlib Library:** I visualized the data.
    - **Seaborn Library:** Helped me create more advanced visuals. 
- **Jupyter Notebooks:** The tool I used to run my Python scripts which let me easily include my notes and analysis.
- **Visual Studio Code:** My go-to for executing my Python scripts.
- **Git & GitHub:** Essential for version control and sharing my Python code and analysis, ensuring collaboration and project tracking.

# Analysis
  **1. Data Preparation**
  I start by importing necessary libraries and loading the dataset, followed by initial data cleaning tasks to ensure data quality.

```python
# Importing Libraries
import ast
import pandas as pd
import seaborn as sns
from datasets import load_dataset
import matplotlib.pyplot as plt  

# Loading Data
dataset = load_dataset('lukebarousse/data_jobs')
df = dataset['train'].to_pandas()

# Data Cleanup
df['job_posted_date'] = pd.to_datetime(df['job_posted_date'])
df['job_skills'] = df['job_skills'].apply(lambda x: ast.literal_eval(x) if pd.notna(x) else x)
```
  Filtered dataset for Data Analyst roles in India.

  Cleaned and standardized salary data to ensure consistency.

  Created additional columns for monthly trends and skill percentages.

# Analysis

## 1. What are the most demanded jobs in Indian market?

We are finding the top 4 most demanded jobs. This query highlights that Data Engineer has highest number of job postings over the months.

### Visualize Data

<img width="580" height="453" alt="image" src="https://github.com/user-attachments/assets/c7152516-af0f-4f60-88bd-f20d5f6d9f5c" />

### Insights:

- Data Engineer roles consistently dominate the Indian job market, maintaining the highest number of openings throughout the year.
- Data Scientist demand fluctuates, peaking around Oct–Nov.
- Data Analyst demand remains steady but moderate, gradually increasing toward mid and late year, suggesting stable opportunities for entry to mid-level professionals.
- Senior Data Engineer roles have the lowest and most stable demand, reflecting limited openings at the senior level compared to entry or mid-level positions.

## 2. Which tools and technologies are most in-demand for Data Analyst roles?

To find how skills are trending in 2023 for Data Analysts, I filtered data analyst positions and grouped the skills by the month of the job postings. This got me the top 5 skills of data analysts by month, showing how popular skills were throughout 2023.

### Visualize Data

<img width="623" height="472" alt="image" src="https://github.com/user-attachments/assets/bd15fba0-8c0b-47d6-a566-34fa8f278539" />

### Insights:
- SQL remains the most consistently demanded skill for majorly all Data roles.
- Tableau and Power BI also appear frequently, highlighting the need for strong visualization skills.
- Overall, recruiters prefer candidates skilled in data querying + analysis + visualization tools. 

## 3. How do salaries fluctuate month-to-month for Data Analysts?

To identify the salary trend over the months of 2023, I only filtered jobs for Data analysts in India and looked at their median salary. 

#### Visualize Data 

<img width="784" height="384" alt="image" src="https://github.com/user-attachments/assets/eb9178af-24dc-4372-93d8-089f7bbe4cef" />

#### Insights

- Average salary peaks sharply in February, indicating possible early-year hiring spikes or bonuses.
- Salaries stabilize from March onward, staying between ₹75K–₹110K for most months.
- The median salary closely follows the average, suggesting a balanced distribution without extreme outliers after February.There's a significant variation in salary ranges across different job titles. 

### 4.Which skills provide the best return on learning investment?
To identify the most optimal skills to learn ( the ones that are the highest paid and highest in demand) I calculated the percent of skill demand and the median salary of these skills. To easily identify which are the most optimal skills to learn. 

#### Visualize Data
<img width="975" height="580" alt="image" src="https://github.com/user-attachments/assets/acb6f019-e56b-4050-a806-e0a8c92ae738" />

#### Insights:

- MongoDB offers the highest median salary (~₹165K) despite low demand, showing high value for niche expertise.
- Power BI and Tableau balance strong demand with good pay, making them top picks for Data Analysts.
- SQL, Python, and Excel are widely required, offering steady job opportunities even with moderate pay levels.
- Tools like Azure and Spark also provide solid returns with growing relevance in cloud and big data fields.
  
### 5. Most hiring companies in India?

Let's visualize the most hiring companies. We narrowed down our search to top 20.

#### Visualize Data

<img width="781" height="457" alt="image" src="https://github.com/user-attachments/assets/2390ba75-bdb7-45c6-85b4-7406b30045b9" />

#### Insights:

- IBM, Visa, and PepsiCo are among the leading recruiters for data roles in India.
- Firms like LTIMindtree, Wells Fargo, and S&P Global also show strong hiring activity.
- The mix of tech, consulting, and finance companies highlights wide demand for data professionals across industries.


### 6. Salary distribution of Data jobs in India    

Let's now look at our last finding. Salary distribution amongst various Data roles.

#### Visualize Data

<img width="737" height="457" alt="image" src="https://github.com/user-attachments/assets/d8159a36-bec6-48fc-a524-c4eb5d9fa5f1" />

#### Insights:

- Data Engineers and Machine Learning Engineers earn the highest median salaries.
- Data Analysts earn comparatively less but with less salary variation, indicating more consistency.
- Senior Data Engineers and Data Scientists show wide pay ranges, reflecting variation by experience and company.


# What I Learned

Throughout this project, I deepened my understanding of the data analyst job market and enhanced my technical skills in Python, especially in data manipulation and visualization. Here are a few specific things I learned:

- **Advanced Python Usage**: Utilizing libraries such as Pandas for data manipulation, Seaborn and Matplotlib for data visualization, and other libraries helped me perform complex data analysis tasks more efficiently.
- **Data Cleaning Importance**: I learned that thorough data cleaning and preparation are crucial before any analysis can be conducted, ensuring the accuracy of insights derived from the data.
- **Strategic Skill Analysis**: The project emphasized the importance of aligning one's skills with market demand. Understanding the relationship between skill demand, salary, and job availability allows for more strategic career planning in the tech industry.


# Conclusion

This project provides a clear view of how skillsets impact salary and job opportunities for Data Analysts in India.
It highlights the importance of continuous upskilling in technologies like Python, SQL, and Power BI to stay competitive.

Through this analysis, I’ve strengthened both my technical and analytical storytelling skills, combining Python, visualization, and market insight to extract meaningful takeaways for career planning.

This project was inspired by **_Luke Barousse_**. 

## 👩‍💻 Author
_Mrigashree Ray_  
Data Analyst   
[LinkedIn](https://www.linkedin.com/in/mrigashree-ray/)  

