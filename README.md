<h1>End-to-End HR Pipeline Analysis and Dashboard</h1>



<h2>Description</h2>
The project aimed to enhance recruitment performance tracking and decision-making by developing a suite of interactive Power BI operational dashboards. These dashboards pull centralized candidate data from Google Sheets (2024–2025 register) to provide real-time insights for recruiting managers. The solution delivers high-level overviews and detailed performance analytics for interviewers and sourcers, supporting better follow-up, visibility, and accountability across the hiring process.

This dashboard is designed to give everyone in the company, particularly hiring managers, a clear understanding of the recruitment process, without needing to constantly request information from HR or the recruitment team.

By tracking Average Days to Hire, which measures the average number of days it takes a single candidate to move through the entire process, hiring managers can set transparent expectations to potential candidates. Similarly, tracking Average Days to Fill, which measures the average number of days it takes the company to begin recruiting and fill a role, the HR team can propose realistic timeframes to management, so they can better plan resource allocation, and begin recruiting at the right time.

The dashboard also helps to set expectations on the cost of recruitment, as well as the most productive places to focus hiring efforts. Finally, the dashboard provides a live update on the number of candidates who have applied and progress to each stage of the hiring process. This is a helpful way to keep everyone up to date with how open positions are progressing, without requiring colleagues to request this information manually.
<br />

<h2>Tools & Technologies Used</h2>

- <b>Power BI</b>
- <b>SQL</b>
- <b>Excel / Google Sheets</b>

<h2>Key Metrics Created (DAX)</h2>

- <b>Time to Hire</b>
- <b>Number of HRs</b>
- <b>Number of Tech Interviews</b>
- <b>Total Hires</b>
- <b>Recruitment Funnel Effectiveness</b>
- <b>Number of Approved Tech Interviews</b>
- <b>HR Approval Rate</b>
- <b>Tech Approval Rate</b>

<h2>Project walk-through</h2>

## Step 1 – Data Extraction

**Source:** Centralized candidate tracking register stored in Google Sheets (2024–2025).  
Due to data sensitivity, the original Google Sheets source cannot be shared.  
Data included multiple attributes across the recruitment process—interview stages, interviewer names, sourcing information, and timelines.  

## Step 2 – Data Cleansing in SQL

Loaded the dataset into SQL Server to clean the data before analysis.  
**Objective:** Remove unnecessary blank rows and ensure structural consistency.  
**Query Used:**  
This eliminated entries with missing scheduling data which were erroneously included due to formatting issues in Google Sheets.

```sql
DELETE FROM [dbo].[HR Scheduling Status - Section B CSV]
WHERE [HR_SCHEDULING_STATUS] IS NULL
```
## Step 3 – Data Modeling in Power BI
 <br />Imported the cleansed dataset from SQL into Power BI.<br />
Built a structured data model, including: Date tables for time-based filtering and Relationships across candidate status, interview scheduling, and performance metrics

## Step 4 – Data Cleaning & Feature Engineering in Power BI
- <b>Removed any residual blank fields and cleaned formatting inconsistencies.</b>
- <b>Separated and standardized data columns (e.g., names, dates, and categorical stages).</b>
- <b>Engineered new metrics and fields using DAX (Data Analysis Expressions), such as: Average Days to Present Bio, HR Approval Rate, Interview Activity by Interviewer and Pipeline Volume by Quarter</b>  

## Step 5 – KPI & Visual Design
Several dashboards were developed to provide comprehensive metrics and visibility across each stage of the recruitment process. These include dedicated views for sourcing, HR interviews, technical stages, overview pages, and specific search reports.

Each dashboard highlights the key performance indicators (KPIs) and the most relevant metrics for its respective stage, enabling stakeholders to track progress, identify bottlenecks, and make data-driven decisions more effectively.<br />
    <br />Dynamic filtering by Quarter, Year, Interviewer, Client, and Search Name.<br />
    <br />Key visuals: Pie charts, bar graphs, trend lines, and progress trackers.<br />

<h2>Final Outcome</h2>

- <b>The final dashboard offers real-time, interactive visibility into HR interviewer performance, sourcer contributions, and candidate progression.</b>
- <b>Enables HR leaders to identify bottlenecks, track KPIs over time, and assess performance per interviewer and quarter.</b>
- <b>Designed to support informed decision-making and improve recruitment operations.

</b>

<p align="left">
NOTE: Due to data sensitivity, the metrics, names, and client information displayed on the dashboard have been blurred.

<p align="center">
  <h1 align="center">Recruiting Overview</h1>
</p>

This page serves as the **overview section** of the recruiting analytics report. It highlights the most important KPIs in the hiring pipeline, including:

- **Number of HR interviews conducted**  
- **Total hires**  
- **Number of technical interviews**  
- **Number of approved technical interviews**

In addition to these summary metrics, the dashboard includes several visualizations for deeper insights:

