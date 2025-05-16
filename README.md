# Projects Analysis 

## <span style="color:orange; font-weight:bold">1. Exploratory Data Analyst example in the UK</span>


View my notebook with detailed steps here:  
[1_EDA.ipynb](My%20Project/1_EDA.ipynb)
## Goals
- Investigate top-paying roles and skills in the data science industry.
- Use Python to explore a real-live dataset on job postings.
- For job-seekers: use these insights to help find the best job opportunities.
(Feel Free to try out different countries or jobs)

## Methodology
### 1. Create a Barplot for Data Job availability in the UK
![Chart](My%20Project/Figures/output7.png) 
## Insights:
### 1. Most In-Demand Roles:
- Data Engineer leads with the highest job count (~11,500).

- Data Analyst and Data Scientist follow, with slightly fewer but still very strong demand (~10,000 and ~9,000 respectively).

- These three roles significantly outpace all others, indicating core demand in data pipeline, analysis, and modeling roles.

### 2. Mid-Level Roles:
- Senior Data Engineer, Senior Data Scientist, and Senior Data Analyst appear in the middle range (between ~1,500–3,500).  

- These roles suggest a healthy career progression path in the UK job market, though not as abundant as entry- or mid-level positions.

### 3. Less Common but Specialized Roles:
- Business Analyst, Software Engineer, Machine Learning Engineer, and Cloud Engineer have noticeably fewer job listings.

- This may indicate:
A more saturated or specialized market.
Or that business-specific roles (like Business Analyst) are being absorbed under broader job titles.

### Implications for Job Seekers:
- If you're aiming to break into tech in the UK, Data Engineer and Data Analyst are the safest bets in terms of volume.

- For long-term growth, investing in senior-level or niche roles (like ML or Cloud) may provide higher value, albeit with stiffer competition.

### 2. Create a Pie Plots of Benefits for Data Analyst in UK
![Chart](My%20Project/Figures/output8.png)
## Insights 
###  Work from Home Offered  
- False: 90.7% — Most data jobs do not offer remote work.
- True: 9.3% — Only a small fraction explicitly offer remote options.

### Degree Requirement
- False: 50.2% — Nearly half of the jobs do not require a degree.
- True: 49.8% — The other half do require a degree.
- This suggests degree requirements are evenly split, showing flexibility in education expectations.

### Health Insurance Offered
- False: 100.0% — None of the jobs mention offering health insurance.
- True: 0.0% — This may reflect either:
- UK companies not listing it explicitly (due to NHS coverage)
- A limitation in how the data captures benefits.

### 3. Create a Barplot for Counts of Job Skills for Data Analyst in UK (What skill is the most important?)
![Chart](My%20Project/Figures/output9.png)

## Insights:
### 1. Top 3 Most Required Skills (Must Have):
- SQL is the most in-demand skill — mentioned in over 4,500 job postings.

- Excel comes a close second — still vital for day-to-day data manipulation.

- Power BI ranks third, showing the importance of business intelligence and visualization tools.

(These three are essential baseline skills for Data Analysts in the UK market.)

### 2. Programming & Analytics Tools (Recommended):
- Python ranks 4th, showing that programming for data wrangling, analysis, and automation is increasingly required.  

- Tableau, R, and SAS also appear — all analytics and visualization tools, with Tableau leading the group.

(The market favors low-code tools, but coding skills (especially Python) are gaining prominence.)

### 3. Cloud & Infrastructure:
Azure and AWS are listed but appear far down, indicating that cloud familiarity is a plus, not a must for most roles.

### 4. Other Software/Tools:
- Tools like Go, PowerPoint, Word, VBA, and SQL Server appear with lower frequency.

- These may reflect legacy systems, internal reporting workflows, or cross-functional expectations.

---

## <span style="color:orange; font-weight:bold">2. What are the top 5 countries for each of the top 6 data roles?</span>

In order to do this, I filtered out those positions, and obtain the top5 countries of these top 6 data roles. And, to create a dataframe with the job_country, job_title_short and country_count. 

View my notebook with detailed steps here:  
[2_Country_Count.ipynb](My%20Project/2_Country_Count.ipynb)

## Key Codes for this question:
1. Creating Percentages next to each bar:  
```
for n, v in enumerate(df_plot['skill_percent']):
        ax[i].text(v + 0.5 , n, f'{v:.0f}%', va='center')
```
2. Add a skill_percent column to the merge dataframe
```
df_skills_perc= pd.merge(df_country_count, df_job_title_count, how='left', on='job_title_short')

df_skills_perc['skill_percent'] = 100 * df_skills_perc['country_count'] / df_skills_perc['jobs_total']
```
## Results
- For Matplotlib 
![Visualization of Top Countries for Data Role using Matplotlib](My%20Project/Figures/output.png)

------------
- For Using Seaborn with the percentages for each bar
![Visualization of Top Countries for Data Role using Seaborn](My%20Project/Figures/output2.png)

