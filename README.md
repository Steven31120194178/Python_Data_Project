# The Analysis

## 1. What are the top 5 countries for each of the top 6 data roles?

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
![Visualization of Top Countries for Data Role using Matplotlib](My%20Project\output.png)

------------
- For Using Seaborn with the percentages for each bar
![Visualization of Top Countries for Data Role using Seaborn](My%20Project\output2.png)

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