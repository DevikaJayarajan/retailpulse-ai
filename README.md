# RetailPulse AI

RetailPulse AI is an end-to-end retail decision-intelligence project combining Australian household spending data with Melbourne pedestrian activity to identify market signals and priority locations for further commercial investigation.

The project covers:

- Australian Bureau of Statistics household spending analysis
- Melbourne pedestrian activity analysis
- Market and location KPI development
- Decision-priority scoring
- Tableau-ready datasets and dashboards
- AI-assisted management reporting with validation guardrails

## Business Question

How can a retail strategy team combine Australian consumer-spending trends with Melbourne pedestrian activity to identify emerging demand patterns, prioritise categories and locations for further investigation, and automate part of the recurring market-review process using AI?

## Data Sources

This project uses publicly available Australian government and City of Melbourne datasets.

### Australian Bureau of Statistics
- Monthly Household Spending Indicator — Australia
- Monthly Household Spending Indicator — Victoria

These datasets are used to analyse household spending trends, growth rates and Victoria's performance relative to Australia.

### City of Melbourne
- Pedestrian Counting System — Monthly Counts per Hour
- Pedestrian Counting System — Sensor Locations

These datasets are used to analyse pedestrian activity, location-level growth, footfall volume and weekday/weekend patterns.

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
9. Automated validation of AI outputs

### Analytical Flow

Raw Data → Quality Audit → Transformation → KPI Analysis → Signal Generation → Decision Priorities → Tableau-ready Outputs → AI Reporting & Validation
