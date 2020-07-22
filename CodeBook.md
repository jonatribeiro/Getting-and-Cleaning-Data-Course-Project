Before using run_analysis.R, one should: 

1. Download the dataset
  - The dataset can be download through the link: https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip. The zip folder should be extracted
and then named "UCI HAR Dataset". The run_analysis.R code should be in the same workspace directory as this folder. 

After the first step, run_analysis.R operates through the following steps:

2. Assigns each data to variables
  - features <- features.txt : 
  features from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ.
  
  - activities <- activity_labels.txt : 
  activities performed and their labels
  
  - subject_test <- test/subject_test.txt : 
  contains test subjects data 
  
  - x_test <- test/X_test.txt : 
  contains features test data
  
  - y_test <- test/y_test.txt : 
  contains test data of activities’ labels
  
  - subject_train <- test/subject_train.txt : 
  contains train subjects data
  
  - x_train <- test/X_train.txt : 
  contains features train data
  
  - y_train <- test/y_train.txt :
  contains train data of activities’ labels

3. Merges the training and the test sets to create one data set
  - X is created by merging x_train and x_test using rbind() function
  - Y is created by merging y_train and y_test using rbind() function
  - Subject  is created by merging subject_train and subject_test using rbind() function
  - Merged is created by merging Subject, Y and X using cbind() function

4. Extracts only the measurements on the mean and standard deviation for each measurement
  - Tidy is created by subsetting Merged, selecting only columns: subject, label and the measurements on the mean and standard deviation (std) for each measurement

5. Uses descriptive activity names to name the activities in the data set
  - Numbers in label column of Tidy (created in the previous step) replaced with the activities taken from second column of the activities variable

6. Appropriately labels the data set with descriptive variable names
  - Replaces:
    - "Acc" with "Accelerometer"
    - "Gyro" with "Gyroscope"
    - "BodyBody" with "Body"
    - "Mag" with "Magnitude"
    - "t" at the beginning of a column's name with "Time"
    - "f" at the beginning of a column's name with "Frequency"
    - "tbody" with TimeBody
    - "-mean()" with "Mean"
    - "-std()" with "STD"
    - "-freq()" with "Frequency"
    - "angle" with "Angle"
    - "gravity" with "Gravity"

7. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject
  - Groups Tidy by subject and activity, then creates FinalTidyData by summarizing Tidy taking the means of each variable for each activity and each subject
  - Exports FinalTidyData into FinalTidyData.txt file.
