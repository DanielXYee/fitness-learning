# Fitness Learning  
----  
A light weight apple watch app with real time recognition of workout categories with pretrained machine learning algorithm.

## Motivation  
While apple watch provide fitness data monitoring and analysis, it relies on users to manually input the workout category to track. It'll be much more user-friendly if apple watch could automatically detect and categorize the type of workout in the real time.

## Data Acquisition  

### PowerSense
Data was collected directly from the Apple Watch and with the assitance of a third party application called [PowerSense](https://itunes.apple.com/us/app/powersense-motion-sensor-data-logging-tool/id1050491381?mt=8),which is a free app on apple stores and the main reason we use it is that it provide high sampling rate of data collection. According to the App store description:  

> PowerSense is a powerful motion sensor logging tool that can track and record various sensor data on your iPhone and Apple Watch. These sensors include accelerometer, gyroscope, magnetometer, etc. The recorded data is stored as XML/csv files and can be then sent out via email, AirDrop to your Mac or upload to your linked Dropbox account.  

In our purpose of training the ML model, we use XML file as saved by the *PowerSense* app, since that gives more information.


### Export your own training data  
Although not required, you may want to train the model by using your own workout data. Here is how:
**To be added** *Describe how to use PowerSense to get export the data we want*  

You can configure the sampling rate to be from 1 to 100 Hz for phone. 50 Hz is fixed for watch.

### XML Data Parser



- Included data types:  
  + Accelerometer measurements
  + Heart rate
  + Calorie count

- Data format
  + XML element tree




## Feature selection  
We first looked in the the data directly exported from apple watch program, which include heart rate, calorie count, etc. The raw data was in XML file format and has many sub-categories. WE set up python notebooks to extract the data we want, clean the data and reformat it into different CSV files by using pands. Then we looked in to heart rate and calories for different workouts, trying to decide whether we will using it as our feature for later model training using machine algorithm.   

As can be seen for the juypter notebook for analysis, the data was very noisy and, most importantly, has poor time resolution ( ~ 1 min per measuremnet) . From here we decide not using heart rate and calorie count as the features, but using the accelerometer measurements data, which can give us very high measurement resolution (50Hz sampling rate, every 0.02s per measurement).   

## Machine Learning Model Training



## Apple watch app dev   

## Real time testing   
