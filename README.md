
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

		Calculate and print the accuracy score of the model.

			balanced_accuracy_score(y_test, testing_predict)
			
			0.9519422040258451

		Generates a confusion matrix.

			confusion_matrix(y_test, testing_predict)

			array([[18652,    87],
       			       [   59,   586]])

		Prints the classification report.

			print(classification_report(y_test, testing_predict))

			              precision    recall  f1-score   support

			           0       1.00      1.00      1.00     18739
           			   1       0.87      0.91      0.89       645

			    accuracy                           0.99     19384
			   macro avg       0.93      0.95      0.94     19384
			weighted avg       0.99      0.99      0.99     19384
		
		Answers the following question: 
			
			How well does the logistic regression model predict both the 0 (healthy loan) and 1 (high-risk loan) labels?

			Looking at the confusion matrix - Number of False Positives and False Negatives are high and will need to be reduced which means the data is 
			in-correctly predicted. 

##Predict a Logistic Regression Model with Resampled Training Data

Identifies that there are a small number of high-risk loan labels. So, uses RandomOverSampler model that uses resampled training data-set to re-evaluate and see if it performs better. 

To do so, complete the following steps:

	Use the RandomOverSampler module from the imbalanced-learn library to resample the data. Be sure to confirm that the labels have an equal number of data points.

		random_oversampler = RandomOverSampler(random_state=1)
		
	Use the LogisticRegression classifier and the resampled data to fit the model and make predictions.

		ros_X, ros_y = random_oversampler.fit_resample(X_train,y_train)

		ros_y.value_counts()

		0    56297
		1    56297

	Evaluate the model’s performance by doing the following:
		
	Calculate the accuracy score of the model.

		balanced_accuracy_score(y_test,lrpredict)

		0.9949528219346048
		
	Generate a confusion matrix.

		confusion_matrix(y_test, lrpredict)

		array([[18637,   102],
		       [    3,   642]])

	Print the classification report.

	print(classification_report(y_test, lrpredict))

	              precision    recall  f1-score   support

	           0       1.00      0.99      1.00     18739
        	   1       0.86      1.00      0.92       645

	    accuracy                           0.99     19384
	    macro avg      0.93      0.99      0.96     19384
	weighted avg       1.00      0.99      0.99     19384
	
	Answer the following question: 

	How well does the logistic regression model, fit with oversampled data, predict both the 0 (healthy loan) and 1 (high-risk loan) labels?

	
	Predictions are better when Logisitic Regression Model is fit with oversampled data than the original data, False Negatives are highly reduced.
	Hence predicting with oversampled data is recommended as it reduces the overall number of incorrect predictions.

	However, in both the cases False Positives are high and are even high when predicted with oversampleddata which still remains to be reduced.

## Final Conclusion

Either of the models are not recommended..

Both the models have False Positives and False Negatives. When predicted with oversampled data though the False Negatives are much reduced, the False Positives have increased so, using any model for can get in-correct predictions. However, comparitively OverSampledData has less number of False Negatives which means more number of predictions are correct. Especially, False Positives are a major concern.

## Pre-requisites

Ensure all the below csv files are existing on the OS from where you are executing the code. You will need to run "Jupyter notebook" from the same directory (Module10-HW) where all the files exist. Below is the list of files which need to exist for the successful execution of the code.

lending_data.csv
report-template.md
credit_risk_resampling.ipynb
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
