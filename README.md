# Getting-and-Cleaning-Data-Course-Project

This repository contains instructions on how to tidy a Human Activity recognition dataset in order to perform further analyses over it. 

# Dataset 

The dataset can be found at: http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones.

# Files

- Codebook.md: a codebook that describes the variables and the data and how the code runs.

- run_analysis.R: an R script that performs the data preparation through the following steps:

  1. Merges the training and the test sets to create one data set;
  2. Extracts only the measurements on the mean and standard deviation for each measurement;
  3. Uses descriptive activity names to name the activities in the data set;
  4. Appropriately labels the data set with descriptive variable names;
  5. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.

- FinalTidyData.txt: the final data after going through the processes above.
