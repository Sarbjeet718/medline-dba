# MedLine DBA Resit Project

Student ID: 32116055  
Student email: 32116055@student.uwl.ac.uk

This repository contains the final code, dataset, outputs and report for the Databases and Analytics resit assignment based on the MedLine Community Healthcare and Appointment Services case study.

The project analyses appointment outcomes, waiting times, referral delays, prescription delays, nurse visit issues, patient feedback and digital service cases. The work is split across three Google Colab notebooks so that the SQL, R analytics, Python processing, MongoDB development and query optimisation sections are easy to review and rerun.

## Repository Structure

```text
medline-dba-resit/
|-- README.md
|-- requirements.txt
|-- .gitignore
|-- medline_resit_dataset/
|-- notebooks/
|   |-- 01_R_SQL_and_R_Analytics.ipynb
|   |-- 02_Python_Data_Processing.ipynb
|   `-- 03_MongoDB_Atlas_and_Optimisation.ipynb
|-- outputs/
|   |-- figures/
|   |-- mongodb/
|   `-- tables/
`-- reports/
    `-- MedLine_Resit_Submission_Report_FINAL_SUBMISSION.docx
```

## Notebooks

### 1. R SQL and R Analytics

`notebooks/01_R_SQL_and_R_Analytics.ipynb`

This notebook loads the MedLine CSV files into an in-memory SQLite database from R. It demonstrates SQL `SELECT`, filtering, joins, grouping, aggregate functions, CRUD examples and query-plan checking. It also includes R analytics and charts for appointment outcomes, patient ratings, waiting days and nurse visit issues.

### 2. Python Data Processing and EDA

`notebooks/02_Python_Data_Processing.ipynb`

This notebook is the main data processing and exploratory analysis workflow. It loads all structured CSV files, checks data quality, converts dates, validates keys, creates calculated fields and produces tables and charts for appointments, waiting times, clinics, services, referrals, prescriptions, feedback, staff capacity, patient risk and digital interactions.

### 3. MongoDB Atlas and Optimisation

`notebooks/03_MongoDB_Atlas_and_Optimisation.ipynb`

This notebook uses MongoDB Atlas for the semi-structured patient service case data. It imports nested JSONL service case documents into the `medline_resit` database and `patient_service_cases` collection. It demonstrates CRUD operations, aggregation pipelines, indexes, repeated timing tests and explain-plan evidence.

## Dataset

The dataset is stored in:

```text
medline_resit_dataset/
```

It contains structured CSV files and a nested JSONL file covering:

- patients
- clinics
- staff
- appointments
- referrals
- prescriptions
- nurse visits
- patient feedback
- digital interactions
- patient service cases

The notebooks use relative file paths, so the dataset folder should remain in the repository root.

## Main Outputs and Charts

Generated outputs are stored in:

- `outputs/figures/` - charts used for analysis and report evidence
- `outputs/tables/` - CSV summaries produced from R, Python and MongoDB workflows
- `outputs/mongodb/` - aggregation pipelines, results, query workloads and explain-plan files
- `reports/` - final Word report for submission

The main chart outputs include:

- appointment status distribution
- bad appointment outcome rate by clinic
- bad appointment outcome rate by service
- waiting days distribution
- waiting days against patient rating
- patient rating by appointment status
- referral delay by service
- prescription delay by clinic
- nurse visit problem rate by clinic
- clinic capacity by clinic
- digital event type counts
- combined clinic risk heatmap
- R analytics charts for clinic outcomes, ratings, waiting days and nurse visit issues

The table outputs include dataset inventory, data quality checks, appointment summaries, clinic and service performance, feedback analysis, referral delay, prescription delay, nurse visit analysis, patient segment risk, MongoDB timing results and MongoDB explain-plan notes.

These files are included so the analysis, figures and supporting evidence can be reviewed without rerunning every notebook.

## How To Run

Run the notebooks in this order:

1. Open `01_R_SQL_and_R_Analytics.ipynb` in Google Colab with an R runtime.
2. Open `02_Python_Data_Processing.ipynb` in Google Colab with a Python runtime.
3. Open `03_MongoDB_Atlas_and_Optimisation.ipynb` in Google Colab with a Python runtime.

The notebooks include setup cells for required packages. For local Python use, install the packages in `requirements.txt`:

```bash
pip install -r requirements.txt
```

## MongoDB Reproducibility

To rerun the MongoDB notebook, add the MongoDB Atlas connection string in Colab as a secret or environment variable named:

```text
MONGODB_URI
```

The Atlas Network Access list must allow the IP address of the machine running the notebook. The notebook creates the required database, collection, documents and indexes from the project dataset.

## Suggested Git Commands

Run these commands inside the repository root folder:

```bash
git init
git add .
git commit -m "Add MedLine DBA resit submission"
git branch -M main
git remote add origin <your-github-repository-url>
git push -u origin main
```

Replace `<your-github-repository-url>` with the URL of the GitHub repository.
