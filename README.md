# SOTA2024_ReportOut

This repository contains all of the code to reproduce the analysis done for the State of the AnVIL 2024 Poll.

## Directory Structure:

### data

Raw data for this project is in a password protected, controlled access shared Google Drive because it contains some identifying information. This data is processed and de-identified and made available within the `wrangled_data` subdirectory.

#### annotations

These are codebook files created by the analysts explaining the columns in the raw data as well as possible values and dictionaries to categorize certain columns (e.g., institution).

* `codebook.txt`: codebook relating to raw data
* `controlledAccessData_codebook.txt`: Controlled access data mentioned in the poll as well as whether AnVIL hosts it.
* `institution_codebook.txt`: institutions and simplified categorization

#### wrangled_data

* `resultsTidy.rds`: wrangled data saved from `1_TidyData.Rmd` (with identifying information of email and raw institutional affiliation removed)
* `resultsTidy_personas.rds`: wrangled data saved from `2_PersonaStats.Rmd`

### analyses

* `1_TidyData.Rmd`
* `2_PersonaStats.Rmd`
* `3_MainAnalysis.Rmd`
* `4_Stats.Rmd`

### resources

* `scripts/shared_functions.R`: some functions used repeatedly in analysis or for plotting

### figures

* `figureCreation.Rmd`

## Other notes:

* Preprint information
* A poster presented at the AnVIL Community Conference 2025
* A companion website information
* AnVIL Collection and other outreach information
