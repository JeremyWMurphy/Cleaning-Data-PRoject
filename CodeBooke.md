# Codebook: run_analysis.R

The original data are the Human Activity Recognition Using Smartphones Dataset Version 1.0 from:

==================================================================
Jorge L. Reyes-Ortiz, Davide Anguita, Alessandro Ghio, Luca Oneto.
Smartlab - Non Linear Complex Systems Laboratory
DITEN - Università degli Studi di Genova.
Via Opera Pia 11A, I-16145, Genoa, Italy.
activityrecognition@smartlab.ws
www.smartlab.ws
================================================================== 

All data were downloaded from: https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip. See the readme within this data set for a complete discription of the original data set.

In short, the data are from an experiment carried out with a group of 30 volunteers. Each person perfomred six activities (walking, walking upstairs, walking downstairs, sitting, standing, laying) while wearing a smartphone (Samsung Galaxy S II) on the waist.

The data from the 30 participants were partitioned into a training set (70%) and a test set (30%).

The original raw data was acquired from two sensors, the accelerometer and the gyroscope. 

# The run_analysis.R code

This code reads in the unzipped data, downloaded from the link above under the assumption that the unzipped folder is placed in the current working directory.

It merges the training data and tes data, and assigns the appropriate variable names.

Next, it makes a selection of a subset of the measurement variables. Specifically it only selects:

1. the mean time series data for the gyroscope and the accelerometer for each of the three axial directions (i.e., X, Y, and Z).  

2. the standard deviation of the time series data for the gyroscope and the accelerometer for each of the three axial directions (i.e., X, Y, and Z). 

Note: these data were selected because they were the closest to the raw form. Other from this data set are processed versions of these original data. Furthermore, the acceleration signal was divided by the original authors into body and gravity acceleration using by filtering the signal above or below a corner frequency of 0.3 Hz. In order to maintain congruity with the gyroscope data, only the body accelerometer data is retained.

The retained and renamed measurment variables are as follow in the script are as follows:

1. Accelerometer variables (units: standard gravity units, 'g'):
 *Accel_Mean_X -- mean acceleration in the X direction
 *Accel_Mean_Y -- mean acceleration in the Y direction
 *Accel_Mean_Z -- mean acceleration in the Z direction
 *Accel_STD_X -- standard deviation of acceleration in the X  	direction
 *Accel_STD_Y -- standard deviation of acceleration in the Y  	direction
 *Accel_STD_Z -- standard deviation of acceleration in the Z  	direction

2. Gyroscope variable (units: angular velocity measured as radians/second):
 *Gyro_Mean_X -- mean angular velocity in the X direction
 *Gyro_Mean_Y -- mean angular velocity in the Y direction
 *Gyro_Mean_Z -- mean angular velocity in the Z direction
 *Gyro_STD_X -- standard deviation of angular velocity in the X  	direction
 *Gyro_STD_Y -- standard deviation of angular velocity in the Y  	direction
 *Gyro_STD_Z -- standard deviation of angular velocity in the Z  	direction

# Output data: tiny_data.txt

The data are written out by the script as a .txt document.

It has 14 columns, the first two columns contain the factor variables participant ID ("Subj_ID") and activity. The reamaining 12 columns contain the above mentioned accelerometer and gyroscope numeric variables.

The output can be read back into R using:

read.table("tiny_data.txt", header = TRUE)


 