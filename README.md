📊 CASE STUDY: Sport England Active Lives Participation Dashboard

Author: Neeraj Raj Srinivasa Raju
Tool: Microsoft Power BI, SQL, Excel
Data Source: Sport England Active Lives Adult Survey (2019–20 & 2020–21)

The case study follows the six-step data analysis process:

❓ Ask
💻 Prepare
🛠 Process
📊 Analyze
📋 Share
🎯 Act

Scenario

Sport England collects national participation data to understand how people across England engage in physical activity. The dataset covers demographic, regional, and participation behaviour trends.

The objective of this analysis was to transform over 1 million survey responses into a structured, interactive Business Intelligence dashboard that identifies:

Year-on-year participation changes

Demographic participation patterns

Regional inequalities

Inclusion gaps

National benchmarking insights

The insights aim to support evidence-based sport development planning and resource allocation.

1️⃣ Ask

💡 BUSINESS TASK: Analyze Sport England participation data to identify national trends, demographic disparities, and regional performance differences to support strategic sport planning.

Primary stakeholders:
National sport development planners and regional participation teams.

Secondary stakeholders:
Policy analysts and community engagement planners.

Key questions:

Did participation increase between 2019–20 and 2020–21?

Which demographic groups are most active?

Are there inclusion gaps for disabled individuals?

Which local authorities outperform or underperform?

How do areas compare against the national average?

2️⃣ Prepare

📂 Data Source:
Sport England Active Lives Survey (Public dataset)

Two survey years were used:

2019–20

2020–21

Key metrics defined:

Total Respondents (569K → 882K)

YoY Increase (313K)

YoY Growth Rate (55%)

Female Participation (801K)

Male Participation (643K)

Disabled Participation (258K – 18%)

National Average per Local Authority (3.89K)

Data Reliability Considerations:

Large aggregated dataset (1M+ responses)

Publicly available survey

No personal-level identifiers

Structured regional and demographic breakdown

Limitations:

Aggregated data (no individual-level behavioural tracking)

Two-year comparison only

Structural differences required separate fact tables

3️⃣ Process

Data Cleaning Steps:

Verified respondent totals (569K and 882K)

Standardised geography naming conventions

Removed duplicate local authorities

Trimmed extra spaces in geography fields

Validated demographic totals

Star Schema Model Implemented:

Fact Tables:

Fact_2019_20

Fact_2020_21

Dimension Tables:

Dim_Geography

Dim_Year

Dim_Period

Relationships configured as one-to-many to ensure clean filtering.

DAX Used:

CALCULATE()

DIVIDE()

SUMX()

FILTER()

SELECTEDVALUE()

SWITCH()

ALL()

VAR / RETURN

This allowed dynamic Year-on-Year KPIs and benchmarking.

4️⃣ Analyze
📌 Summary Page

![Summary Page](Summary-Page.png)

Participation increased from 569K in 2019–20 to 882K in 2020–21, representing a 313K increase and 55% growth rate.

Female participation (55%) exceeded male participation (44%), and the gender distribution remained stable across both years.

The map visual highlights geographic concentration, with certain regions significantly outperforming the national average.

📌 Respondents Profile

![Respondents Profile](Respondents-Profile.png)

Demographic distribution shows:

Female: 801K

Male: 643K

Disabled: 258K (18%)

Non-disabled: ~77%

Age participation:

55–74: 556K (highest participation group)

35–54: 457K

16–34: 272K

75+: 156K (lowest participation)

This indicates strong engagement among middle-aged adults and lower participation among older adults.

📌 Regional & Local Authority Participation

![Regional and Local Authority Participation](R-&-LA-Participation.png)

National average participation per area: 3.89K

Top performing region:

Worcester: 12.1K respondents

Other strong performers:

Worthing: 2.1K

Wychavon: 2.1K

The benchmarking donut visual clearly highlights which areas exceed or fall below national average.

Year-on-year area comparison shows certain regions shifting from negative to positive growth, indicating regional recovery patterns.

📌 Demographics & Age Group Insights

![Demographics and Age Group Insights](Demographics-and-Age-group-Insights.png)


Age group distribution remains consistent across periods.

Treemap insights show that 55–74 and 35–54 dominate participation across high-performing regions.

Disability participation remains significantly lower than non-disabled participation in nearly all regions, highlighting potential inclusion gaps.

5️⃣ Share

The dashboard was structured into six logical pages:

Summary Page – Executive-level overview

Respondents Profile – Demographic breakdown

Regional & Local Authority Participation – Geographic benchmarking

Demographics & Age Group Insights – Age segmentation

Information Page – Usage instructions

Help Page – Author and contact details

Interactive slicers (Year, Month, Geography) allow dynamic filtering, making the dashboard accessible for both technical and non-technical users.

The design focuses on clarity, benchmarking, and actionable comparison rather than decorative visuals.

6️⃣ Act

Conclusion Based on Analysis:

📈 Participation increased by 55% year-on-year, indicating strong overall growth.

👩 Female participation consistently exceeds male participation.

♿ Disabled participation represents only 18% of total respondents, indicating room for stronger inclusion strategies.

👵 The 75+ demographic remains the least engaged group at 156K respondents.

🗺 Regional disparities exist, with some local authorities significantly exceeding the national average of 3.89K while others fall below.

Strategic Recommendations:

🔹 Prioritise funding and intervention in underperforming regions.
🔹 Develop targeted inclusion programmes for disabled communities.
🔹 Introduce age-specific engagement strategies for 75+.
🔹 Use benchmarking insights to replicate success factors from high-performing regions.
🔹 Continue monitoring year-on-year participation trends to assess intervention effectiveness.

This case study demonstrates:

Structured BI lifecycle

Advanced DAX application

Clean star-schema modelling

Quantified insight generation

Strategic, action-oriented conclusions
Dim_Geography

Dim_Year

Dim_Period / Month

🧮 Key DAX Used:

CALCULATE()

DIVIDE()

SUMX()

FILTER()

SELECTEDVALUE()

SWITCH()

📬 Contact

For queries related to this dashboard:

Neeraj Raj Srinivasa Raju
📧 Email: neerajrajsrinivasaraju@gmail.com
