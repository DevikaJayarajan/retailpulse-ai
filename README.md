# RetailPulse AI

RetailPulse AI is an end-to-end retail decision-intelligence project combining Australian household spending data with Melbourne pedestrian activity to identify market signals and priority locations for further commercial investigation.

The project covers:

- Australian Bureau of Statistics household spending analysis
- Melbourne pedestrian activity analysis
- Market and location KPI development
- Decision-priority scoring
- Tableau-ready datasets and dashboards
- AI-assisted management reporting with validation guardrails

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

## Key Features

- Automated cleaning and transformation of ABS household spending data
- Validation of monthly time-series continuity and missing values
- Comparison of Victoria household spending growth against Australia
- Exact calendar-month matching for pedestrian month-on-month and year-on-year analysis
- Sensor coverage validation to avoid misleading pedestrian growth calculations
- Market and location signal generation using defined business rules
- Priority scoring for further commercial investigation
- Tableau-ready analytical outputs
- AI-generated management summary with reporting guardrails
- Automated checks to validate AI output structure, wording and selected numeric values

## Repository Structure

```text
retailpulse-ai/
├── data/
│   ├── raw/
│   └── processed/
├── notebooks/
│   └── retailpulse_ai_analysis.ipynb
├── reports/
│   ├── ai_management_summary.txt
│   └── ai_validation_results.csv
└── README.md
```
## Project Outputs

The project produces the following decision-support outputs:

- `spending_kpis.csv` — spending growth and trend metrics
- `spending_comparison.csv` — Victoria vs Australia category comparison
- `latest_market_priorities.csv` — latest market signals and investigation priorities
- `pedestrian_kpis.csv` — location-level pedestrian KPIs
- `latest_location_priorities.csv` — latest validated location signals and priorities
- `ai_management_summary.txt` — AI-assisted management summary
- `ai_validation_results.csv` — automated checks used to validate the AI-generated summary

The outputs are designed to support further commercial investigation rather than direct store-opening or investment decisions.

## Tech Stack

- Python
- Pandas
- NumPy
- Jupyter Notebook
- Tableau
- OpenAI API
- CSV / Excel data processing
- GitHub

## Key Findings

### Market Signals
- Victoria showed strong year-on-year growth across several household spending categories in the latest reporting period.
- Categories such as Miscellaneous goods and services, Clothing and footwear, and Food were identified as high-priority areas for further commercial investigation.
- Strong growth alone was not treated as sufficient evidence; Victoria's performance was also compared with Australia to provide broader context.

### Location Signals
- Several Melbourne pedestrian locations showed strong validated year-on-year growth while also maintaining meaningful footfall volumes.
- Locations were prioritised using both growth and activity scale rather than ranking solely by percentage growth.
- Coverage validation was applied before year-on-year comparisons to reduce the risk of misleading signals caused by incomplete sensor observations.

### Decision Intelligence
Market and location evidence are treated as independent signals and brought together only at the decision-support stage. The outputs identify where further commercial investigation may be warranted rather than making direct store-opening or investment recommendations.

## Limitations

- Household spending and pedestrian activity are separate datasets with different geographic and time structures.
- The analysis does not assume that changes in pedestrian activity cause changes in spending, or vice versa.
- Pedestrian counts represent activity around sensor locations and should not be interpreted as store-level sales or customer conversion.
- Some pedestrian sensors have incomplete historical coverage, so year-on-year comparisons are only used when both the current and prior-year periods meet the defined coverage threshold.
- Priority labels are analytical decision-support signals designed to identify areas that warrant further commercial investigation.
- External factors such as demographics, competition, rent, store economics and local trading conditions would need to be incorporated before making a real investment decision.

## How to Run the Project

1. Clone or download this repository.
2. Open `notebooks/retailpulse_ai_analysis.ipynb`.
3. Ensure the required Python libraries are installed.
4. Place the required raw data files in the corresponding folders under `data/raw/`.
5. Run the notebook from top to bottom.
6. Generated analytical outputs will be saved under `data/processed/` and `reports/`.

### Required External Raw File

The City of Melbourne hourly pedestrian counts file is not stored in this repository because it is approximately 120 MB.

Download:

`pedestrian-counting-system-monthly-counts-per-hour.csv`

and place it in:

```text
data/raw/City of Melbourne Pedestrian Counting System/
```
## AI-Assisted Reporting & Validation

The project includes an AI-assisted reporting layer that converts validated analytical outputs into a concise management summary.

The AI component is intentionally used as a reporting layer rather than as the source of calculations or KPI logic.

Key controls include:

- Only validated market and location outputs are provided to the AI
- The prompt explicitly prevents invented calculations and causal claims
- Market and pedestrian evidence are treated as independent evidence streams
- The AI is instructed not to make direct store-opening recommendations
- Automated checks verify required sections, wording constraints and selected numeric values
- A fallback management summary is available if the API call is unavailable

This approach demonstrates how generative AI can support analytics communication while keeping the underlying calculations deterministic and auditable.

## Future Improvements

Potential extensions include:

- Adding demographic and socioeconomic data to strengthen location analysis
- Incorporating competitor locations and proximity measures
- Adding rental or commercial property data for deeper site evaluation
- Automating scheduled data refreshes and reporting
- Expanding the AI reporting layer into a repeatable stakeholder briefing workflow
- Deploying the analytical pipeline using cloud-based data and automation tools

## Author

**Devika Jayaraj**  
Master of Data Science, RMIT University  
Melbourne, Australia

Interested in Data Analytics, Business Intelligence, Data Engineering and AI-enabled analytics.

Connect with me on LinkedIn: [linkedin.com/in/devika-jayaraj](https://www.linkedin.com/in/devika-jayaraj)
