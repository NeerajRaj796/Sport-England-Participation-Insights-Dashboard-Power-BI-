📊 CASE STUDY: Sport England Active Lives Participation Dashboard (2019–20 vs 2020–21)

Author: Neeraj Raj Srinivasa Raju
Tooling: Power BI (DAX + Data Modelling), Excel (data validation), SQL (text validation)
Dataset: Sport England – Active Lives Adult Survey (2019–20 & 2020–21)

Scenario

Sport England’s Active Lives Survey is one of the most important public datasets for understanding how people across England engage with sport and physical activity. But raw survey tables are not decision-friendly: they’re large, repetitive, and difficult for non-technical users to interpret.

The purpose of this project was to transform two years of survey outputs into an interactive Power BI dashboard that helps stakeholders answer practical questions such as:

Is participation increasing or decreasing year-on-year?

Which regions/local authorities perform above or below the national benchmark?

How does participation differ by age, gender, and disability status?

Where are the biggest gaps that could inform targeted action?

This dashboard was built as an insight tool — not just a visual report.

❓ 1) Ask
Business Task

Build an interactive BI dashboard that compares 2019–20 vs 2020–21 participation patterns and highlights:

National trend (YoY change)

Demographic distribution (age, gender, disability)

Geographic variation (region & local authority benchmarks)

Where disparities exist, so organisations can prioritise interventions

Define the problem

The core problem is that participation outcomes are not evenly distributed. Even when the national trend improves, some demographic groups and regions may lag behind.

This creates a BI need: move from “overall numbers” to “who/where is missing” in a way stakeholders can explore without needing technical skills.

Ensuring I understood the problem

I translated the vague objective (“participation insights”) into measurable questions:

What is the YoY change at national level?

Which geography is above/below national average?

Which demographic groups dominate participation and which are underrepresented?

Do patterns change meaningfully across time (Period/Month)?

These questions shaped the model design and KPIs.

💻 2) Prepare
What data to collect

I used Sport England’s published Active Lives Survey aggregated outputs for:

Survey Year (2019–20, 2020–21)

Geography (regional groupings and local authorities)

Demographics

Gender (Male/Female)

Age bands (16–34, 35–54, 55–74, 75+)

Disability status (Disabled / Not Disabled)

Metrics to measure

To make the dashboard decision-ready, I defined core metrics first:

Participation volume KPIs

Total Respondents

YoY Difference (Respondents)

YoY Growth %

Demographic share KPIs

% Female vs % Male

% Disability vs % No Disability

Age band distribution (%)

Regional benchmarking KPIs

Respondents by Geography

Area vs National Average

Above/Below National benchmark indicators

How I located the data

I sourced the two survey-year datasets and imported them into Power BI as two fact tables (because the structures differ across years). This approach preserved row-level integrity and avoided forced joins that would cause incorrect totals.

Security measures

Because the dataset contains aggregated survey results (not personal data), risk is low. Still, I applied typical BI security discipline:

Restricted editing access (only author maintains the PBIX)

Controlled sharing via Power BI service/workspace permissions (view vs edit)

Optional: RLS design-ready structure (Dim tables enable future row-level filters if needed by region/team)

🛠 3) Process

This stage ensured the data is clean, consistent, and modelled correctly before analysis.

Data cleaning and error removal

The main challenge was structural mismatch between years:

2019–20 and 2020–21 tables use different IDs

Geography naming may not be identical across years

Some fields appear only in one year or are grouped differently

To avoid errors and inconsistencies:

Cleaning steps performed

Standardised Geography text formatting (trim/case consistency)

Removed duplicate geography labels using a dedicated dimension table

Ensured numeric fields were typed correctly (whole numbers)

Verified totals against expected year totals

How Excel helped validate data quality

Excel was used for quick sanity checks:

Checked if totals by age bands add up logically to total respondents

Identified incorrectly entered cells (e.g., blank numerics, text in numeric columns)

Quick pivot checks: Geography → totals to spot outliers

Using SQL to check extra spaces / inconsistencies

Where text issues are common (like Geography), SQL-style checks help detect formatting differences.

Example logic I used conceptually:

TRIM(Geography) to remove leading/trailing spaces

Compare LEN(Geography) vs LEN(TRIM(Geography))

Group by Geography to detect duplicates caused only by whitespace

Removing duplicates

Duplicates were removed mainly in dimension creation:

Geography dimension created from both fact tables

Removed duplicates after appending

Checking bias

This dataset is survey-based, so bias can exist due to:

Response rate differences by region

Underrepresentation of some demographics

Collection time effects (e.g., pandemic period in 2020–21)

Instead of claiming “no bias,” the report accounts for it by:

Comparing proportional distribution (not only absolute values)

Emphasising benchmarking and shares

Avoiding causal claims (only describing patterns)

📊 4) Analyze
How data was sorted and formatted

Inside Power BI:

Geography sorted using a clean Dim table

Survey Year formatted consistently (Dim_Year)

Measures built for YoY comparisons

Visual interactions controlled to prevent misleading cross-filtering

How calculations were performed

All KPIs were created using DAX measures so they remain dynamic under slicers.

Common DAX patterns used

You mentioned you mainly used: CALCULATE, DIVIDE, SUMX, FILTER, SELECTEDVALUE, SWITCH.
Here’s what each does in the context of your dashboard:

1) CALCULATE()

Changes the filter context to compute a metric under specific conditions.

