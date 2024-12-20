# ATM-Transactions

## Executive Summary:
This report focuses on the data quality issues found in the ATM transaction dataset for May in Northern Virginia. Some of the main issues include outliers in transaction amounts and daily balances, as well as incorrect transaction dates. These issues could cause problems with analyzing data and might lead to inaccurate conclusions, especially when detecting fraud. To fix these problems, I recommend cleaning the data, removing outliers, and improving how the data is entered to make sure that future analysis is more accurate.

## Data Background:
The data comes from ATM transactions across several bank branches in Northern Virginia for the month of May. It includes information such as transaction ID, customer ID, amount of the transaction, daily balance, and transaction date/time. The bank uses this data to spot potentially fraudulent transactions, and they’re concerned that some data irregularities could be affecting the analysis. One limitation is that the dataset only covers one month, so it doesn’t provide a full picture of customer behavior over time.

## Problem Statement:
There are a few data quality issues that could impact the results of fraud detection:
-	Outliers in Balances: One customer had an unusually high daily average balance that didn’t change throughout the month, which is not typical.
-	Incorrect Transaction Date: One transaction was recorded on a date outside of May, which shouldn’t have been in the dataset.
-	Unusual Transaction Amounts: Some transactions had amounts that were much higher than what most customers usually spend, which could be a sign of fraud or data errors.
These issues could lead to inaccurate fraud detection and might affect decision-making processes.

## Methodology:
To find and address these data issues, the following steps were used:
- Exploratory Data Analysis: I looked through the dataset to check for missing or incorrect data.
-	Statistical Analysis: I calculated summary statistics (like mean and median) for transaction amounts and daily balances to identify any extreme values.
-	Data Visualization: Using Tableau, I created charts and graphs to see patterns in the data, such as high transaction amounts or strange balances. I also checked for any unusual transaction dates.

## Findings:
Here’s what I found after analyzing the data:
1.	Outlier in Daily Balance: One customer had a daily average balance of $1,000,000, which stayed the same every day. This is clearly an outlier, so this data was removed.

![Average Daily Balance Outlier](https://github.com/user-attachments/assets/b306e8e4-350c-48a2-8d98-499d94f0b210)

&nbsp;
&nbsp;

The same chart from above, but with the outliers excluded.

&nbsp;
&nbsp;

![Average Daily Balance No Outlier](https://github.com/user-attachments/assets/3e06e5f8-5af9-493c-b632-82d78bc4688a)

2.	Incorrect Transaction Date: There was one transaction that was recorded outside of May. This was corrected by removing it from the dataset.
3.	High Transaction Amounts: I identified five transactions with amounts much higher than the average transaction, ranging from $2,000 to $4,000. These could be either mistakes or signs of fraud, so they need to be looked at more closely.
   
![Mean and Median (With Outliers)](https://github.com/user-attachments/assets/534e2448-4131-4a3a-9a78-75dce3b0d647)

&nbsp;
&nbsp;

The same chart from above, but notice how much closer the average and median are. This represents a more symmetrical distribution in the data.

&nbsp;
&nbsp;

![Mean and Median (No Outliers)](https://github.com/user-attachments/assets/3ee9abea-9b67-42b8-85cc-c3e8f423127b)

&nbsp;
&nbsp; 

### Here are some summary stats:
-	Average Transaction Amount: $392.24
-	Median Transaction Amount: $280
-	Outliers in Transaction Amounts: 5 transactions had amounts over $1,500.
-	Branch with Most Transactions: Leesburg, VA had the most transactions, with 22.

## Tableau Dashboard
![KPI Dashboard](https://github.com/user-attachments/assets/00b3b3f2-2f73-40d1-b82e-94a1758a54f2)
Link to the Tableau dashboard: [ATM Transactions](https://public.tableau.com/app/profile/tyler.ross7761/viz/ATMTransactions_17315186211760/Dashboard1#1)

&nbsp;
&nbsp;

## Recommendations:
To improve the data quality and ensure more accurate analysis, I recommend the following:
1.	Data Cleaning:
-	Remove or fix outliers in the daily average balance and transaction amounts.
-	Make sure all transactions are within the correct date range.
-	Continue checking for outliers in future data to catch any issues early.
2.	Outlier Handling:
-	Set up automatic checks to find outliers in the data, like using Z-scores or other statistical methods.
-	Transactions with unusually high amounts should be flagged for review to confirm if they are legitimate.
3.	Better Data Collection:
-	Add more information to the data, like customer location or device IDs, to help detect fraud more accurately.
-	Regularly update the data set to capture more transactions and identify patterns over a longer period of time.
