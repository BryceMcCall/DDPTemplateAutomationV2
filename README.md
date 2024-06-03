# DDP-Reporting-Template-Automation

This script automates the population of the DDP Reporting Excel Template.

## Description

This project reads, filters, and processes data from multiple files to produce organized and aggregated output. It applies various transformations and filters to the input data, and it handles conversions between units, with the option to output the results to new files. It can handle special rows differently and applies conditional logic based on predefined mappings.

## Files

report.csv: Primary input file containing data to be processed.
SetsAndMaps.xlsm: Contains mappings for processing.
merged_data.csv: Intermediate file generated after merging input files.
j_filter.xlsx: Additional filtering parameters.
WB1.xlsx, WB2.xlsx, WB3.xlsx: Input files with data in tabular form to be processed and aggregated.

## Prerequisites

Python 3.x
pandas
numpy
openpyxl

## Functions

correct_list_string(s)
Takes a string s, and returns a corrected string if s is a string representation of a list.

filter_data(row)
Processes and filters the data based on predefined conditions and returns the filtered result along with unique ID.

convert_value(row)
Converts SATIMGE values based on TargetUnit column using predefined conversion factors.

## Workflow

Reads the input DataFrames.
Merges the DataFrames based on common columns.
Applies predefined filters and processes special rows differently.
Aggregates the data by UniqueID and Year, summing SATIMGE values.
The final DataFrame is exported to 'input/results_filter.csv'.
The script also reads and writes data from/to Excel workbooks, updating cells based on the processed data.

=================================
## UPDATE
03 June 2024
Bryce McCall

This automation is not in it's current form working 100% in the sense that it's not populating everything that could be populated in the IDDRI template, and there are places where it appeared to be populating incorrectly
NOTE: The GDP numbers are not populated with this automation system (a GAMS script was used)

Residential filter file needs to be tweaked: refrigeration needs to be added to the 'other' group in the template. 
Cement emissions arent populated automatically and needs to be added. Cement sector emissions are not simple since they are IPPU, and there is also the combustion (energy) componenet that needs to be included.


