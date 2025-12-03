# Power BI Test Execution & Quality Dashboard
This project contains an interactive analytics dashboard built in Microsoft Power BI to analyze software test execution across multiple releases, owners, nodes, and priorities.

## Key Dashboard Features

1. Total test volume & execution metrics
2. Execution % and pass rate calculation using DAX
3. Status distribution (Pass / Fail / Pending / Not Executed)
4. Workload breakdown by Owner & Node
5. Execution timeline using Last_Updated
6. Drill-down view of individual test records
7. Filtering by Owner, Release, Priority, Status

## DAX Measures used

Total Tests = COUNTROWS('TestCases')

Executed Tests =
CALCULATE(
    [Total Tests],
    'TestCases'[Status] IN {"Pass","Fail","Pending for Review"}
)

Pass Count =
CALCULATE(
    [Total Tests],
    'TestCases'[Status] = "Pass"
)

Fail Count =
CALCULATE(
    [Total Tests],
    'TestCases'[Status] = "Fail"
)

Execution % =
DIVIDE( [Executed Tests], [Total Tests] )

Pass Rate =
DIVIDE( [Pass Count], [Executed Tests] )

## Skills Demonstrated

1. Power BI — data visualization & report design
2. DAX — calculated metrics & KPIs
3. Data modeling — relationship & semantic layer
4. Data cleaning — date transformation & missing fields
5. Analytical insight — trend & performance analysis

## Data Source and workflows

1. Base dataset stored in Google Sheets
2. Imported via CSV connector in Power BI
3. Cleaned for date formats and text fields
4. No confidential data — purely demo dataset

### Data Workflow & Live Update Logic

The data entry is distributed across five individual Google Sheets — one for each engineer (Dipika, Amit, Swapnil, Varun, Priya). Each member updates their assigned test results independently in their respective sheet.

These individual sheets are linked to an aggregated master sheet using Google Sheet formulas, which automatically combines all entries with column validation and data consistency.

Power BI reads from this aggregated sheet as a single unified data source.
Whenever engineers update test cases in their own sheet:

✔ changes automatically propagate to the master sheet

✔ Power BI refreshes to reflect updated values

✔ KPIs, charts, and slicers update in real time

This simulates a collaborative QA execution system where multiple contributors work asynchronously but produce a centralized analytics view.

## Data Flow Diagram

           Engineer 1 (Dipika)  ┐
                                │
           Engineer 2 (Amit)    ┤
                                │
           Engineer 3 (Swapnil) ┤   Individual Data Input Sheets
                                │
           Engineer 4 (Varun)   ┤
                                │
           Engineer 5 (Priya)   ┘

                                ⬇  (Automated aggregation using Google Sheets formulas)

    ┌────────────────────────────────────────────────────────┐
    │                    Master Aggregated Sheet             │
    │      (live consolidated dataset of 1000 test records)  │
    └────────────────────────────────────────────────────────┘
                                ⬇
                      Connected via Web CSV connector
                                ⬇
    ┌────────────────────────────────────────────────────────┐
    │                        Power BI                        │
    │ ┌─────────┬──────────┬──────────┬──────────┬─────────┐ │
    │ │ KPIs    │ Donut    │ Workload │ Trend    │ Table   │ │
    │ │ (DAX)   │ Chart    │ by Owner │ Over Time│ View    │ │
    │ └─────────┴──────────┴──────────┴──────────┴─────────┘ │
    │                                                        │
    │ Real-time updates reflect new test data instantly      │
    └────────────────────────────────────────────────────────┘

    Each engineer updates their own sheet independently. These five sheets feed into the master aggregated sheet using formula-based synchronization. Power BI is connected to this unified dataset, enabling real-time updates and automatically refreshed analytics.

## Project Purpose

### Real–World Context (Ericsson Experience Simulation)

This dashboard simulates the type of QA test tracking, execution monitoring, and performance reporting that I previously participated in during my time at Ericsson. While the dataset here is anonymized and self-generated, the workflow, structure, and analytical process closely mirror the real-world test execution and reporting cycles used in telecom network validation and live node activities.

This dashboard enables:
1. QA teams to monitor progress
2. Managers to identify bottlenecks
3. Stakeholders to evaluate execution quality
4. Data-driven decision making during release cycles

##### This project is an independent self–driven analytics initiative, simulating real QA execution reporting used in enterprise environments.

## Final Result

This project demonstrates the ability to:

1. analyze and transform real-world datasets
2. build KPI-driven Power BI dashboards
3. write and apply DAX measures effectively
4. handle date hierarchies & calendar intelligence
5. design visually intuitive analytical interfaces
6. uncover actionable insights from operational data
7. structure data models for analytics use cases

## How to View the Dashboard

Screenshots are included in /screenshots/ directory.
Interactive PBIX file will be available upon request.

## Repository Structure

    ├── README.md
    ├── screenshots/
    │   ├── dashboard-full.png
    │   ├── donut-status.png
    │   └── owner-workload.png
    └── dataset/
        └── sample_test_data.csv

## Author

### Dipika Chandra
##### Data Analytics | Power BI | SQL | Python
linkedin.com/in/dipika-chandra-26a1a71a0

