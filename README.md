# Aircraft Risk Analysis: Identifying Low-Risk Aircraft for Business Expansion
# Overview
The project is an inquiry into the aircraft risk profile in order to assist a company venturing into the aviation industry. Based on past data on aviation-related accidents, the analysis is used to compare which makes and models of aircraft are the least risky in terms of operations. The notebook includes data cleanup, transformation, and exploratory risk analysis to provide practical solution insights on aircraft safety.

# Business Understanding
The company plans to purchase and operate aircraft for both commercial and private purposes but lacks knowledge of aviation risk factors.
The project addresses this business problem:

“Which aircraft types demonstrate the lowest risk and are safest for investment and operation?”

Key Objectives:

Identify aircraft makes and models with fewer and less severe accidents.

Evaluate operational purposes (commercial, private, instructional, etc.) linked to higher incident frequency.

Develop a Severity Index combining injury outcomes to rank aircraft by overall safety.

Insights from this analysis will guide the company’s aviation division on which aircraft to prioritize for purchase.

# Data Understanding and Analysis
The dataset (Aviation_Data.csv) includes extensive historical aviation accident records with fields such as:

Categorical: Make, Model, Aircraft Damage, Purpose of Flight, FAR Description, Country

Numerical: Fatal, Serious, Minor Injuries, Number of Engines, Latitude, Longitude

Datetime: Event.Date

# Data Preparation

Removed duplicates and standardized column formatting.

Converted date fields to proper datetime types.

Handled missing data by:

Dropping rows missing key identifiers (Make, Model)

Replacing categorical missing values with "Unknown"

Filling numeric injury counts and engine data using median imputation grouped by make/model.

Normalized categorical fields for consistency (str.strip().str.title()).

Feature Engineering

Severity_Index = Weighted injury score combining fatal, serious, and minor injuries:
Severity_Index = (Fatal * 3) + (Serious * 2) + (Minor * 1)

Any_Fatal = Binary indicator showing whether any fatalities occurred.

Aggregated risk metrics per aircraft Make + Model, computing:

Total accidents

Mean severity

Total fatalities and injuries

# Key Analyses

Damage Severity Analysis – Distribution of aircraft damage levels across makes and models.

Operational Purpose Risk – Compared accident frequency by flight type (Private, Commercial, Instructional, Agricultural).

Aircraft Model Comparison – Identified aircraft with the lowest weighted severity and accident frequency.

Visualization (Tableau-ready) – Bar charts, heatmaps, and dashboards illustrating severity vs frequency patterns.

# View Interactive Dashboard
https://public.tableau.com/app/profile/raphael.ndemo/viz/AircraftsoperationalRisksAnalysis/AircraftSafetyRiskDashboardData-DrivenInsightsforStrategicFleetDecisions?publish=yes

# Conclusion

The analysis provides a data-driven safety ranking of aircraft that the company can use to inform purchasing and risk management decisions.

