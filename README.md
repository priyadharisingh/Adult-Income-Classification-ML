# Adult-Income-Classification-ML
The model with an accuracy of 85% provides an idea where the person lies in income group >=50000 or &lt;50000.

# Background:
This data was extracted from the 1994 Census bureau database by Ronny Kohavi and Barry Becker (Data Mining and Visualization, Silicon Graphics). A set of reasonably clean records was extracted using the following conditions: ((AAGE>16) && (AGI>100) && (AFNLWGT>1) && (HRSWK>0)). The prediction task is to determine whether a person makes over $50K a year.<br>

### Description of fnlwgt (final weight):
The weights on the Current Population Survey (CPS) files are controlled to independent estimates of the civilian noninstitutional population of the US. These are prepared monthly for us by Population Division here at the Census Bureau. We use 3 sets of controls. These are:<br>

A single cell estimate of the population 16+ for each state.<br>

Controls for Hispanic Origin by age and sex.<br>

Controls by Race, age and sex.<br>

We use all three sets of controls in our weighting program and "rake" through them 6 times so that by the end we come back to all the controls we used. The term estimate refers to population totals derived from CPS by creating "weighted tallies" of any specified socio-economic characteristics of the population. People with similar demographic characteristics should have similar weights. There is one important caveat to remember about this statement. That is that since the CPS sample is actually a collection of 51 state samples, each with its own probability of selection, the statement only applies within state.<br>

# Assumption:
The person being sampled has provided the right income details.
The investigator is not bias while collecting the information.
The people sampled are randomly selected.

# Short-coming:
Some people might not be present at the time of sampling and were replaced by their substitutes. The substitutes might not contain the properties of the original individual.
Many people might not want to reveal their original income.

# Methods:
1.	Importing datasets and libraries: <br>
The dataset was downloaded from Kaggle in the csv format and was imported in the jupyter notebook. Further, libraries required to create the model were imported in the notebook.<br>

2.	Checking for null values:<br>
Upon writing the code for checking the null values it seems there are no null values. However, further dig into the data suggests that there are ‘?’ in the dataset. These compound to the null values. Hence ‘?’ are changed to NAN values and cca and mode imputation methods were used to fill these values as per the requirement.<br>

3.	Outlier Detection:<br>
Columns like age, capital gain and capital loss have outliers. However, it will not be removed as they are the factors that help determine the income range of a person.<br>

4.	Feature Engineering:<br>
    i.	Label Encoding:<br>
The machine cannot understand >=50000 and <50000 and so we change it in the form of 0 and 1. This is done with the help of label encoder.<br>

    ii.	One Hot Encoding:<br>
One Hot Encoding is done to encode the categorical columns. This helps the machine get a better idea as how to tackle the categorical columns. This method of encoding is only performed for nominal dataset.<br>

    iii.	Dropping the columns that are not required:<br>
Upon finding the correlation, we see that the columns fnlwgt and education have no correlation with the other columns. Hence, these columns are dropped as keeping them would deteriorate the accuracy of the model.<br>

5.	Model creation:<br>
The entire data was divided into training and testing set in the ratio of 80:20 i.e. 80% of the data was training set and 20% was testing set. Multiple classification models were used to train the data. XGBoostClassifier out performed them all with an accuracy of 85% and a cross_val_score of 84.97%.<br>

# Final Verdict:
•	The model with an accuracy of 85% can predict if a person lies in an income range greater or less than 50000. The forecast help government have an idea about the income distribution and can come up with policies to help people from lower income group.<br>
•	This model also helps government save the cost incurred during data collection.<br>
