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

## Data Source

1. Base dataset stored in Google Sheets
2. Imported via CSV connector in Power BI
3. Cleaned for date formats and text fields
4. No confidential data — purely demo dataset

## Project Purpose

1. This dashboard enables:
2. QA teams to monitor progress
3. Managers to identify bottlenecks
4. Stakeholders to evaluate execution quality
5. Data-driven decision making during release cycles

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

## Author

### Dipika Chandra
##### Data Analytics | Power BI | SQL | Python
linkedin.com/in/dipika-chandra-26a1a71a0

