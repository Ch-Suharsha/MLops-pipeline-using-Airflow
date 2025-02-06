# MLops-pipeline-using-Airflow

The data set consists of 5 key columns which disusses the app behaviour and they are
1) App
2) Usage
3) Times opened
4) Notifications
5) Data

This pipeline aims to simplify the analysis of screentime data by automating its preparation and using machine learning to predict app usage. To keep things running smoothly, we will create an Airflow DAG that schedules and automates daily data preprocessing, ensuring an efficient and scalable workflow.

The code in processing.py file prepares the screentime dataset for machine learning by cleaning and transforming the data. It starts by loading the dataset and checking for missing values and duplicates to ensure data quality. Then, it processes the Date column to extract useful details like the day of the week and month. Finally, it converts the App column into a numeric format using one-hot encoding.

You can find a file with the name model.py which consists the code for the machine learning model and the model i have used here is random forest model, this particular file consists the code to train the model by splitting the data into training and testing setsto train and evaluate the model.

Diving into the process it separates the target variable (Usage in minutes) from the other data and splits it into 80% for training and 20% for testing. The training data is used to train a RandomForestRegressor model. Once trained, the model makes predictions on the test data, and its accuracy is measured using the Mean Absolute Error (MAE), which shows the average difference between predicted and actual values.

Coming to the next part as we understand the process this needs to be happen again and again so that the data is always updated which is nothing but automating the process and we are using  airflow to do this with the help of direct acyclic graphs,the dags are nothing but few steps of process which goes on and on when ever it gets a reminder and we define it in a python file which Iam attaching in the files as dag.py.

