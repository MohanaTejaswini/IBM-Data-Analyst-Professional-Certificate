
# **📝Using Data Analysis for Detecting Credit Card Fraud 📊🕵️💳**


Companies today are employing analytical techniques for the early detection of credit card frauds, a key factor in mitigating fraud damage. The most common type of credit card fraud does not involve the physical stealing of the card, but that of credit card credentials, which are then used for online purchases.

Imagine that you have been hired as a Data Analyst to work in the Credit Card Division of a bank. And your first assignment is to join your team in using data analysis for the early detection and mitigation of credit card fraud.  

In order to prescribe a way forward, that is, suggest what should be done in order for fraud to get detected early on, you need to understand what a fraudulent transaction looks like. And for that you need to start by looking at historical data. 

**Here is a sample data set that captures the credit card transaction details for a few users.**
<p align="center">
<img src="/1 - Introduction to Data Analytics /Related images/Using Data Analysis For detecting credit card Fraud_DA_1-Image_DataSet_Reading (week 5).png" width=85% height=85%>

Descriptive techniques of analysis, that is, techniques that help you gain an understanding of what happened, include the identification of patterns and anomalies in data. Anomalies signify a variation in a pattern that seems uncharacteristic, or, out of the ordinary. Anomalies may occur for perfectly valid and genuine reasons, but they do warrant an evaluation because they can be a sign of fraudulent activity.  

**Past studies have suggested that some of the common events that you may need to watch out for include:**

- A change in frequency of orders placed, for example, a customer who typically places a couple of orders a month, suddenly makes numerous transactions within a short span of time, sometimes within minutes of the previous order.

- Orders that are significantly higher than a user’s average transaction.

- Bulk orders of the same item with slight variations such as color or size—especially if this is atypical of the user’s transaction history.

- A sudden change in delivery preference, for example, a change from home or office delivery address to in-store, warehouse, or PO Box delivery.

- A mismatched IP Address, or an IP Address that is not from the general location or area of the billing address.

**Before you can analyze the data for patterns and anomalies, you need to:**

- Identify and gather all data points that can be of relevance to your use case. For example, the card holder’s details, transaction details, delivery details, location, and network are some of the data points that could be explored. 

- Clean the data. You need to identify and fix issues in the data that can lead to false or incomplete findings, such as missing data values and incorrect data. You may also need to standardize data formats in some cases, for example, the date fields. 

Finally, when you arrive at the findings, you will create appropriate visualizations that communicate your findings to your audience. The graph below samples one such visualization that you would use to capture a trend hidden in the sample data set shared earlier on in the case study.

<p align="center">
<img src="/1 - Introduction to Data Analytics /Related images/Transaction value (Transaction-USD)_DA_1-Q9-Chart.png" width=85% height=85%>

**In the next section you will be asked to answer the following 5 (five) questions based on this case study:**

1. List at least 5 (five) data points that are required for the analysis and detection of a credit card fraud. (3 marks)
   
**Answered as**
1. IP address of tranasction
2. Shipping Address
3. Transaction Details (amount, date, time, location)
4. Network information like Location and where the device is used
5. Card Holder Details

**Actual Answwer**
Card holder / Customer Id
Transaction date
Transaction time
Transaction value
Shipping address
IP address
Device model
Location

2. Identify 3 (three) errors/issues that could impact the accuracy of your findings, based on a data table provided. (3 marks)

**Answered as**
1. Missing data values in any of the required data points
2. Inaccurate of location data where the transactions done 
3. Incorrect of data formats to recognize the correct one

**Actual Answwer**
-Missing transaction value  
-Missing IP Address  
-Date format inconsistency

3. Identify 2 (two) anomalies, or unexpected behaviors, that would lead you to believe the transaction may be suspect, based on a data table provided. (2 marks)
  
**Answered as**
1. A sudden increase in frequency of transactions with in short span of time (for johnp user ID)
2. Large tranasctions higher than the user's average

**Actual Answwer**
-Significantly higher Transaction Value where Shipping Address has been changed from home/office address to P.O. Box.
-Higher Transaction Value and increased frequency of transactions.
-IP Address change and significantly higher Transaction Value.
-IP Address change and Shipping Address change

4. Briefly explain your key take-away from the provided data visualization chart. (1 mark)

**Answered as**
1.The data visualization chart likely captures the transaction value which is suddenly purchased more than the user average spend money.
2.it could show patterns of typical transactions and help identify any sudden spikes or irregularities that might inculde potential fraud activities

**Actual Answwer**
The visualization depicts the transaction values per transaction for all three users. The key take-away from this visualization is the sharp rise in the transaction values for users johnp and ellend, which may be indicative of an anomaly.  

5. Identify the type of analysis that you are performing when you are analyzing historical credit card data to understand what a fraudulent transaction looks like. [Hint: The four types of Analytics include: Descriptive, Diagnostic, Predictive, Prescriptive] (1 mark)

**Answered as**
Descriptive Analytics

**Actual Answwer**
The learner identified 'Descriptive Analytics' as the type of analysis that they are performing when they are analyzing historical credit card data to understand what a fraudulent transaction looks like.
