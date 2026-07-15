# Term Deposit Marketing

In this project, we are leveraging information from a call center to develop a machine learning solution in the European banking market. We are seeking ways to improve the success rate for product calls that we offer to our clients. We measure success rates by whether the customer subscribes to the term deposit and we have the following attributes for feature engineering:

Inputs:
#### Age: Age of customer (numeric)
---
#### Job: Type of job (categorical)
---
#### Marital: Marital Status (categorical)
---
#### Education: categorical
---
#### Default: Has credit in default? (binary)
---
#### Balance: Average yearly balance, in euros (numeric)
---
#### Housing: Has a housing plan (binary)
---
#### Loan: Has personal loan? (binary)
---
#### Contact: Contact Communication Type (categorical)
---
#### Day: Last contact day of the month (numeric)
--- 
#### Month: Last contact month of year (categorical)
---
#### Duration: Last contact duration, in seconds (numeric)
---
#### Campaign: Number of contacts performed during this campaign and for this client (numeric, includes last contact)
---
Output:
#### y - has the client subscribed to a term deposit? (binary)
---

First, I standadized the numeric columns, such as age, balance, duration, and campaign. I then encoded the categorical columns using get_dummpies. Next, I used different machine learning algorithms and the results are displayed below:

| Model | Accuracy | MAE | MSE | RMSE | R² | F1 Score | ROC AUC |
|---------|---------:|---------:|---------:|---------:|---------:|---------:|---------:|
| LogisticRegression | 0.855625 | 0.144375 | 0.144375 | 0.379967 | -1.150458 | 0.452347 | 0.918624 |
| RandomForestClassifier | 0.857375 | 0.142625 | 0.142625 | 0.377657 | -1.124392 | 0.469055 | 0.922644 |
| GradientBoosting | 0.933750 | 0.066250 | 0.066250 | 0.257391 | 0.013210 | 0.411111 | 0.942164 |
| XGBClassifier | 0.865375 | 0.134625 | 0.134625 | 0.366913 | -1.005232 | 0.490780 | 0.942316 |
| LGBMClassifier | 0.694250 | 0.305750 | 0.305750 | 0.552947 | -3.554130 | 0.319421 | 0.940729 |
| SGDClassifier | 0.842875 | 0.157125 | 0.157125 | 0.396390 | -1.340369 | 0.438589 | 0.918363 |
| BernoulliNB | 0.917875 | 0.082125 | 0.082125 | 0.286575 | -0.223248 | 0.173585 | 0.834185 |
| GaussianNB | 0.881375 | 0.118625 | 0.118625 | 0.344420 | -0.766913 | 0.362660 | 0.817221 |
| NearestCentroid | 0.887875 | 0.112125 | 0.112125 | 0.334851 | -0.670096 | 0.467023 | 0.907934 |
| Perceptron | 0.767625 | 0.232375 | 0.232375 | 0.482050 | -2.461213 | 0.346113 | 0.889849 |
| LinearDiscriminantAnalysis | 0.930000 | 0.070000 | 0.070000 | 0.264575 | -0.042646 | 0.459459 | 0.911588 |
| RidgeClassifier | 0.868625 | 0.131375 | 0.131375 | 0.362457 | -0.956824 | 0.464049 | 0.909740 |
| RidgeClassifierCV | 0.868625 | 0.131375 | 0.131375 | 0.362457 | -0.956824 | 0.464049 | 0.909740 |

According to the metrics, XGBClassifier appears to have the highest ROC AUC score, so I used this to plot the feature importance. Even though GradientBoosting has a higher accuracy, the confusion matrix shows a high percentage for miss-classification. Therefore, XGBClassifer, with the accuracy level of 0.865375, is the most optimal machine learnign algorithm for predicting term subscription.

I used KMeans for the elbow plot and determined the optimal number of clusters to be 3. I then plotted the histograms for the columns for each cluster.

## Cluster 0
Age: Younger than average.
Balance: Mostly average to below-average balances, with a few very high outliers.
Duration: Slightly shorter-than-average call durations.
Campaign: Generally few campaign contacts.
Job: Mainly management, technician, admin, and blue-collar workers.
Marital: Mostly single and married customers.
Education: Predominantly secondary education, followed by tertiary.
Housing Loan: Slightly more customers have housing loans.
Contact: Primarily contacted via cellular.
Month: Most contacts occurred in Q2.
Default: Very low credit default rate.
Personal Loan: Most do not have personal loans.
Day: Contacts spread across the month, slightly higher toward the end.

## Cluster 1
Age: Older than average.
Balance: Mostly average balances with a few high-balance outliers.
Duration: Around average to slightly shorter call durations.
Campaign: Generally few campaign contacts.
Job: Predominantly retired, with many management and technician workers.
Marital: Mostly married customers.
Education: Mainly secondary education, followed by tertiary.
Housing Loan: Most do not have housing loans.
Contact: Primarily contacted via cellular.
Month: Most contacts occurred in Q2.
Default: Very low credit default rate.
Personal Loan: Personal loans are uncommon.
Day: Contacts evenly distributed throughout the month.

## Cluster 2
Age: Around the average age with the widest age range.
Balance: Mostly average balances with a few very high outliers.
Duration: Around-average call durations with few long calls.
Campaign: Generally few campaign contacts.
Job: Mainly technicians, followed by blue-collar and management workers.
Marital: Mostly married customers.
Education: Predominantly secondary education, followed by tertiary.
Housing Loan: Slightly more customers have housing loans.
Contact: Primarily contacted via cellular.
Month: Most contacts occurred in Q2.
Default: Very low credit default rate.
Personal Loan: Most do not have personal loans.
Day: Contacts spread fairly evenly across the month, with a slight mid-month concentration.




