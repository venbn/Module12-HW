
## Dev

I use Jupyter notebook to write the Python code, this code is built in Jupyter notebook on a Mac PC. 
The process must be pretty much same when executing from GitBash on WindowsPC except that you will need Visual Studio Code to install required extensions/moduled.
To ensure, a suitable environment is existing to execute this code, you will need to have python3 and pip3 installed already. 
Python versions older than 3 might not function effeciently. The Python version used to write this code is 3.10.6, any verison of Python3 should work.

## Dependencies

Apart from python3 and pip3, you will need to have jupyter, anaconda and matplotlib installed at the operating system level.
All the dependent librariries required to successfully use pandas and sklearn modules must be installed, the code is heavily dependent on pandas, hvplot,pathlib and sklearn modules.

Following modules must be already installed before running the code and conda environment must be activated as well. To execute the code, Jupyter notebook must be used. 

Below commands are Mac compatible.

pip3 install conda
pip3 install anaconda3
pip3 install scikit-learn

Since the code performs predictive analysis on imbalanced data, below module needs to be installed

python3 -m pip install -U imbalanced-learn

Before running the code, conda environment must be created and activated.

conda create -n cenv python=3.10.6
conda activate cenv

## What does code perform ?

The code performs the following...

Split the Data into Training and Testing Sets
Open the starter code notebook and then use it to complete the following steps.

Read the lending_data.csv data from the Resources folder into a Pandas DataFrame.

Create the labels set (y) from the “loan_status” column, and then create the features (X) DataFrame from the remaining columns.

Note A value of 0 in the “loan_status” column means that the loan is healthy. A value of 1 means that the loan has a high risk of defaulting.

Check the balance of the labels variable (y) by using the value_counts function.

Split the data into training and testing datasets by using train_test_split.

## Create a Logistic Regression Model with the Original Data

Use logistic regression to complete the following steps:

	Fit a logistic regression model by using the training data (X_train and y_train).

	Save the predictions on the testing data labels by using the testing feature data (X_test) and the fitted model.

	Evaluate the model’s performance by doing the following:

		Calculate the accuracy score of the model.

		![]LRM-BalancedAccuracyModel.png

		Generate a confusion matrix.

		Print the classification report.

		Answer the following question: 
			
			How well does the logistic regression model predict both the 0 (healthy loan) and 1 (high-risk loan) labels?

##Predict a Logistic Regression Model with Resampled Training Data

Did you notice the small number of high-risk loan labels? 

Perhaps, a model that uses resampled data will perform better. You’ll thus resample the training data and then reevaluate the model. Specifically, you’ll use RandomOverSampler.

To do so, complete the following steps:

	Use the RandomOverSampler module from the imbalanced-learn library to resample the data. Be sure to confirm that the labels have an equal number of data points.

	Use the LogisticRegression classifier and the resampled data to fit the model and make predictions.

	Evaluate the model’s performance by doing the following:

	Calculate the accuracy score of the model.

	Generate a confusion matrix.

		Print the classification report.

			Answer the following question: 

				How well does the logistic regression model, fit with oversampled data, predict both the 0 (healthy loan) and 1 (high-risk loan) labels?

## Write a Credit Risk Analysis Report

For this section, you’ll write a brief report that includes a summary and an analysis of the performance of both machine learning models that you used in this challenge. You should write this report as the README.md file included in your GitHub repository.

Structure your report by using the report template that Starter_Code.zip includes, and make sure that it contains the following:

An overview of the analysis: Explain the purpose of this analysis.
The results: Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of both machine learning models.

A summary: Summarize the results from the machine learning models. Compare the two versions of the dataset predictions. Include your recommendation for the model to use, if any, on the original vs. the resampled data. If you don’t recommend either model, justify your reasoning.
 
## Final Conclusion


## Pre-requisites

Ensure all the below csv files are existing on the OS from where you are executing the code. You will need to run "Jupyter notebook" from the same directory (Module10-HW) where all the files exist. Below is the list of files which need to exist for the successful execution of the code.

crypto_market_data.csv
crypto_investments.ipynb
README.md

Git must be installed. If using Windows GitBash must be installed.

To execute the code from Windows - you will need Visual Studio Code installed as well to look at the code.

The file 'crypto_investments.ipynb' is the file to be opened from the 'Jupyter notebook' interface ONLY.

## Execution process

Clone the directory which contains all the .csv files and the .ipynb file to your system using the following commands

git clone https://github.com/venbn/Module10-HW.git

Once the clone completes.. 

Go to the directory "Module10-HW"

cd Module10-HW

Execute 'Jupyter notebook' command

In the Jupyter notebook interface, open the file 'crypto_investments.ipynb'

You should be able to see the code
