# Code Book

The tidy data created is the result of merging the training and test sets. 
The mean and standard deviation were then extracted for each measurement variable.
Descriptive actvity names are used to name each activity in the data set.
Descriptive variable names are used to label the data set.
An independent tidy data set with the average of each variable for each activity and each subject is created.

This code book summarizes the resulting data fields in `tidy.txt`.

## Identifiers

* `subject` - The ID (1-30) of the test subject
* `activity` - The type of activity performed when the corresponding measurements were taken

## Variables

* `x_train`, `y_train`, `x_test`, `y_test`, `subject_train` and `subject_test` contain the data from the downloaded files.
* `x_data`, `y_data` and `subject_data` merge the previous datasets to further analysis.
* `features` contains the correct names for the `x_data` dataset, which are applied to the column names stored in `mean_and_std_features`, a numeric vector used to extract the desired data.
* A similar approach is taken with activity names through the `activities` variable.
* `all_data` merges `x_data`, `y_data` and `subject_data` in a big dataset.
* Finally, `averages_data` contains the relevant averages which will be later stored in a `.txt` file. `ddply()` from the plyr package is used to apply `colMeans()` and ease the development.

## Activity Observation

* `WALKING` (value `1`): subject was walking during the test
* `WALKING_UPSTAIRS` (value `2`): subject was walking up a staircase during the test
* `WALKING_DOWNSTAIRS` (value `3`): subject was walking down a staircase during the test
* `SITTING` (value `4`): subject was sitting during the test
* `STANDING` (value `5`): subject was standing during the test
* `LAYING` (value `6`): subject was laying down during the test
