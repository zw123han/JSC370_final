### Data
This document details the data source, how it was retrieved, and processed.

#### Required executables
There is a `data.Rmd` file in this directory, which contains (3) chunks of code to run. It expects the `tidyverse` and `reticulate` packages to be installed, in order to support both `R` and `Pandas (Python)` csv conversions. You should also have an `R` and `Python` distribution installed. You must also install the `miniconda` package, or some distribution of `Pandas`. The RStudio terminal should automatically prompt this.

#### Data sourcing and cleaning
The data itself is retrieved from an older JSON version of the levels.fyi database [1], using the `Pandas` and `requests` packages in `Python` [2]. The data is then processed for the specific applications of this project as follows:

- Earning data standardized to (US) dollars.
- 5th percentile and 99th percentile of total compensation earners removed, to avoid erronous self-reported entries
- Column attributes (company names, location) standardized, timestamps converted, unused columns removed

You should expect (2) CSV files in the directory you ran the notebook. (1) salary.csv is the raw CSV directly converted from the stored JSON format. (2) salary_interest.csv containing the cleaned version of the dataset used in this project.

#### Extras
If this analysis is meaningful to you, consider paying for levels.fyi's private database which is cleaner and more up to date.

#### References

[1] levels.fyi. (2022). Salary Data (updated 2021). https://www.levels.fyi/js/salaryData.json.
Retrieved March 10, 2022.

[2] Grierson, M. (2020, January 8). https://towardsdatascience.com/a-beginners-guide-to-grabbing-and-analyzing-salary-data-in-python-e8c60eab186e. Retrieved March 10, 2022. 