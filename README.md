# Disaster Response Pipeline 

## Overview:
In this project, I have built a model to classify messages that are sent during disasters. There are 36 pre-defined categories, and examples of these categories include Aid Related, Medical Help, Search And Rescue, etc. By classifying these messages, we can allow these messages to be sent to the appropriate disaster relief agency. 

In the project, I have also built a basic ETL and Machine Learning pipeline to streamline the steps. Also, this project contains a web app where you can input a message and get classification results.



## Data:
The data comes from [appen](https://appen.com/datasets/combined-disaster-response-data/) containing 30,000 messages drawn from events including an earthquake in Haiti in 2010, an earthquake in Chile in 2010, floods in Pakistan in 2010, super-storm Sandy in the U.S.A. in 2012, and news articles spanning a large number of years and 100s of different disasters. The data has been encoded with 36 different categories related to disaster response and has been stripped of messages with sensitive information in their entirety. This dataset contains the original message in its original language, the English translation, and dozens of classes for message content. These classes are noted in column titles with a simple binary 1= yes, 2=no.

## File Structure
~~~~~~~
        disaster_response_pipeline
          |-- app
                |-- templates
                        |-- go.html
                        |-- master.html
                |-- run.py
          |-- data
                |-- disaster_message.csv
                |-- disaster_categories.csv
                |-- DisasterResponse.db
                |-- process_data.py
          |-- models
                |-- classifier.pkl
                |-- train_classifier.py
          |-- README

## File Descriptions
1. App folder includes the templates folder and "run.py" for the web application
2. Data folder contains "DisasterResponse.db", "disaster_categories.csv", "disaster_messages.csv" and "process_data.py" for data cleaning and transfering.
3. Models folder includes "classifier.pkl" (Not included on github because of large size of >300MB) and "train_classifier.py" for the Machine Learning model.
4. README file

## Instructions
1. Run the following commands in the project's root directory to set up your database and model.

    - To run ETL pipeline that cleans data and stores in database
        `python data/process_data.py data/disaster_messages.csv data/disaster_categories.csv data/DisasterResponse.db`
    - To run ML pipeline that trains classifier and saves
        `python models/train_classifier.py data/DisasterResponse.db models/classifier.pkl`

2. Run the following command in the app's directory to run your web app.
    `python run.py`

3. Go to http://127.0.0.1:5000/
