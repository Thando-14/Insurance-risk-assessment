# 🚗 Insurance Fraud and Risk Assessment System

### Business Intelligence | Microsoft Power BI | Risk Analytics

## 📌 Project Overview

The **Insurance Fraud and Risk Assessment System** is a Business Intelligence (BI) project developed to support motor insurance claim risk assessment and potential fraud investigation in the Indian motor insurance sector.

The project uses a synthetic insurance dataset containing **53,503 records** to explore insurance portfolio trends, identify risk indicators, and prioritize records that may require further investigation.

Using Microsoft Power BI, Power Query, and DAX, the system transforms insurance data into an interactive analytical solution that combines portfolio exploration, rules-based risk scoring, and executive-level reporting.

The solution is designed to help insurance analysts and Special Investigation Units (SIUs) prioritize suspicious records, improve risk visibility, and support more consistent, data-driven decisions.

**Important:** The system identifies potentially high-risk records for human review. It does not confirm fraud or automatically reject insurance claims.

## Project Objectives

- Analyze insurance portfolio data to identify patterns in claim history and risk indicators.
- Classify records into Low, Medium, and High risk categories.
- Develop a transparent, rules-based risk assessment framework.
- Identify high-risk records that meet additional criteria for potential fraud review.
- Visualize portfolio performance, claims history, and risk distributions.
- Develop an interactive Power BI dashboard for analytical and executive reporting.
- Support investigation prioritization and more efficient allocation of review resources.
- Identify data quality issues that require further validation.

## Tools and Technologies

| Tool | Purpose |
|---|---|
| Microsoft Power BI | Interactive dashboards and reporting |
| Power Query | Data cleaning, transformation, and ETL |
| DAX | KPI calculations, risk measures, and classifications |
| Synthetic insurance dataset | Portfolio exploration and risk assessment |
| Data visualization | Risk distributions, claims analysis, and executive insights |

## Dataset Overview

The project uses a synthetic insurance dataset named `data_synthetic`, containing **53,503 records and 30 original variables**.

The dataset covers the following analytical areas:

- **Customer demographics:** Age, income level, credit score, geographic information, and segmentation group.
- **Policy information:** Policy type, policy start date, renewal date, premium amount, and coverage amount.
- **Claims history:** Claim History and Previous Claims History.
- **Driving records:** Clean, Minor Violations, Major Violations, DUI, and Accident.
- **Risk indicators:** Risk Profile and Coverage-to-Income ratio.

### Data preparation

Power Query was used to assess data quality, prepare data types, and create analytical fields.

| Data quality check | Result |
|---|---:|
| Total records | 53,503 |
| Missing values | 0 |
| Completely duplicated rows | 0 |
| Unique customer IDs | 40,259 |
| Records associated with repeated customer IDs | 23,888 |
| Renewal dates before policy start dates | 2,247 |

A unique Record ID was used to identify individual observations, while Customer ID was retained as a business identifier.

Records with renewal dates preceding policy start dates were flagged for data quality review rather than automatically treated as fraudulent.

### Derived fields

- Age Group
- Credit Score Category
- Policy Duration Days
- Coverage to Income
- Data Quality Flag
- Risk Score
- Risk Band
- Potential Fraud Indicator

## Power BI Dashboard

The solution contains three coordinated report pages.

### 1. Insurance Portfolio Exploratory Analysis

This page provides an overview of the insurance portfolio and its underlying patterns.

Key visualizations include:

- Total records and unique customer IDs.
- Total claim history and financial portfolio measures.
- Records by policy type.
- Claims by geographic location.
- Records by driving record category.
- Average premium by age group.
- Records by credit score category.
- Claims by customer segmentation group.
- Income level versus total coverage.
- A policy type and driving record summary matrix.

Interactive slicers allow users to filter the analysis by geography, segmentation group, driving record, age group, and policy type.

### 2. Fraud Detection and Risk Assessment

This page focuses on rules-based risk classification and investigation prioritization.

Key features include:

- Risk Score calculation using six risk indicators.
- Low, Medium, and High risk classifications.
- Potential Fraud Review identification.
- A record-level investigation queue.
- Descending risk-score ordering.
- Visibility of contributing risk indicators.
- Data quality flags alongside risk outputs.
- Conditional formatting to distinguish risk bands.

The investigation queue is intended to support human assessment of records that meet the defined risk criteria.

### 3. Executive Dashboard

The executive dashboard consolidates the portfolio and risk findings into a management-level overview.

Its components include:

- Portfolio summary KPIs.
- Records by risk band.
- High-risk records by driving record.
- Potential reviews by policy type.
- Top geographic locations by review count.
- Interactive filters for geography, policy type, segmentation group, risk band, and driving record.
- Navigation between dashboard pages.

This view helps stakeholders understand portfolio composition, risk distribution, and potential investigation workload.

## Risk Assessment Methodology

The project implements a transparent, rules-based risk scoring framework using six indicators:

1. Claim History
2. Previous Claims History
3. Credit Score
4. Driving Record
5. Risk Profile
6. Coverage-to-Income ratio

