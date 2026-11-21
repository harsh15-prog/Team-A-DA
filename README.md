# Uber Trips | Data Analysis & Interactive Dashboard

An analysis of 50,000 ride records across six US cities, focused on trip completion, revenue, fare patterns and data quality. The project combines Python-based exploratory analysis with an interactive Streamlit dashboard.

## Project overview

The goal was to understand how trips perform across cities, what drives fare amounts, and which data quality issues need attention before drawing conclusions.

**Dataset:** 50,000 records, January 1–February 4, 2023, covering Boston, Chicago, Los Angeles, New York, San Francisco and Seattle. The reviewed dataset has 24 columns, including derived measures and quality flags.

## Tools used

Python, Pandas, NumPy, Matplotlib, Seaborn, SciPy, Streamlit and Jupyter Notebook.

## What I worked on

- Checked missing values, duplicate records, trip statuses and invalid distance/duration values.
- Audited precomputed data quality flags rather than deleting flagged records without investigation.
- Compared completed trips and fare revenue across cities, payment methods and drivers.
- Explored hourly and daily trip distributions and the relationship between trip distance and fare.
- Built a Streamlit dashboard with city, status and payment filters, visualizations and CSV export.

## Key findings

- **42,540 of 50,000 trips (85.08%)** were completed; 4,984 were cancelled and 2,476 were no-shows.
- **Completed-trip fare total:** approximately **$679.7K** in the reviewed dataset.
- **Boston** led the six cities in completed trip volume (7,182) and completed-trip fare revenue (approximately $115K).
- **Distance and fare** showed a strong positive relationship (Pearson r ≈ 0.871; in-sample linear-fit R² ≈ 0.758). The fitted relationship was approximately **fare = $2.98 + $1.85 × distance (km)**. This is descriptive analysis, not a validated predictive model.
- **Three zero-distance records** were identified. The main reviewed dataset retains all 50,000 records for auditing; the separate report uses a 49,997-row subset after excluding those three records.

**Data caveat:** The dataset has synthetic-looking patterns. In particular, the coordinate-based city-center flag applies to nearly all records, and trip timestamps follow a highly regular schedule. These features limit real-world interpretations of geographic and demand patterns.

## Repository structure

```text
Analyzed File/
  cleaning.ipynb
  uber_trips_cleaning_and_analysis.ipynb
  trips_reviewed.csv
Dashbord/
  streamlit_dashboard.py
  trips_reviewed.csv
Raw Files/
  uber_trips_dataset_50k.csv
  Uber_Fare_Hackathon_Data_Analyst_Instructions.pdf
UberTrips-Analytical report.pdf
requirements.txt
README.md
```

## Run the dashboard

From the project root:

```bash
pip install -r requirements.txt
streamlit run "Dashbord/streamlit_dashboard.py"
```

To explore the notebooks, open the files in `Analyzed File/` using Jupyter Notebook. The analytical notebook uses `trips_reviewed.csv` in the same folder.

## Notes on the numbers

Different project outputs use different subsets: the main notebook and dashboard inspect 50,000 reviewed rows; the PDF report analyzes 49,997 rows after removing three zero-distance records; a stricter operational filter in the notebook retains 35,299 completed trips. Metrics should always be interpreted using the subset named in the relevant analysis.

## Team & Contributors

This project was developed collaboratively during the Data Analytics Hackathon organized by WsCube Tech.

Special thanks to my teammates for their contributions, teamwork, and efforts throughout the project.

- Harsh Chaudhary
- Mahipal Choudhary
- Aniket Kumar
- Jitesh Kumar
- Aditya
- Parth Soni
- Bhavishikha

From data cleaning and analysis to dashboard development and presenting our findings, this project was a collective effort.
