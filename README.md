# Adult-Income-Classification-ML
The model with an accuracy of 85% provides an idea where the person lies in income group >=50000 or &lt;50000.

# Background:

# Assumption:
The person being sampled has provided the right income details.
The investigator is not bias while collecting the information.
The people sampled are randomly selected.

# Short-coming:
Some people might not be present at the time of sampling and were replaced by their substitutes. The substitutes might not contain the properties of the original individual.
Many people might not want to reveal their original income.

# Methods:
1.	Importing datasets and libraries:
The dataset was downloaded from Kaggle in the csv format and was imported in the jupyter notebook. Further, libraries required to create the model were imported in the notebook.

2.	Checking for null values:
Upon writing the code for checking the null values it seems there are no null values. However, further dig into the data suggests that there are ‘?’ in the dataset. These compound to the null values. Hence ‘?’ are changed to NAN values and cca and mode imputation methods were used to fill these values as per the requirement.

3.	Outlier Detection:
Columns like age, capital gain and capital loss have outliers. However, it will not be removed as they are the factors that help determine the income range of a person.

4.	Feature Engineering:
i.	Label Encoding:
The machine cannot understand >=50000 and <50000 and so we change it in the form of 0 and 1. This is done with the help of label encoder.

ii.	One Hot Encoding:
One Hot Encoding is done to encode the categorical columns. This helps the machine get a better idea as how to tackle the categorical columns. This method of encoding is only performed for nominal dataset.

iii.	Dropping the columns that are not required:
Upon finding the correlation, we see that the columns fnlwgt and education have no correlation with the other columns. Hence, these columns are dropped as keeping them would deteriorate the accuracy of the model.

5.	Model creation:
The entire data was divided into training and testing set in the ratio of 80:20 i.e. 80% of the data was training set and 20% was testing set. Multiple classification models were used to train the data. XGBoostClassifier out performed them all with an accuracy of 85% and a cross_val_score of 84.97%.

Final Verdict:
•	The model with an accuracy of 85% can predict if a person lies in an income range greater or less than 50000. The forecast help government have an idea about the income distribution and can come up with policies to help people from lower income group.
•	This model also helps government save the cost incurred during data collection.
