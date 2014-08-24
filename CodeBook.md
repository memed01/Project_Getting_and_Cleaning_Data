Coursera: Getting and Cleaning Data
===================================
Codebook
==================================================================


The dataset includes the following files:
=========================================

- 'README.txt'

- 'features_info.txt': Shows information about the variables used on the feature vector.

- 'features.txt': List of all features.

- 'activity_labels.txt': Links the class labels with their activity name.

- 'train/X_train.txt': Training set.

- 'train/y_train.txt': Training labels.

- 'test/X_test.txt': Test set.

- 'test/y_test.txt': Test labels.

The following files are available for the train and test data. Their descriptions are equivalent. 

- 'train/subject_train.txt': Each row identifies the subject who performed the activity for each window sample. Its range is from 1 to 30. 

- 'train/Inertial Signals/total_acc_x_train.txt': The acceleration signal from the smartphone accelerometer X axis in standard gravity units 'g'. Every row shows a 128 element vector. The same description applies for the 'total_acc_x_train.txt' and 'total_acc_z_train.txt' files for the Y and Z axis. 

- 'train/Inertial Signals/body_acc_x_train.txt': The body acceleration signal obtained by subtracting the gravity from the total acceleration. 

- 'train/Inertial Signals/body_gyro_x_train.txt': The angular velocity vector measured by the gyroscope for each window sample. The units are radians/second. 


The generated output is saved to the file tidy-data.csv. This file includes all rows merged from the test and training data included in the activity recognition dataset.

The analysis addresses the training and test data separately, first combining the feature vector with outcome variables and subject identifiers (e.g. X_train.txt, Y_train.txt, subject_train.txt), and then merges the training and test data into a single, larger dataset.

The analysis then subsets the data so that only mean and standard devation measurements from the original data are included. This includes all measurements identified by -mean() or -std() labels.

The analysis continues by taking the average value for each of these measurements by subject and activity. For example, a single subject will include a number of entries for each of the mean and std measurements across six different activities such as standing, walking, etc. The average value for "subject 1 standing" for each measurement is calculated, then for "subject 2 walking", etc, continuing with each subject-activity pair.

The final output is the combined average values by subject-activity pair for every mean or std devation measurement in the original training and test data. Feature labels from the original dataset are retained, but it should be noted that the value in the output is now the average of all those values for subject-activity. For example, the feature label may be "tBodyAcc.mean...X", but the output is actually the mean of the "tBodyAcc.mean...X" values for each subject-activity pair.
