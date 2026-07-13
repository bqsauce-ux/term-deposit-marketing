# Term Deposit Marketing

In this project, we are leveraging information from a call center to develop a machine learning solution in the European banking market. We are seeking ways to improve the success rate for product calls that we offer to our clients. We measure success rates by whether the customer subscribes to the term deposit and we have the following attributes for feature engineering:

Inputs:
Age: Age of customer (numeric)
---
Job: Type of job (categorical)
---
Marital: Marital Status (categorical)
---
Education: categorical
---
Default: Has credit in default? (binary)
---
Balance: Average yearly balance, in euros (numeric)
---
Housing: Has a housing plan (binary)
---
Loan: Has personal loan? (binary)
---
Contact: Contact Communication Type (categorical)
---
Day: Last contact day of the month (numeric)
--- 
Month: Last contact month of year (categorical)
---
Duration: Last contact duration, in seconds (numeric)
---
Campaign: Number of contacts performed during this campaign and for this client (numeric, includes last contact)
---
Output:
y - has the client subscribed to a term deposit? (binary)
---

First, I standadized the numeric columns, such as age, balance, duration, and campaign. I then encoded the categorical columns using get_dummpies. Next, I used different machine learning algorithms and the results are displayed below:


# Cluster 0
Age: Distribution is centered below 0, with most values between approximately -1.2 and -0.2. Customers in Cluster 0 tend to be younger than the overall average. There are relatively few older customers.
Balance: Strong right-skewed distribution. Most observations are clustered near or below the mean, with a few very large positive values.	Most customers have below-average or average account balances, while a small number of customers have very high balances (outliers).
Duration: Distribution peaks slightly below 0, although it spans both negative and positive values.	Call durations are generally slightly shorter than the dataset average, with some longer calls present.
Campaign: Most observations are at 0 or very low values with a long right tail.	Below-average campaign contacts are typical for this cluster. Very high campaign counts are uncommon.
Job	Management, technician, admin, and blue-collar are the largest groups. These occupations are more common in Cluster 0, while retired, student, housemaid, and unemployed are less common.
Marital	Single and married dominate; divorced is relatively rare. The cluster is primarily composed of single and married customers.
Education	Secondary education is the largest category, followed by tertiary. Secondary education is above average within this cluster, while primary and unknown education occur less frequently.
Housing Loan: Both yes and no are represented, with "Yes" appearing slightly more frequent.	Housing loans are fairly common in this cluster.
Contact:Cellular contact overwhelmingly dominates. Customers are primarily contacted by cellular phone; telephone and unknown contacts are much less common.
Month: Q2 has the highest frequency, followed by Q1.Most contacts occurred during Q2, while Q3 and Q4 are less represented. Default	Almost every customer has No default, with very few Yes. Cluster 0 has a very low credit default rate, indicating generally good credit history.
Personal Loan	The majority of customers have No personal loan. Most customers do not have personal loans.
Day (Week)	Contacts are distributed across all four weeks, with a slight increase during the third and fourth weeks. There is no strong weekly contact pattern, although contacts appear somewhat more frequent toward the end of the month.

## Cluster 1
Age	Distribution is centered above 0, with most values between about 0.5 and 1.5.	Customers are older than the overall average.
Balance	Strongly right-skewed. Most customers have balances near the mean with a few very large outliers.	Most customers have average to slightly below-average balances, while a few have exceptionally high balances.
Duration	Distribution is centered slightly below 0 with a long right tail.	Call durations are around average to slightly below average, although some customers had much longer calls.
Campaign	Most values are close to 0 with a long right tail.	Customers were contacted relatively few times, with only a few receiving many campaign contacts.
Job	Retired is the largest category, followed by management and technician.	This cluster contains a high proportion of retired customers, with management and technician also well represented.
Marital	Married customers dominate; divorced and single are much less common.	The cluster is composed primarily of married customers.
Education	Secondary education is the largest group, followed by tertiary.	Secondary education predominates, while primary and unknown education are less frequent.
Housing Loan	"No" is much more common than "Yes".	Most customers do not have a housing loan.
Contact	Cellular is overwhelmingly the primary contact method.	Customers are primarily contacted via cellular phone.
Month	Q2 has the highest frequency.	Most marketing contacts occurred during Q2.
Default	Almost all customers have No default.	Very few customers have a history of credit default.
Loan	Most customers have No personal loan.	Personal loans are uncommon in this cluster.
Day	Contacts are spread fairly evenly across the month, with a slight concentration in the middle.	There is no strong day-of-month pattern for contacts.

## Cluster 2
Age	Distribution is centered around 0 with values spread on both sides.	Customers are close to the overall average age, with a wider age range than the other clusters.
Balance	Strongly right-skewed with most balances near the mean and a few large outliers.	Most customers have average balances, while a small number have very high account balances.
Duration	Distribution is concentrated around the center with fewer long calls.	Call durations are around the dataset average, with relatively few extremely long calls.
Campaign	Most customers were contacted only a few times; distribution has a long right tail.	Customers generally received few campaign contacts, with only a small number contacted many times.
Job	Technician is the largest occupation, followed by blue-collar and management.	The cluster is dominated by technicians, with substantial representation from blue-collar and management occupations.
Marital	Married customers are the largest group, followed by single customers; divorced is least common.	The cluster consists primarily of married customers.
Education	Secondary education is the largest category, followed by tertiary.	Most customers have secondary education, while tertiary education is also common.
Housing Loan	"Yes" appears slightly more common than "No".	A relatively large proportion of customers have housing loans.
Contact	Cellular is overwhelmingly the dominant contact method.	Customers are contacted primarily via cellular phone.
Month	Most contacts occurred during Q2, with fewer in Q3 and Q4.	Marketing activity is concentrated in Q2.
Default	Almost all customers have No default.	The cluster has a very low credit default rate.
Loan	Customers without personal loans are more common than those with loans.	Most customers do not have personal loans.
Day	Contacts are spread across the month with a slight concentration in the middle.




