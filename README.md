# m
# Marketing Geo Experiment – Paid Social Incrementality

## Project Overview

This project designs a geographic marketing experiment to evaluate the impact of increasing paid-social advertising spend.

The experiment uses historical state-level data to identify suitable treatment and comparison markets and evaluates whether a planned increase in paid-social spend can detect a 2.5% increase in finance net revenue.

The project follows the requirements of the supplied Geo Experiment case study and uses GeoLift / GeoX experiment-design principles.

## Business Problem

A fictional online retailer operates across 16 U.S. states.

The business wants to test a:

* **40% increase in daily paid-social spend**
* **Experiment period:** June 1, 2026 – June 28, 2026
* **Primary KPI:** Finance net revenue
* **Planning effect:** 2.5% increase in combined treatment-state revenue
* **Maximum incremental spend:** USD 300,000
* **Treatment states:** 2–4 states
* **Required treatment revenue share:** 12%–25%

The objective is to identify suitable treatment states and a comparison pool while considering historical revenue patterns, operational events, audience overlap and spending constraints.

## Project Objectives

1. Assess the quality of the supplied marketing and revenue data.
2. Identify suitable treatment states.
3. Construct an appropriate comparison/donor pool.
4. Verify the revenue-share and budget constraints.
5. Examine historical treatment and comparison trends.
6. Construct a synthetic-control diagnostic.
7. Evaluate alternative treatment combinations.
8. Identify operational and methodological risks.
9. Provide a recommendation for the proposed experiment.

## Data

The project uses four worksheets from the supplied Excel file:

### 1. Markets

Contains:

* State eligibility
* Delivery groups
* Planned BAU daily paid-social spend
* Audited 28-day revenue

### 2. Daily Metrics

Contains historical daily:

* Finance net revenue
* Orders
* Paid-social spend
* Platform-attributed revenue
* Revenue-feed completeness

### 3. Audience Overlap

Contains pairwise cross-border audience overlap between states.

### 4. Operations Calendar

Contains known historical and future operational events affecting individual states or all markets.

## Methodology

### Step 1 – Data Preparation

The analysis includes:

* Missing-value inspection
* Duplicate detection
* State-code standardization
* Date validation
* Finance-revenue quality checks

### Step 2 – Treatment Selection

Candidate states are evaluated using:

* Eligibility
* Revenue-share constraint
* Delivery-group restrictions
* Incremental-spend constraint
* Operational-calendar information
* Audience-overlap information
* Historical revenue behavior

### Step 3 – Comparison Pool

Untreated states are evaluated as potential comparison/donor markets.

The primary comparison pool used in the analysis is:

```text
OH, MO, IN, TN, KY, CO, NC, SC
```

### Step 4 – Synthetic-Control Diagnostic

A weighted synthetic control is constructed using historical finance net revenue.

The diagnostic evaluates:

* Pre-test MAPE
* Correlation
* Treatment versus synthetic-control trends
* Historical residual variation

This diagnostic is used to support experiment planning and should not be interpreted as an official GeoLift package output.

## Selected Experiment Design

### Treatment States

```text
Pennsylvania (PA)
Michigan (MI)
Wisconsin (WI)
```

### Comparison Pool

```text
Ohio (OH)
Missouri (MO)
Indiana (IN)
Tennessee (TN)
Kentucky (KY)
Colorado (CO)
North Carolina (NC)
South Carolina (SC)
```

### Experiment

| Parameter               | Value                |
| ----------------------- | -------------------- |
| Treatment states        | PA, MI, WI           |
| Experiment period       | June 1–28, 2026      |
| Paid-social change      | +40% over BAU        |
| Primary KPI             | Finance net revenue  |
| Planning effect         | 2.5%                 |
| Incremental spend       | Approximately $246K  |
| Maximum spend           | $300K                |
| Treatment revenue share | Approximately 14.22% |

## Key Analysis

The selected treatment states satisfy the required revenue-share constraint and remain below the maximum incremental-spend limit.

The historical treatment aggregate is compared with a synthetic control constructed from untreated states.

The analysis also considers operational events and audience overlap because these factors can affect the validity of the comparison.

## Key Risks

Important risks considered include:

* Missing finance-revenue observations
* Duplicate records
* Revenue-feed incidents
* Operational changes in control states
* Audience spillover
* Campaign targeting leakage
* Conversion lag
* Sensitivity to donor-state selection
* Changes in the relationship between treatment and comparison markets

## Project Structure

```text
marketing-geo-experiment/
│
├── README.md
├── data/
│   └── Data.xlsx
├── notebooks/
│   └── marketing_geo_experiment.ipynb
├── report/
│   └── Marketing_Geo_Experiment_Project.docx
├── outputs/
│   ├── data_quality.png
│   ├── audited_revenue.png
│   ├── synthetic_control.png
│   ├── candidate_fit.png
│   └── marketing_project_key_metrics.csv
└── requirements.txt
```

## Tools & Technologies

* Python
* Pandas
* NumPy
* Matplotlib
* SciPy
* Jupyter Notebook
* Excel
* GeoLift / GeoX experiment-design concepts

## Conclusion

The analysis produces a feasible planning design using Pennsylvania, Michigan and Wisconsin as treatment states, with an untreated comparison pool constructed from historical state-level revenue behavior.

The design satisfies the stated revenue-share and incremental-spend constraints. Final launch should be conditional on the formal GeoLift/GeoX validation and power/design analysis required for the experiment.

## References

* GeoLift – Meta
* Meridian GeoX – Google
* Supplied Geo Experiment case study and synthetic dataset
