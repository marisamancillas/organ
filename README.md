# organ

The purpose of this repository is to document code developed for my master's project. Specifically, there are scrips uploaded here that I developed to  clean and harmonize plant species occurrence data across multiple herbaria for the Organ Mountains, New Mexico. 

The project's overall goal is to provide a baseline of plant species occurrence data through time. 

# contents 

## collector_name_dictionary.csv

This CSV is a dictionary I made of regular expression search patterns which match all possible collector name spellings in my dataset. Having this dictionary is helpful because, at any step of the process, the search pattern can be modified to include different spellings. Additionally, it makes the data-cleaning process automated and repeatable. 

## harmonizing_merging_phase_1.Rmd

The goal of this script was to harmonize plant species occurrence data across several herbaria and biodiversity repositories for the Organ Mountains (-106.6418 W, 32.1589 N, -106.4665 W, 32.42757 N) from the first specimen collection record in 1848 to February 2021. Specific objectives were to (1) Subset the occurrence records for the Organ Mountains both for georeferenced and non-georeferenced records (2) Identify duplicate records and harmonize all information for that individual collection event within and between institutions and (3) Standardize schema and combine all occurrences into one dataset.

## harmonizing_merging_phase_2.Rmd

The overall objective of this script was to transform the merged dataset from "harmonizing_merging_phase_1" into a set of clean, related tables with reduced duplication.

In order to achieve this, data related to the collection_date was processed, cleaned, and filtered, then parsed into a year, month, and date column. The resulting dates were evaluated for credibility with respect to the age of the collector. In other words, if a collector was not alive during the year/decade, those dates were corrected. I determined which specimen collectors were in which decade using the raw New Mexico State University Herbarium metadata. Once this column was standardized, I harmonized duplicates using the unique combination of collector name, date (or day, month, year), and the locality description for records with less than 1 georeferencing attempt. If there was more than one georeference, I selected coordinates with “high confidence” verification status, lowest coordinate uncertainty, and highest non-NA entries for georeferencing protocol, notes, and sources. Finally, the data were separated into related tables representing different data types(i.e., biodiversity, location, time, metadata, and unstructured notes). 


## harmonizing_merging_phase_3.Rmd

In this script, I join the final occurrence dataset with a taxonomy table produced in a separate workflow. This step refines the occurrence dataset to only relatively clean taxonomic names.

