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

<p align="center">
STEP 1 – Data Extraction<br/>
<p align="left">
    <br />Source: Centralized candidate tracking register stored in Google Sheets (2024–2025).<br />
    <br /> Due to data sensitivity, the original Google Sheets source cannot be shared.<br />
    <br />Data included multiple attributes across the recruitment process—interview stages, interviewer names, sourcing information, and timelines.<br />

<p align="center">
STEP 2 - Data Cleansing in SQL<br/>
<p align="left">
    <br />Loaded the dataset into SQL Server to clean the data before analysis.<br />
    <br />Objective: Remove unnecessary blank rows and ensure structural consistency<br />
    <br />Query Used:<br />
    <br />This eliminated entries with missing scheduling data which were erroneously included due to formatting issues in Google Sheets.<br />

```sql
DELETE FROM [dbo].[HR Scheduling Status - Section B CSV]
WHERE [HR_SCHEDULING_STATUS] IS NULL
```
<p align="center">
STEP 3 - Data Modeling in Power BI<br/>
<p align="left">
    <br />Imported the cleansed dataset from SQL into Power BI.<br />
    <br />Built a structured data model, including: Date tables for time-based filtering and Relationships across candidate status, interview scheduling, and performance metrics<br />

<p align="center">
STEP 4 - Data Cleaning & Feature Engineering in Power BI<br/>
<p align="left">
    <br />Removed any residual blank fields and cleaned formatting inconsistencies.<br />
    <br />Separated and standardized data columns (e.g., names, dates, and categorical stages).<br />
    <br />Engineered new metrics and fields using DAX (Data Analysis Expressions), such as: Average Days to Present Bio, HR Approval Rate, Interview Activity by Interviewer and Pipeline Volume by Quarter<br />

<p align="center">
STEP 5 - KPI & Visual Design<br/>
<p align="left">
    <br />Several dashboards were developed to provide comprehensive metrics and visibility across each stage of the recruitment process. These include dedicated views for sourcing, HR interviews, technical stages, overview pages, and specific search reports.

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
Search Report<br/>
<img src="https://i.imgur.com/q4Qzfgb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<p align="center">
HR Interview Insights <br/>
<img src="https://i.imgur.com/GBcQ3s1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<p align="center">
Technical Interview Analytics <br/>
<img src="https://i.imgur.com/lOvaOel.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />


