# Powerbi_project

Key Learnings derived from the dashboard are:
 
👉 Import Data in PostgreSQL DB;
👉 Connecting Power BI to Database;
👉 Data Cleaning & Processing in Power Query Editor;
👉 Data Modelling among three tables;
👉 Data Visualization;
👉 Creating KPI's;
👉 Time Intelligence Functions;
👉 DAX Queries (Calculate, SUM, SUMX, Concatenate, Filter, etc);
👉 Creating & Publishing Dashboard;
👉 Generating Insights
 
Key Insights: On the basis of All Seasons in IPL from Raw Data, following insights are derived:
 
✔ Latest IPL Winner for Year: 2022 is "Gujrat Titans"
✔ Maximum Runs scored in All IPL Seasons are scored by "Virat Kohli"
✔ Maximum Wickets taken by in All IPL Season is "D J Bravo"
✔ Total Six hits in all the tournaments are 10,666
✔ Total Four hits in all the tournaments are 25,499
 
 
[
1. Batting Strike Rate = (Total Runs scored in an innings/ Number of deliveries faced by the batsman)*100
DAX Query = StrikeRate for batsman =
(SUM('public ipl_ball_by_ball_2008_2022'[batsman_run])/COUNT('public ipl_ball_by_ball_2008_2022'[ball_number]))*100
 
2. Economy = (Total Runs conceded by a bowler/ Number of overs bowled)
DAX Query = Economy =
DIVIDE(SUMX(FILTER('public ipl_ball_by_ball_2008_2022', 'public ipl_ball_by_ball_2008_2022'[extra_type]<>"legbyes"&&'public ipl_ball_by_ball_2008_2022'[extra_type]<> "byes"), 'public ipl_ball_by_ball_2008_2022'[total_run]),(COUNT('public ipl_ball_by_ball_2008_2022'[overs]))/6)
 
3. Bowling Average = (Total Runs conceded by a bowler/ Number of wickets taken)
DAX Query = Average by Bowler =
DIVIDE(SUMX(FILTER('public ipl_ball_by_ball_2008_2022', 'public ipl_ball_by_ball_2008_2022'[extra_type]<>"legbyes"&&'public ipl_ball_by_ball_2008_2022'[extra_type]<> "byes"), 'public ipl_ball_by_ball_2008_2022'[total_run]),SUM('public ipl_ball_by_ball_2008_2022'[iswicket_delivery]))
 
4. Bowling Strike Rate = (Total Deliveries a bowler bowled in an innings/ Number of wickets taken)
DAX Query = Bowling SR =
COUNT('public ipl_ball_by_ball_2008_2022'[bowler])/SUM('public ipl_ball_by_ball_2008_2022'[iswicket_delivery])
]
 
 
 
