# Analysis 

## <span style="color:orange; font-weight:bold">1. What are the top 5 countries for each of the top 6 data roles?</span>

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
![Visualization of Top Countries for Data Role using Matplotlib](My%20Project/output.png)

------------
- For Using Seaborn with the percentages for each bar
![Visualization of Top Countries for Data Role using Seaborn](My%20Project/output2.png)

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
## <span style="color:orange; font-weight:bold">2. Find the trending for Top 7 Data Roles in the US </span>

View my notebook with detailed steps here:  
[3_Data_Role_Trend.ipynb](My%20Project\3_Data_Role_Trend.ipynb)



![Chart](My%20Project/output3.png)
# Insights

### 1. Highest-Paid Roles
Machine Learning Engineer (orange line) has the highest volatility but also reached the highest salary point—nearly $200K in May. Despite fluctuations, it remains one of the top-paying roles throughout the year.

Senior Data Scientist (blue line) consistently ranks among the top earners, staying within the 
170K range.

### 2. Stability vs Volatility
Most Stable Salaries:
Data Engineer (brown line): Shows little fluctuation, staying within 
140K.

Data Scientist (red line): Fairly stable, hovering around 
145K.

Most Volatile Salaries:
Machine Learning Engineer and Software Engineer (purple line): Both show significant monthly changes, indicating fluctuating demand or reporting inconsistencies.

Software Engineer saw a sharp dip in September (~
145K by December, which may indicate a seasonal hiring or market anomaly.

### 3. Lowest-Paid Role
Senior Data Analyst (pink line) has the lowest salary trend, staying within the 
125K range across the year.


## <span style="color:orange; font-weight:bold">3. What is the most optimal skill to learn for Data Scientist & Data Analyst?</span>

View my notebook with detailed steps here:  
[5_Data_Role_Trend.ipynb](My%20Project\5_Optimal_Skills.ipynb)

## Methodology
1. Group skills to determine median salary and likelihood of being in posting
2. Visualize median salary vs percent skill demand
3. Compare both Data Jobs to see the skill demand and the salary difference

![Chart](My%20Project/output4.png)
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

![Chart](My%20Project/Compare%20Data%20Scientist%20and%20Analyst.PNG)


