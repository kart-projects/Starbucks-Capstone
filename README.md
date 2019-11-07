# Welcome to Starbucks-Capstone project
In this project we will analyze simulated datasets containing transaction, demographic information and offers that mimics customer behavior on the Starbucks rewards mobile app. The task in this project is to combine these datasets to determine which demographic groups respond best to which offer type. We will also take a step forward and build out Random Forest models for each offer types which could be used to predict if we should recommend an offer for a customer who has not transacted at all using the mobile app. We could also use the same models to resend offers to customers who were previously not influenced by the other or same offers.   

### Table of Contents

1. [Installation](#installation)
2. [Motivation](#motivation)
3. [File Descriptions (*.ipynb, *.json)](#files)
4. [Summary Results](#summaryresults)
5. [Licensing, Authors, and Acknowledgements](#licensing)

## Installation and instructions <a name="installation"></a>

The included python and iron python notebook files in this repo should run with Anaconda distribution of Python versions 3.*.

1. To explore this project please download the data folder with three JSON datasets, targeted_offers.py and Starbucks_Capstone_Project.ipynb files.

2. You can either upload the iron python notebook file and the data folder containing the JSON files using the Jupyter notebook which will automatically place these files in the current working directory of your Python installation or place these files in the current working directory and then run the notebooks.
Hint: To check for the current working directory using the available notebooks just type os.getcwd() in a cell and run it. If you would like to change the current working directory before running these notebooks, use the os.chdir function, e.g. if your current working path is c:\projects, the statement you would want to execute is os.chdir("c:&#92;&#92;projects").

3. The targeted_offers.py file can be run from python command line with the following command,
**python targeted_offers.py data\portfolio.json data\transcript.json data\profile.json**

## Motivation<a name="motivation"></a>
This project was submitted a part of the Capstone project requirement for the Udacity Data Scientist Nano Degree (DSND) program. The project aims to excercise the Data Scientist skills learnt in the program. I have focused on the following key procedures that were required to logically analyze the datasets and gain more insights so as to provide an offer recommendation to the customers of the Starbucks mobile app.
1. Data Exploaration
2. Data Preparation, Cleaning and Transformation
3. Descriptive data analysis.
4. Model Building
5. Model Deployment

Apart from the above machine learning and data mining procedures that were recorded in the iron python notebook, I also tried some more heuristic data analysis on subsets of targeted population inorder to provide top two recommendations based on the majority vote of influenced customers in the analyzed subset datasets. 
## File Descriptions <a name="files"></a>

The data is contained in three files, the data names, shapes, schema and explanation of each variable in these files are below:

1. **portfolio.json - containing offer ids and meta data about each offer (duration, type, etc.)**
    *Columns*:
        id (string) - offer id
        offer_type (string) - type of offer ie BOGO, discount, informational
        difficulty (int) - minimum required spend to complete an offer
        reward (int) - reward given for completing an offer
        duration (int) - time for offer to be open, in days
        channels (list of strings)
	*Rows*: 10 

2. **profile.json - demographic data for each customer**
    *Columns*:
        age (int) - age of the customer
        became_member_on (int) - date when customer created an app account
        gender (str) - gender of the customer (note some entries contain 'O' for other rather than M or F)
        id (str) - customer id
        income (float) - customer's income
    *Rows*: 17000
	
3. **transcript.json - records for transactions, offers received, offers viewed, and offers completed**
    *Columns*
        event (str) - record description (ie transaction, offer received, offer viewed, etc.)
        person (str) - customer id
        time (int) - time in hours since start of test. The data begins at time t=0
        value - (dict of strings) - either an offer id or transaction amount depending on the record
	*Rows*: 306534

4. **Starbucks_Capstone_Project.ipynb**
    This is the iron python notebook file where a data mining procedures were followed step by step to predict offers for customers who have not transacted with the mobile app. The notebook is divided into 4 main sections where Data Exploration, Data Preparation and Cleaning, Data Analysis, Model Building and Model Deployment were showcased. Each section is numbered separately to help the reviewer understand the process in a step by step manner.

5. **targeted_offers.py**
    This is the python file containing the main() function. This file can be executed from a python 3.X commandline using the instruction provided in the ## Installation and instructions <a name="installation"></a> section.
	
## Summary Results<a name="results"></a>
In this project I analyzed the simulated datasets containing transactions on the Starbucks mobile app using two different approaches.

1. The first approach was recorded in the iron python notebook. Here, I gained insights about the dataset through data exploration techniques, built Random Forest machine learning models for each offer types, deployed these models on customer profiles who have not transacted with the mobile app and got predictions for each customer offer that we can use to forward offers on the app.

2. The second approach was recorded in the targeted_offers.py file. Here, I focused on a heuristic approach to clean, subset, analyze and recommend offers three targeted subset population.

A more detailed summary of my analysis is available in my blogpost [here]().

## Licensing, Authors, Acknowledgements<a name="licensing"></a>
Since this was a Capstone project for Udacity Data Scientist Nano Degree program, you can find more descriptions about these simulated datasets from a business perspective and also the other types of experiment we could conduct on them in this video [here](https://classroom.udacity.com/nanodegrees/nd025/parts/84260e1f-2926-4127-895f-cc4432b05059/modules/80c955ce-72f2-403a-9bf5-cc58636dab9d/lessons/d6285247-6bc0-4783-b118-6f41981b9469/concepts/480e9dc2-4726-4582-81d7-3b8e6a863450). 

Feel free to use the attached code in the iron python notebook and python code file as you would like! Keep coding to understand and apply datascience.