Example use:

“Total respondents for 2019–20”

“Total respondents excluding a selected geography”

2) DIVIDE()

Safe division (prevents divide-by-zero errors).

Example use:

Growth % = (This Year – Last Year) / Last Year

3) SUMX()

Row-by-row calculation over a table, then sums results.
Useful when totals aren’t direct sums of one column, but derived.

4) FILTER()

Builds a filtered table expression.
Often used inside CALCULATE or SUMX for conditions.

5) SELECTEDVALUE()

Returns the selected value from a slicer when only one item is selected.
Used for titles, dynamic text, or KPI labels.

6) SWITCH()

Used for conditional logic (like nested IF).
Perfect for KPI arrows/colors and dynamic labels.

Combining data from multiple sources

The analysis combined two yearly datasets using a modelling approach rather than row-level merge:

Fact_2019_20

Fact_2020_21

These were connected to shared dimensions:

Dim_Year

Dim_Geography

(Optional) Dim_Period / Month

This method prevents incorrect joins and ensures each fact table remains valid.

Tables, relationships, and schema

The dashboard uses a star schema, which is best practice for BI performance and clean filtering.

Fact tables

Fact_2019_20: survey-year totals by geography and demographic

Fact_2020_21: similar metrics but different structure/IDs

Dimension tables

Dim_Year: two survey years for consistent filtering

Dim_Geography: unified list of geographies used in both years

Dim_Period (if used): for time breakdown

Why star schema?

It ensures:

Filters behave correctly (e.g., geography slicer affects both facts)

Measures stay consistent

Model scales if more years are added later

What the analysis found (Quantified core insights you already provided)
National participation trend

2019–20: 569,000 respondents

2020–21: 882,000 respondents

Change: +313,000 respondents

YoY Growth: +55%

This is a strong increase and becomes the headline narrative of the dashboard.

(If you want, later I can help you add “confidence narrative” around why growth happened, but without making unsupported claims.)

📄 5) Dashboard Pages

1) Summary Page

![Summary Page](Summary-Page.png)

This page acts as the executive overview and is designed to be understood in under 30 seconds. It brings together the most decision-critical indicators: national participation totals, the year-on-year trend, and a high-level demographic distribution. The geographic visual provides immediate context for where participation is concentrated, while the accompanying breakdowns highlight how participation is distributed across core groups. The page is intended for senior stakeholders who want “what’s happening” before exploring deeper diagnostic pages.

2) Respondents Profile

![Respondents Profile](Respondents-Profile.png)

This page explains who the respondents are, focusing on the most important segmentation variables: gender, disability status, and age bands. The key value here is not only the counts but the ability to filter by geography and compare distributions year-on-year. This allows stakeholders to test questions like: “Is the growth coming evenly from all age groups?” and “Do areas with high totals also show balanced inclusion?” It provides the demographic foundation needed before interpreting geographic performance.

3) Regional and Local Authority Participation

![Regional and Local Authority Participation](R-&-LA-Participation.png)

This page is designed for performance monitoring. It allows users to evaluate participation by geography and compare areas against a national benchmark. The map is the starting point for exploration, but the key insight comes from identifying which areas overperform and which fall below the national baseline. This is the page that supports action — it helps decision-makers identify which regions or local authorities require attention, investment, or programme redesign based on participation outcomes.

4) Demographics and Age group Insights

![Demographics and Age Group Insights](Demographics-and-Age-group-Insights.png)

This page deepens the analysis by connecting demographic behaviour with geography. Instead of looking at age and disability as national totals, it helps users explore how these patterns differ regionally. This is where inclusion gaps become more visible: for example, whether disability participation is consistently low across all areas or whether some regions demonstrate stronger inclusive participation. It supports targeted planning by letting users isolate an age group (e.g., 16–34 or 75+) and see where participation is strongest or weakest.

5) Information Page

![Information Page](Information-Page.png)

This page reduces the “BI learning curve” for non-technical users. It explains how to interact with slicers, how visuals respond to each other, and how to interpret metrics. It improves adoption because many dashboards fail not due to poor analysis, but because users are not confident in interacting with them. This page directly addresses that problem by providing a built-in guide.

6) Help Page

![Help Page](Help-Page.png)

This page provides ownership and support details. It shows who created the dashboard and where users can reach out for questions, data issues, or improvement requests. Adding this page strengthens governance and improves credibility, especially in an organisational setting where dashboards must be maintained and trusted over time.

📢 5) Share
How I summarised and communicated findings

The dashboard communicates insight through:

A progressive page narrative (summary → demographics → geography → deep dive)

Consistent KPI placement so users learn the layout quickly

Clear benchmarking (national average) to make interpretation easy

Tooltips and interactive filtering for self-service exploration

Why this helps decision-making

This dashboard supports better decisions because it enables:

Evidence-based prioritisation: focus on regions below benchmark

Inclusion monitoring: identify demographic gaps (age/disability)

Faster reporting: stakeholders access answers without manual reports

Repeatable analysis: model can extend to more years in future

Stronger outcomes

Because the dashboard highlights where participation is uneven, it can support:

Targeted programmes for low-participation regions

More inclusive sport development strategy

Better distribution of resources and funding

✅ 6) Act
Action-driven results (how this leads to action)

The core action value comes from:

Identifying regions/local authorities underperforming vs the national baseline

Identifying demographic groups with low participation shares

Helping stakeholders decide where intervention is needed most
