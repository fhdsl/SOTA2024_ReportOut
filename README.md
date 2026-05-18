# SOTA2024_ReportOut

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.17611423.svg)](https://doi.org/10.5281/zenodo.17611423)

This repository contains all of the code to reproduce the analysis done for the State of the AnVIL 2024 Poll.

[Survey Instrument](https://github.com/fhdsl/SOTA2024_ReportOut/blob/main/resources/supplemental_material/State_of_the_AnVIL_2024_Community_Poll-DocVersion.pdf)

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

* `1_TidyData.Rmd`: Fetching of Raw Data and wrangling steps for later analysis to create a de-identified tidy data file.
* `2_PersonaStats.Rmd`: Identification of personas and joining of persona categorization with tidy data.
* `3_MainAnalysis.Rmd`: Main analysis and plotting driver
* `4_Stats.Rmd`: Code to support all stated stats/general observations in the report out that aren't directly observed from plots/figures. Description of format for this:
    * Chronological order of statements and sections aligning with layout of the preprint
    * For each section, if there's a table that is used to support multiple statements, table is constructed within an expandable details section prior to any direct statements from the preprint
    * For each statement, there's a section separator and the specific statement, followed by an expandable details section with code to show the support for the statement.
* `5_PCA.Rmd`: Performs PCA analysis for all respondents after subsetting and wrangling the data

### reports

This directory contains corresponding knit HTML files for each of the R Markdown files in the `analyses` directory and the figure creation R Markdown in the `figures` directory.  

### resources

* `scripts/shared_functions.R`: some functions used repeatedly in analysis or for plotting
* `plots/`: plots from the main analysis saved as png files
* `supplemental_material/`: Includes the [complete poll](https://github.com/fhdsl/SOTA2024_ReportOut/blob/main/resources/supplemental_material/State_of_the_AnVIL_2024_Community_Poll-DocVersion.pdf), [supplementary Table 1](https://github.com/fhdsl/SOTA2024_ReportOut/blob/main/resources/supplemental_material/SupplementalTable1.pdf) (relation of study aims and poll questions), and [supplementary Table 2](https://github.com/fhdsl/SOTA2024_ReportOut/blob/main/resources/supplemental_material/SupplementalTable2.pdf) (raw responses translated to awareness and use)

### figures

* `figureCreation.Rmd`: Uses `patchwork` to combine plots from `3_MainAnalysis.Rmd`to make figure panels and adjusts aesthetics as necessary.
* The figure panels themselves are saved as png files within this directory as well

## Other notes:

* Preprint: https://www.biorxiv.org/content/10.1101/2025.11.14.688517v1
* A poster presented at the AnVIL Community Conference 2025: https://www.youtube.com/watch?v=Z_xTenvwRDo&list=PL6aYJ_0zJ4uDbUn28tves8OKwrDB7dN32&index=8
* [AnVIL Collection](https://hutchdatascience.org/AnVIL_Collection/) and this poll are largely supported by the [Outreach Working Group](https://anvilproject.org/team/working-groups#outreach-working-group)
