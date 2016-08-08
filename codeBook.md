## Code Book for Course Project

### Overview

Source of the data: 

https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip

Full description of the data: 

http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

### Process

The script `run_analysis.R` performs the following process to clean up the data and create tidy data sets:

- Merge the training and test data sets to create one data set.

- Extracts only the measurements on the mean and standard deviation for each measurement.

- Names the activities with human readable activity names read from `activity_labels.txt` in the data set.

- Labels the data set with descriptive names.

- Saves the result as `finalTidyData.txt`.

- The average of each measurement for each activity and each subject is merged to a second data set. The result is saved as `finalMeanData.txt`.

### Variables

train.x - table contents of `train/X_train.txt`
train.y - table contents of `train/y_train.txt`
train.subject - table contents of `test/subject_train.txt`
trainData - combined training data set
test.x - table contents of `test/X_test.txt`
test.y - table contents of `test/y_test.txt`
test.subject - table contents of `test/subject_test.txt`
testData - combined testing data set
fullData - merged training and testing data
featureName - table contents of `features.txt`
featureIndex - extracted mean and standard deviation index
finalData - temp of the first output tidy data set
activityName - table contents of `activity_labels.txt`
groupData - temp of the second output tidy data set with the average of each variable for each activity and each subject.

### Output

`finalTidyData.txt`

- `finalTidyData.txt` is a 10299x68 data frame.
- The first column contains subject IDs.
- The second column contains activity names.
- The last 66 columns are measurements.
- Subject IDs are integers between 1 and 30.

`finalMeanData.txt`

- `finalMeanData.txt` is a 180x68 data frame.
- The first column contains subject IDs.
- The second column contains activity names.
- The averages for each of the 66 attributes are in columns 3-68.