# Insights
The top hiring countries for six popular data job roles, offering insight into the global demand for data professionals.  
## United States: The Dominant Player
Across all six roles—Data Analyst, Data Engineer, Data Scientist, Senior Data Analyst, Senior Data Engineer, and Senior Data Scientist—the United States consistently holds the top position. This reflects the country’s mature tech industry, widespread data-driven business models, and a strong culture of analytics adoption.

## India: A Rapidly Growing Data Hub
India ranks second or third in several roles, especially in engineering and science positions. This trend aligns with India’s booming tech sector and its growing focus on data science education and outsourcing markets.  

## Western Europe’s Consistent Presence
The United Kingdom, France, and Germany frequently appear among the top five, highlighting Western Europe’s stable demand for data professionals. 

# Conclusion
The visualization confirms the United States as the central hub for data jobs, with India and Western Europe following as major players. Senior and specialized roles are more concentrated, while entry-to-mid level roles like Data Analyst are more widespread. Emerging appearances from countries like Sudan may warrant further investigation, as they could indicate interesting developments in regional data ecosystems.  

---
## <span style="color:orange; font-weight:bold">3. Find the trending for Top 7 Data Roles in the US </span>

View my notebook with detailed steps here:  
[3_Data_Role_Trend.ipynb](My%20Project\3_Data_Role_Trend.ipynb)



![Chart](My%20Project/Figures/output3.png)
# Insights

## 1. Highest-Paid Roles
Machine Learning Engineer (orange line) has the highest volatility but also reached the highest salary point—nearly $200K in May. Despite fluctuations, it remains one of the top-paying roles throughout the year.

Senior Data Scientist (blue line) consistently ranks among the top earners, staying within the 
170K range.

## 2. Stability vs Volatility
### Most Stable Salaries:  
Data Engineer (brown line): Shows little fluctuation, staying within 
140K.

Data Scientist (red line): Fairly stable, hovering around 
145K.

### Most Volatile Salaries:  
Machine Learning Engineer and Software Engineer (purple line): Both show significant monthly changes, indicating fluctuating demand or reporting inconsistencies.

Software Engineer saw a sharp dip in September (~
145K by December, which may indicate a seasonal hiring or market anomaly.

## 3. Lowest-Paid Role
Senior Data Analyst (pink line) has the lowest salary trend, staying within the 
125K range across the year.

----
## <span style="color:orange; font-weight:bold">4. How well do the Top 6 Data Jobs paid in the US?</span>
View my notebook with detailed steps here:  
[4_Salary_Analysis.ipynb](My%20Project\4_Salary_Analysis.ipynb)

## Methodology
- Evaluate median salary for Top 6 data jobs
- Find median yearly salary per skill for Data Analyst
- Visualize for highest paying skills and most demanded skills to compare their salaries

![Chart](My%20Project/Figures/output6.png)
# <span style="color:red; font-weight:bold">Conclusion</span>
- We can see that Senior Data Scientist has the highest yearly salary in the US  

- Moving into Senior Data roles (especially engineering or science tracks) is financially rewarding. 
- Technical depth pays more: Data Scientists and Engineers generally earn more than Analysts.
- Data Analyst has the lowest median salary in the chart. A common entry point into the data field with less variation and lower ceiling unless transitioning to more technical roles. 


----
## <span style="color:orange; font-weight:bold">5. What is the most optimal skill to learn for Data Scientist & Data Analyst?</span>

View my notebook with detailed steps here:  
[5_Data_Role_Trend.ipynb](My%20Project\5_Optimal_Skills.ipynb)

## Methodology
1. Group skills to determine median salary and likelihood of being in posting
2. Visualize median salary vs percent skill demand
3. Compare both Data Jobs to see the skill demand and the salary difference

![Chart](My%20Project/Figures/output4.png)
### 🧪 Data Scientist Overview
### High-Demand Skills:

- Python (73%) and SQL (54%) are the most in-demand, with median salaries of ~$133K and ~$134K respectively.

- R (45%) and Tableau (21%) are also fairly common.

### High-Paying Skills:

- TensorFlow ($150K) stands out with the highest median salary, although it appears in only 10% of jobs.

- Spark ($136K) and AWS ($134K) also offer high salaries and moderate demand (15-16%).

### Observations:

- A trade-off between demand and salary. More niche, specialized skills like TensorFlow and Spark are less frequently required but pay more.

- Widely used skills like Python and SQL provide a balance of good pay and high demand.

### 📊 Data Analyst Overview
### High-Demand Skills:

- SQL (57%) and Excel (41%) dominate in job requirements.

- Python (32%), Tableau (31%), and R (20%) are also fairly popular.

### High-Paying Skills:

- Python ($98K) and Oracle ($97K) are the top-paying, though Oracle is only in 6% of jobs.

- Tableau ($93K) and SQL Server ($93K) also offer competitive salaries.

### Observations:  

- Analysts earn less overall than scientists (~$90K range vs. ~$130K+).

- While Excel is widely used, it correlates with lower salaries (~$85K).

- Python stands out for both demand and salary potential.

![Chart](My%20Project/Figures/output5.PNG)


