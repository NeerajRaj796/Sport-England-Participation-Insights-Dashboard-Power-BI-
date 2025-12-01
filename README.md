📊 Sport England Participation Insights Dashboard (Power BI)
By Neeraj Raj Srinivasa Raju

This repository showcases a complete Power BI dashboard analysing Sport England’s Active Lives Survey for the periods 2019–20 and 2020–21.
The dashboard explores participation trends, demographic patterns, geographic insights, and year-on-year performance using a professionally modelled BI solution.

🚀 Project Overview

This Power BI project transforms raw Sport England data into an interactive, decision-focused insight report.

Key highlights include:

Clean star schema modelling

Multiple fact tables with shared dimensions

Advanced DAX measures

Consistent colour theme & UI/UX design

Fly-out navigation panel for smooth page transitions

Help & information pages for non-technical users

🗂️ Dashboard Pages & Screenshots
✔ 1. Summary Page

High-level participation story summarising the most important insights.

![Summary Page](screenshots/summary.png)

✔ 2. Respondents Profile

Demographic breakdowns such as gender, disability, and age distributions.

![Respondents Profile](screenshots/respondents_profile.png)

✔ 3. Regional and Local Authority Participation

UK map breakdown with filters for year and region.

![Regional and Local Authority Participation](screenshots/regional_local.png)

✔ 4. Demographics and Age Group Insights

Trend insights, YoY patterns, and age-segment behaviour.

![Demographics and Age Group Insights](screenshots/demographics_age.png)

✔ 5. Information Page

Explains dataset, methods, and how to navigate the report.

![Information Page](screenshots/info_page.png)

✔ 6. Help Page

User guide + author contact details for support.

![Help Page](screenshots/help_page.png)

🧩 Data Model & Architecture

The dashboard is built using a clean and performant star schema.

Fact Tables

Fact_2019_20

Fact_2020_21

Dimension Tables

Dim_Geography

Dim_Year

Key Principles Followed

Single-direction one-to-many relationships

Standardised geography values across both datasets

Consistent year/period mapping

Cleaned & validated Power Query transformations

Efficient DAX replacing complex calculations

🔧 Technologies Used
Technology	Purpose
Power BI Desktop	Data modelling, report building
Power Query (M)	Data cleaning & transformation
DAX	Advanced calculations, KPIs, YoY change
JSON Custom Theme	Visual consistency & accessibility
Star Schema	Optimised analytical model
Navigation Panel	Enhanced user experience
🧠 Key DAX Functions Used

CALCULATE() → modify filter context

DIVIDE() → safe percentage/ratio calculations

SUMX() → row-by-row evaluation

FILTER() → custom logic filtering

SELECTEDVALUE() → dynamic response to slicers

SWITCH() → conditional formatting (arrows, colours, labels)

📥 Dataset Source

This analysis uses publicly available data from:

Sport England – Active Lives Adult Survey
Includes respondent demographics, participation trends, and local authority details.

✨ Features Demonstrated

End-to-end BI solution building

Data cleaning across two incompatible datasets

Dimensional modelling with shared dimensions

Year-on-year performance monitoring

Geographic insights using choropleth mapping

KPI cards with dynamic increase/decrease indicators

Pages built with UX standards for public-sector analytics

Help and Information pages for accessibility

📬 Author

Neeraj Raj Srinivasa Raju
📧 Email: rajneeraj796@gmail.com

For any queries related to the dashboard or data model, feel free to reach out.

⭐ Support

If you found this project useful, please ⭐ star this repository and connect with me on LinkedIn!