Each indicator contributes up to two points under the documented scoring rules, producing a total risk score ranging from **0 to 12**.

### Risk classification

| Risk band | Risk score | Interpretation |
|---|---:|---|
| Low | 0–3 | Routine processing under standard controls |
| Medium | 4–6 | Additional verification may be appropriate |
| High | 7–12 | Prioritize for human review |

### Potential Fraud Review criteria

A record enters the Potential Fraud Review queue only when both conditions are met:

- The record is classified as High risk, with a risk score of 7 or higher.
- At least one of the defined strong risk triggers is present.

The strong triggers are:

- Coverage exceeds 10 times the income level.
- Claim History is 4 or more.
- Previous Claims History is 2 or more.
- Driving Record is DUI or Major Violations.

This additional condition distinguishes the investigation queue from the overall High-risk population.

The framework is rules-based rather than a trained machine learning model because the synthetic dataset does not contain verified fraud outcome labels.

## Key Results

| Metric | Result |
|---|---:|
| Total records | 53,503 |
| Unique customer IDs | 40,259 |
| Total claim history count | 134,955 |
| Total premiums | 161,777,152 |
| Average premium | 3,023.70 |
| Total coverage | 26,354,549,988 |
| Average coverage | 492,580.79 |
| Average credit score | 673.32 |
| Average risk score | 5.87 |

### Risk classification results

| Risk category | Records | Percentage |
|---|---:|---:|
| High risk | 20,139 | 37.64% |
| Medium risk | 26,804 | 50.10% |
| Low risk | 6,560 | 12.26% |
| Potential Fraud Review | 19,895 | 37.18% |

The three risk bands account for all 53,503 records. Potential Fraud Review is a subset of High-risk records, not a separate risk category.

### Policy type distribution

| Policy type | Records | Portfolio share |
|---|---:|---:|
| Group | 18,255 | 34.12% |
| Business | 13,986 | 26.14% |
| Family | 12,424 | 23.22% |
| Individual | 8,838 | 16.52% |

Group policies represent the largest category in the dataset, followed by Business, Family, and Individual policies.

These results describe the supplied synthetic dataset and should not be interpreted as estimates of actual fraud prevalence in the insurance industry.

##  Testing and Evaluation

The project documentation reports successful checks for:

- Record count reconciliation.
- Claim history aggregation.
- Risk-band classification totals.
- Potential Fraud Review rule consistency.
- Investigation queue filtering and sorting.
- Conditional formatting.
- Dashboard slicer interaction.
- Page navigation.
- Policy date anomaly handling.

These checks demonstrate consistency of the documented calculations and dashboard behavior. They do not establish predictive accuracy or confirm that flagged records are fraudulent.

##  Limitations

The following limitations are important when interpreting the results:

- **Synthetic data:** The dataset may not reflect the patterns and relationships found in real insurance operations.
- **No verified fraud labels:** Confirmed fraud detection accuracy, precision, recall, and false-positive rates cannot be calculated.
- **No monetary claim amount field:** Claim History represents claim activity frequency, not the monetary value of claims.
- **No confirmed investigation outcomes:** The project cannot establish how many flagged records represent actual fraud.
- **No demonstrated external evidence verification:** The documented implementation does not demonstrate automated verification of police reports, dashcam footage, or repair invoices.
- **Rules-based scoring:** Risk points and thresholds have not been calibrated against confirmed historical outcomes.
- **No measured financial savings:** Actual fraud losses prevented, savings achieved, and improvements in claim turnaround time have not been established.

The system should therefore be treated as an analytical decision-support tool, with human review required for flagged records.

##  How to Use the Project

1. Clone or download the repository.
2. Install Microsoft Power BI Desktop.
3. Open the project `.pbix` file, if included in the repository.
4. Update the data source path if required.
5. Refresh the dataset.
6. Explore the Portfolio Exploratory Analysis page.
7. Review the risk classifications and Potential Fraud Review queue.
8. Use the Executive Dashboard to examine portfolio and investigation patterns.

The Power BI project file and original dataset must be included separately for users to reproduce the dashboard. They were not included with the report document used to prepare this README.

##  Future Enhancements

Potential improvements identified in the project include:

- Calibrating risk scores and thresholds against historical claims with confirmed investigation outcomes.
- Integrating monetary claim amounts and exact incident dates.
- Incorporating vehicle details, repair garage identifiers, and supporting documentation.
- Adding an investigator feedback mechanism to distinguish confirmed fraud from false positives.
- Monitoring review volumes against investigation capacity.
- Improving upstream data validation and identifier management.
- Implementing role-based access controls and privacy safeguards before operational deployment.
- Evaluating supervised machine learning models once reliable fraud outcome labels become available.


## 🎓 Academic Context

This project was developed as part of the **Advanced Diploma in ICT in Business Intelligence**.

**Project title:** Insurance Fraud and Risk Assessment System  
**Module:** BIPJ702   
**Institution:** Durban University of Technology

---

*This project demonstrates how Business Intelligence, data preparation, DAX, and interactive Power BI dashboards can support insurance portfolio analysis and transparent, rules-based risk assessment.*

