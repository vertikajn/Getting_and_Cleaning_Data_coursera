# Getting_and_Cleaning_Data_coursera

This repository contains the R code file , Final dataset file and documentation files for the Coursera course(Getting and Cleaning data)

The dataset used is - [Human Activity Recognition Using Smartphones](http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones)

## Files and procedures

`codebook.md` describes the variables, the data, and any transformations or work that was performed to clean up the data.

`run_analysis.R` contains all the code to perform the analyses described in the 5 steps.
The output of the 5th step is called `tidy_dataset.txt`, and uploaded in coursera


The script `run_analysis.R`performs the 5 steps.

* Firstly data is merged using the `rbind()` function. All variables and entities are matched accordingly.
* Then, only those columns with the mean and standard deviation measures are taken from the whole dataset. After extracting these columns, they are given the correct names, taken from `features.txt`.
* As activity data is addressed with values 1:6, we take the activity names and IDs from `activity_labels.txt` and they are substituted in the dataset.
* On the whole dataset, those columns with vague column names are corrected.
* Finally, we generate a new dataset with all the average measures for each subject and activity type (30 subjects * 6 activities = 180 rows). The output file is called `tidy_dataset.txt`, and uploaded to this repository.