- **Pie Chart:** Displays the proportion of candidates at each stage of the process (HR Interviewed, Tech Interviewed, Client Stage, Hired).  
- **Bar Charts:** Show the distribution of HR interviews by search/project and the number of technical interviews completed by search.  
- **Search Pipeline Overview Table:** Summarizes candidate flow for each active search, tracking counts across every stage (HRs, Techs, Bios Posted, Client Stage, and Hires). This allows comparison of performance and progress across different roles.  
- **Line Chart:** Visualizes HR interview activity over time, illustrating volume trends and growth in interviews from 2024 to 2025.
 <p align="center">
<img src="https://i.imgur.com/tf04hUi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<p align="center">
<p align="center">
  <h1 align="center">Search Report</h1>
</p>

This explanatory **search report** provides a detailed breakdown of a specific recruitment search, offering key metrics and visualizations to track hiring progress. It can be accessed by clicking the "Click for Search Info" link on the overview page or by selecting the corresponding search in the overview pipeline. The report highlights essential KPIs, including the total number of HR interviews, technical interviews conducted, and bios submitted to the client, which represent candidate profiles sent for review.

In addition to these summary metrics, this dashboard also includes several visualizations for deeper insights:

A pie chart illustrates the distribution of candidates across different stages. Additionally, a bar chart breaks down the number of technical interviews handled by each interviewer.

The report also includes a line chart tracking HR interview activity over time, displaying yearly, monthly or daily trends. This helps identify peak hiring periods and assess recruiter workload.

Finally, a candidate progress tracker lists each candidate in the pipeline, detailing their current stage (e.g., HR Interviewed, Tech Interviewed), assigned interviewer, and source. This table ensures transparency in tracking individual candidate journeys and helps recruiters manage the pipeline efficiently.
 <p align="center">
<img src="https://i.imgur.com/q4Qzfgb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<p align="center">
<p align="center">
  <h1 align="center">HR interview report</h1>
</p>

This specialized HR interview report provides a focused analysis of recruitment activities, filtered by HR interviewer along with other standard filtering options. It highlights key metrics tailored to assess HR interview performance, including HR approval rate, interviewer contributions, and workload distribution.

The report begins with core HR-specific metrics, such as the total number of HR interviews conducted, the HR approval rate (percentage of candidates advancing past HR screening), and the number of bios presented to the client (profiles submitted after tech approval). These KPIs help measure the efficiency and effectiveness of HR screenings.

A pie chart breaks down the contribution of each HR interviewer, showing the proportion of interviews handled by interviewers. This visualization helps identify top performers and balance workloads. Another pie chart displays the bios presented per interviewer, indicating how many candidates each HR professional successfully moved forward to the client review stage.

A line chart tracks HR interview activity over time, segmented by interviewer. This allows hiring managers to monitor individual recruiter workloads, identify peak periods, and ensure equitable task distribution. For example, spikes in interviews for a specific recruiter may signal the need for workload adjustments.

Finally, the report also includes a candidate progress tracker, listing each candidate’s current stage (e.g., HR Interviewed, Tech Interviewed), assigned HR interviewer, and source. This table ensures visibility into the pipeline, helping teams track candidate flow and interviewer accountability.
 <p align="center">
<img src="https://i.imgur.com/GBcQ3s1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<p align="center">
<p align="center">
  <h1 align="center">Tech Interview Analytics Report</h1>
</p>

This tech interview report provides a focused analysis of the technical evaluation phase in the recruitment process, with filtering capabilities by HR interviewer, tech interviewer, and other standard parameters. It delivers key metrics to assess the efficiency and effectiveness of technical screenings, including tech approval rate, average days to tech interview (time elapsed between HR and tech interviews), and interviewer-specific contributions.

The report opens with core tech-specific metrics, such as the total number of tech interviews conducted, the tech approval rate (percentage of candidates passing technical evaluations), and the average days to tech interview, which highlights bottlenecks in scheduling. These KPIs help identify delays and optimize the handoff between HR and technical teams.

A pie chart visualizes the contribution of each HR interviewer in advancing candidates to tech interviews, showing the proportion of candidates referred by recruiters. This reveals which HR professionals are most effective at qualifying candidates for technical rounds. Another pie chart breaks down the number of tech interviews conducted by each technical interviewer, providing insight into workload distribution and specialization.

A line chart tracks tech interview activity over time, segmented by the HR interviewer responsible for initiating the process. This helps correlate HR recruiter performance with downstream tech interview volume, ensuring accountability and identifying trends—such as spikes in referrals from specific recruiters.

Finally, the report includes a candidate progress tracker, listing each candidate’s current stage (e.g., Tech Interviewed, Pending Client Review), assigned HR interviewer, tech interviewer, and sourcer. This table ensures end-to-end visibility, enabling teams to monitor pipeline efficiency and interviewer performance.
 <p align="center">
<img src="https://i.imgur.com/lOvaOel.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />


