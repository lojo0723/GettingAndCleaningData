Code Book
==========

## Pre Analysis
This script will check if the data file is present in your working directory.
Otherwise, it will download / Unzip the file. 

## Read data and Merge
subject_test : subject IDs for test

subject_train : subject IDs for train

X_test : values of variables in test

X_train : values of variables in train

y_test : activity ID in test

y_train : activity ID in train

activity_labels : Description of activity IDs in y_test and y_train

features : description(label) of each variables in X_test and X_train

dataSet : bind of X_train and X_test

## 1. Extracts only the measurements on the mean and standard deviation for each measurement. 
Create a vector of only mean and std labels, then use the vector to subset dataSet.

MeanStdOnly : a vector of only mean and std labels extracted from 2nd column of features
dataSet : at the end of this step, dataSet will only contain mean and std variables
## 2. Uses descriptive activity names to name the activities in the data set
Create a vector of "clean" feature names by getting rid of "()" at the end. Then, will apply that to the dataSet to rename column labels.

CleanFeatureNames : a vector of "clean" feature names
## 3. Appropriately labels the data set with descriptive activity names.
Combine test data and train data of subject and activity, then give descriptive lables. Finally, bind with dataSet. At the end of this step, dataSet has 2 additonal columns 'subject' and 'activity' in the left side.

subject : bind of subject_train and subject_test
activity : bind of y_train and y_test
## 4. Creates a second, independent tidy data set with the average of each variable for each activity and each subject. 
Group the activity column of dataSet as "act_group", then rename each levels with 2nd column of activity_levels. Finally apply the renamed "act_group" to dataSet's activity column.

act_group : factored activity column of dataSet
## 5. Output tidy data
dataSet is melted to create tidy data. It will also add [mean of] to each column labels for better description. Finally output the data as "tidy_data.txt"

baseData : melted tall and skinny dataSet
secondDataSet : casete baseData which has means of each variables
