# MLops-pipeline-using-Airflow

The data set consists of 5 key columns which disusses the app behaviour and they are
1) App
2) Usage
3) Times opened
4) Notifications
5) Data

This pipeline aims to simplify the analysis of screentime data by automating its preparation and using machine learning to predict app usage. To keep things running smoothly, we will create an Airflow DAG that schedules and automates daily data preprocessing, ensuring an efficient and scalable workflow.

The code in processing.py file prepares the screentime dataset for machine learning by cleaning and transforming the data. It starts by loading the dataset and checking for missing values and duplicates to ensure data quality. Then, it processes the Date column to extract useful details like the day of the week and month. Finally, it converts the App column into a numeric format using one-hot encoding.

