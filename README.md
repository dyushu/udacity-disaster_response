# Disaster Response Pipeline
This repository contains the files for the Udacity data scientist nano-degree project 2: build a disaster response pipeline.

## Contents
Following is the file structure of the project:

<pre><code>
  - app
| - template
| |- master.html  # main page of web app
| |- go.html  # classification result page of web app
|- run.py  # Flask file that runs app

- data
|- disaster_categories.csv  # data to process 
|- disaster_messages.csv  # data to process
|- process_data.py
|- InsertDatabaseName.db   # database to save clean data to

- models
|- train_classifier.py
|- classifier.pkl  # saved model 

</code></pre>

- The folder `notebooks` contains some exploratory scripts.  See in
  particular `notebooks/ML Pipeline Preparation.py`, where a grid
  search is used to find good parameter for the model.

- The folder `data` contains the original message dataset (message
  text and categories), as two separate CSV files.  The script
  `process_data.py` transforms and saves this to a database file.

- The folder `models` contains the script `train_classifier.py` to
  train the model.

- The folder `app` contains the Flask webapp that categorizes new
  messages.  It assumes the database file and model generated by the
  scripts mentioned above are in the `out` folder at the root of this
  repository.

- README.md

## Instructions

1. Run the following commands in the project's root directory to set
   up your database and model.

    - To run ETL pipeline that cleans data and stores in database
        `python data/process_data.py data/disaster_messages.csv
        data/disaster_categories.csv out/DisasterResponse.db`
    - To run ML pipeline that trains classifier and saves `python
        models/train_classifier.py data/DisasterResponse.db
        out/classifier.pkl`

2. Run the following command in the app's directory to run your web
    app.  `python run.py`

3. If you are running in Udacity's workspace, then try to get `WORKSPACEDOMAIN` and `WORKSPACEID` by typing `env|grep WORK` 

4. If you are running in Udacity's workspace, go to https://SPACEID-3001.SPACEDOMAIN . Otherwise, go to http://0.0.0.0:3001/

## Acknowledgments

The code in this repository is based on a template provided by
Udacity.  In particular, the web app is almost unmodified from their
example.
