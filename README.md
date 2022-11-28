# organ

The purpose of this repository is document code developed for my masters project. Specifically, there are scrips uploaded here that I developed to  clean and harmonize plant species occurrence data across multiple herbaria for the Organ Mountains, New Mexico. 

The overall goal of the project is to provide a baseline of plant species occurrence data through time. 

# contents 

## collector_name_dictionary.csv

This csv is a dictionary I made of regular expression search patterns which match all possible collector name spellings in my dataset. Having this dictionary is quite usefull because at any step of the process the search pattern can be modified to include additional spellings. Additionally, it makes the datacleaning process automated and repeatable. 

## harmonizing_merging_new.Rmd

This is the rmarkdown file which harmonizes the original data downloads into one dataset. Within this file is a regular expression search pattern for all localities including an Organ Mountain place name. 

## taxonomy_cleaning_workflow.Rmd

This is the workflow developed to clean taxonomic names. 

