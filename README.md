# Bank-Loan-Performance-Analysis-Dashboard
Interactive bank loan performance dashboard with SQL-backed KPIs for applications, funded amount, amount received, interest rate, DTI, and Good vs Bad loan analysis.

Bank Loan Report – Portfolio Performance & Risk Analytics
## Project Overview

This project builds an end-to-end Bank Loan Reporting and Analytics solution to monitor lending performance, portfolio health, and risk quality.

Using SQL for data preparation and Power BI for interactive dashboards, the report gives stakeholders a clear view of:

How much is being lent (funded amount)

How much is being repaid (amount received)

The quality of the loan book (Good vs Bad loans)

Trends across time, regions, borrower profiles, and loan characteristics

The core deliverable is a Bank Loan Report built to support informed, data-driven decisions in lending strategy and risk management.

## Objectives

The main objectives of this project are to:

Track Total Loan Applications and their Month-to-Date (MTD) and Month-over-Month (MoM) trends.

Measure Total Funded Amount (capital deployed) and Total Amount Received (cash inflow).

Monitor Average Interest Rate and Average Debt-to-Income Ratio (DTI) for portfolio risk and pricing.

Classify loans into Good Loans and Bad Loans using loan status, and compute quality KPIs.

Analyse performance across:

Time (monthly trends)

Geography (state)

Loan term

Employment length

Loan purpose

Home ownership

Provide a Details dashboard for loan-level drill-down and operational analysis.

## Dataset & Fields

The analysis is based on a bank loan dataset (loan-level data). Key fields include:

id – loan application ID

issue_date – loan issue date

loan_amount – funded principal

total_payment – total amount received from borrower

int_rate – interest rate

dti – debt-to-income ratio

loan_status – e.g., Fully Paid, Current, Charged Off

address_state – borrower’s state

term – loan term (e.g., 36, 60 months)

emp_length – borrower’s employment length

purpose – loan purpose (e.g., debt consolidation, credit card)

home_ownership – e.g., own, rent, mortgage

Note: Actual dataset file is not included here if it is proprietary – this repo focuses on logic, queries, and the reporting layer.

## Tech Stack

SQL – Data extraction, aggregation, MTD/PMTD metrics, and segment-wise summaries.

Power BI – Data model, measures, and interactive dashboards:

Bank Loan Report.pbix

Documentation – Query logic and data preparation steps:

Query_Document.docx

## KPI Framework (Dashboard 1 – Portfolio Performance)

Dashboard 1 provides a high-level performance summary, focusing on portfolio KPIs and trends.

Core KPIs

Total Loan Applications

Total number of loan applications.

MTD applications and MoM change vs previous month.

Total Funded Amount

Total principal disbursed as loans.

MTD funded amount and MoM change.

Total Amount Received

Total repayments collected from borrowers.

MTD collections and MoM change.

Average Interest Rate

Average interest rate across the portfolio.

MTD vs previous month to understand pricing trends.

Average DTI (Debt-to-Income Ratio)

Average borrower DTI, used as a proxy for financial stress.

Tracked MTD and compared MoM to monitor changes in borrower risk profile.

These KPIs together answer:

How fast are we growing? How much have we lent? How much have we collected? And at what risk/price?

## Good vs  Bad Loans – Portfolio Quality

Loans are classified into two quality buckets based on loan_status:

Good Loans:

Status: Fully Paid, Current

Bad Loans:

Status: Charged Off

Good Loan KPIs

Good Loan Application % – Percentage of total applications that are Good Loans.

Good Loan Applications – Count of applications that are Fully Paid or Current.

Good Loan Funded Amount – Total principal funded to Good Loans.

Good Loan Total Received Amount – Total repayments collected from Good Loans.

These show the healthy, revenue-generating portion of the portfolio.

Bad Loan KPIs

Bad Loan Application % – Percentage of applications that ended up Charged Off.

Bad Loan Applications – Count of Charged Off loans.

Bad Loan Funded Amount – Principal associated with Charged Off loans (capital at risk/loss).

Bad Loan Total Received Amount – Recoveries from Bad Loans.

These metrics quantify default risk, portfolio losses, and recovery performance.

## Loan Status Grid View

A Loan Status Grid summarises key indicators by loan_status:

For each status (e.g., Fully Paid, Current, Charged Off):

Total loan applications

Total funded amount

Total amount received

MTD funded amount

MTD amount received

Average interest rate

Average DTI

This grid helps answer:

How do Current and Fully Paid loans compare to Charged Off loans in terms of interest rate and DTI?

Which statuses contribute most to outstanding exposure vs cash inflow?

## Overview Dashboard (Dashboard 2 – Visual Analytics)

Dashboard 2 focuses on multi-dimensional analysis using visual charts.

1. Monthly Trends by Issue Date (Line Chart)

Metrics:

Total Loan Applications

Total Funded Amount

Total Amount Received

X-axis: Month (by issue date)

Used to spot seasonality, growth patterns, and divergence between funding and collections.

2. Regional Analysis by State (Filled Map)

Metrics: Applications, Funded Amount, Amount Received

Dimension: address_state

Helps to:

Identify high-volume states and under-penetrated regions.

Compare regional funding vs collections, highlighting possible risk hotspots.

3. Loan Term Analysis (Donut Chart)

Metrics: Applications, Funded Amount, Amount Received

Segments: term (e.g., 36 vs 60 months)

Used to understand:

The distribution of exposure across different tenors.

Whether longer-term loans dominate funded amount or pose higher repayment risk.

4. Employee Length Analysis (Bar Chart)

Metrics: Applications, Funded Amount, Amount Received

Dimension: emp_length categories

Supports questions like:

Do borrowers with longer employment history receive larger loans or perform better?

Are defaults more concentrated among those with shorter tenure?

5. Loan Purpose Breakdown (Bar Chart)

Metrics: Applications, Funded Amount, Amount Received

Dimension: purpose

Shows:

Which loan purposes drive most demand and exposure.

Potential risk patterns by purpose (e.g., debt consolidation vs credit card refinancing).

6. Home Ownership Analysis (Tree Map)

Metrics: Applications, Funded Amount, Amount Received

Dimension: home_ownership (own, rent, mortgage)

Allows analysis of:

How ownership status correlates with loan amounts and repayment performance.

Which segments (owners, renters, mortgagors) are most significant for the bank.

## Details Dashboard (Dashboard 3 – Loan-Level Drill-Down)

The Details dashboard is a loan-level explorer that consolidates:

Loan ID, Issue Date

State, Term, Purpose, Home Ownership

Loan Amount, Total Amount Received

Interest Rate, DTI

Loan Status, Good/Bad Loan flag

With filters for:

Date range

Loan status (including Good vs Bad)

State

Purpose

Term

Home ownership

Employment length

It supports:

Deep-dive analysis of high-risk segments (e.g., high DTI + Charged Off).

Operational use by risk and collections teams.

Export of filtered subsets for modelling or further analysis.

## Analytical Highlights

Established a standard KPI framework for loan monitoring (applications, funding, collections, pricing, DTI).

Created a Good vs Bad Loan lens to quantify portfolio quality and losses.

Enabled time-, region-, and segment-wise analysis via Power BI dashboards.

Built a clear, auditable logic layer using SQL, making metrics reproducible and extendable.
