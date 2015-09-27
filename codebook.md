# Code Workflow Explained

The script `run_analysis.R`performs the 5 steps.

* Firstly data is merged using the `rbind()` function. All entities are matched accordingly.
* Only those columns with the mean and standard deviation measures are taken from the whole dataset. After extracting these columns, they are given the correct names, taken from `features.txt`.
* As activity data is addressed with values 1:6, we take the activity names and IDs from `activity_labels.txt` and they are substituted in the dataset.
* Wrong or vague column names are corrected in whole dataset.
* Finally, we generate a new dataset with all the average measures for each subject and activity type (30 subjects * 6 activities = 180 rows). The output file is called `tidy_dataset.txt`, and uploaded to this repository.

# Variables and other functions

* `x_train`, `y_train`, `x_test`, `y_test`, `subject_train` and `subject_test` contain the data from the downloaded files.
* `x_data`, `y_data` and `subject_data` merge the previous datasets to further analysis.
* `features` contains the correct names for the `x_data` dataset, which are applied to the column names stored in `std_mean_measurements`, a numeric vector used to extract the desired data.
* A similar approach is taken with activity names through the `activities` variable.
* `all_data` merges `x_data`, `y_data` and `subject_data` in a big dataset.
* Finally, `tidy_dataset` contains the relevant averages which will be later stored in a `.txt` file. `ddply()` from the plyr package is used to apply `colMeans()` .