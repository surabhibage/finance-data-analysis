# Finance Data Analysis

This repository contains a personal finance analytics project focused on understanding income, expenses, savings, debt, and financial behavior across different demographic and regional segments. The project uses a synthetic personal finance dataset and a PySpark-based data processing workflow to generate summary tables and visual insights.

## Overview

The analysis explores questions such as:

- How do income and savings vary by gender and region?
- What are the financial patterns by education level?
- How do loan amounts and EMI obligations differ across loan types?
- How do savings trends change over time relative to inflation-like pressure?

The project combines data cleaning, transformation, aggregation, and chart generation to support financial analysis and reporting.

## Repository Structure

```text
finance-data-analysis/
├── final_sprint/
│   ├── code/
│   │   └── final-run-script.py
│   ├── data/
│   │   └── synthetic_personal_finance_dataset.csv
│   └── output/
│       ├── education_agg/
│       ├── joined_table/
│       ├── loan_agg/
│       ├── top_savings/
│       ├── skinny_table/
│       ├── mean_income_male_female_global.png
│       ├── median_income_by_region_usd.png
│       └── na_savings_inflation_rising.png
├── old_work/
│   ├── README.md
│   ├── run_pa4.sh
│   └── deliverables/
├── .gitignore
└── README.md
```

## Dataset

The project uses a synthetic personal finance dataset containing records with attributes such as:

- user ID
- age
- gender
- education level
- employment status
- job title
- monthly income
- monthly expenses
- savings
- loan amount
- monthly EMI
- loan type
- loan interest rate
- region
- record date

The dataset is stored here:

- `final_sprint/data/synthetic_personal_finance_dataset.csv`

## Project Workflow

The main analysis logic is implemented in:

- `final_sprint/code/final-run-script.py`

This script performs the following tasks:

1. Loads the finance dataset into a Spark DataFrame.
2. Cleans and normalizes column names and values.
3. Converts date and numeric fields into usable analysis formats.
4. Standardizes regional currency values.
5. Aggregates data by education level and loan type.
6. Joins relevant financial metrics for summary exploration.
7. Identifies top-savings records and a reduced “skinny table”.
8. Generates charts and saves them into the output directory.

## Key Outputs

The project generates analytical summaries and visualizations including:

- average income and spending by education level
- average loan metrics by loan type
- joined user-level financial summaries
- top savings rankings
- median income by region
- gender-based income comparison
- savings compared to inflation-adjusted savings over time

These outputs are saved under:

- `final_sprint/output/`

## Technologies Used

- Python
- PySpark
- Pandas
- Matplotlib
- Seaborn
- Google Cloud Storage

## Setup

To run the project, you will need:

- Python 3.x
- Java runtime (required by Spark)
- PySpark
- `matplotlib`
- `seaborn`
- `pandas`
- `google-cloud-storage`

Install the dependencies using:

```bash
pip install pyspark matplotlib seaborn pandas google-cloud-storage
```

## Running the Analysis

Update the Google Cloud bucket name in the script before running:

```python
bucket = "your-bucket-name"
data_path = f"gs://{bucket}/data/synthetic_personal_finance_dataset.csv"
```

Then run:

```bash
python final_sprint/code/final-run-script.py
```

The script reads the dataset, performs the analysis, and saves output artifacts to the configured bucket or output location.

## Notes

- `old_work/` contains earlier project files and legacy scripts used during the development process.
- `final_sprint/` represents the finalized version of the analytics pipeline and output generation.
- This repository is intended for data exploration and analytical reporting rather than a production web or application deployment.

## Contributors

This project was developed as part of a collaborative finance analytics effort, with work spanning data cleaning, transformation, aggregation, and visualization.

## License

This repository is provided for educational and research purposes. If you plan to reuse or distribute the code, please confirm whether a repository license is required and add an appropriate license file if needed.
