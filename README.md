# RetailPulse AI

RetailPulse AI is an end-to-end retail decision-intelligence project combining Australian household spending data with Melbourne pedestrian activity to identify market signals and priority locations for further commercial investigation.

## Executive Summary

- **Clothing and footwear, Food, and Miscellaneous goods and services** were identified as the strongest **High Priority market categories** in the latest reporting period.
- **Little Collins St-Swanston St (East)** was one of the strongest High Priority location signals, combining approximately **643,499 monthly pedestrian movements** with **20.55% validated YoY growth**.
- **Recreation and culture** recorded the fastest Victorian category growth at approximately **9.05% YoY**, but remained **Medium Priority** because Victoria underperformed Australia by approximately **1.76 percentage points**.
- The outputs are intended to identify areas that **warrant further commercial investigation**, rather than make direct store-opening or investment recommendations.

The project covers:

- Australian Bureau of Statistics household spending analysis
- Melbourne pedestrian activity analysis
- Market and location KPI development
- Decision-priority scoring
- Tableau-ready datasets and dashboards
- AI-assisted management reporting with validation guardrails

## Contents

- [Executive Summary](#executive-summary)
- [Interactive Dashboards](#interactive-dashboards)
- [Dashboard Preview](#dashboard-preview)
- [Business Question](#business-question)
- [Data Sources](#data-sources)
- [Analytical Boundary](#analytical-boundary)
- [Project Workflow](#project-workflow)
- [Key Features](#key-features)
- [Repository Structure](#repository-structure)
- [Project Outputs](#project-outputs)
- [Tech Stack](#tech-stack)
- [Key Findings](#key-findings)
- [Limitations](#limitations)
- [How to Run the Project](#how-to-run-the-project)
- [AI-Assisted Reporting & Validation](#ai-assisted-reporting--validation)
- [Future Improvements](#future-improvements)

## Interactive Dashboards

Explore the RetailPulse AI dashboards on Tableau Public:

[View RetailPulse AI - Retail Decision Intelligence](https://public.tableau.com/app/profile/devika.jayaraj/viz/RetailPulseAI-RetailDecisionIntelligence/Dashboard1)

The published workbook includes navigation between:

- Market Overview
- Location Intelligence
- Decision Intelligence

## Dashboard Preview

### Market Overview

![Market Overview](tableau/market_overview.png)

### Location Intelligence

![Location Intelligence](tableau/location_intelligence.png)

### Decision Intelligence

![Decision Intelligence](tableau/decision_intelligence.png)

## Business Question

How can a retail strategy team combine Australian consumer-spending trends with Melbourne pedestrian activity to identify emerging demand patterns, prioritise categories and locations for further investigation, and automate part of the recurring market-review process using AI?

## Data Sources

This project uses publicly available Australian government and City of Melbourne datasets.

### Australian Bureau of Statistics

- [Monthly Household Spending Indicator — July 2026](https://www.abs.gov.au/statistics/economy/finance/monthly-household-spending-indicator/jul-2026#data-downloads) — Australian Bureau of Statistics

Source credit: **Australian Bureau of Statistics (ABS), Monthly Household Spending Indicator.**

### City of Melbourne

- [Pedestrian Counting System — Counts per Hour](https://data.melbourne.vic.gov.au/explore/dataset/pedestrian-counting-system-monthly-counts-per-hour/export/) — City of Melbourne Open Data
- [Pedestrian Counting System — Sensor Locations](https://data.melbourne.vic.gov.au/explore/dataset/pedestrian-counting-system-sensor-locations/export/) — City of Melbourne Open Data

Source credit: **City of Melbourne Open Data, Pedestrian Counting System.**

> Note: The raw hourly pedestrian counts file is approximately 120 MB and is not stored in this GitHub repository. The processed datasets used in the analysis are included in `data/processed/`.

## Analytical Boundary

Spending and pedestrian datasets are analysed separately and combined only at the decision-support stage.

The analysis does not claim that spending changes cause pedestrian changes, or that pedestrian activity directly represents store sales.

## Project Workflow

The project follows an end-to-end analytics workflow:

1. Raw data collection
2. Data quality audit
3. Data transformation
4. KPI analysis
5. Market and location signal generation
6. Decision-priority scoring
7. Tableau-ready dataset creation
8. AI-assisted management reporting
9. Automated validation of reporting outputs

### Analytical Flow

Raw Data → Quality Audit → Transformation → KPI Analysis → Signal Generation → Decision Priorities → Tableau-ready Outputs → AI Reporting & Validation

## Key Features

- Automated cleaning and transformation of ABS household spending data
- Validation of monthly time-series continuity and missing values
- Comparison of Victoria household spending growth against Australia
- Exact calendar-month matching for pedestrian month-on-month and year-on-year analysis
- Sensor coverage validation to reduce misleading pedestrian growth calculations
- Market and location signal generation using defined business rules
- Priority scoring for further commercial investigation
- Tableau-ready analytical outputs
- AI-assisted management reporting with validation guardrails
- Automated checks to validate report structure, prohibited recommendation language and numeric values directly against validated analytical tables
- Guardrail stress test using a deliberately unsafe store-opening recommendation to confirm that unsupported recommendations are detected

## Repository Structure

```text
retailpulse-ai/
├── data/
│   ├── raw/
│   │   ├── ABS Monthly Household Spending Indicator/
│   │   └── City of Melbourne Pedestrian Counting System/
│   └── processed/
├── notebooks/
│   └── retailpulse_ai_analysis.ipynb
├── reports/
│   ├── ai_management_summary.txt
│   ├── ai_validation_results.csv
│   └── ai_guardrail_test_results.csv
├── tableau/
│   ├── market_overview.png
│   ├── location_intelligence.png
│   └── decision_intelligence.png
├── .gitignore
├── README.md
└── requirements.txt
