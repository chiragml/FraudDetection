# FraudDetection

***
### Accuracy Score :
0.9979802922977389
Classification Report :


              precision    recall  f1-score   support

           0       1.00      1.00      1.00    240881
           1       0.00      0.00      0.00       243

   micro avg       1.00      1.00      1.00    241124
   macro avg       0.50      0.50      0.50    241124
weighted avg       1.00      1.00      1.00    241124

### Observations
Isolation Forest detected 487 errors with an accuracy of 99.79% as shown in the report above. Hence, using Isolation Forest seems optimal for this classification problem. Here, errors are the detected fraudulant transactions that were made in the sample dataset.

Furthermore, in this dataset, most important variables are "amount" and "isFraud" followed by the "oldbalanceOrg", "newbalanceOrig" as observed by using corelation matrix. I also used the mean and the standard deviation of the data to figure out the outliers of the data and filtered the complete data between the range (1.338957e+04, 2.087215e+05) of the amount column which are 25% of the mean value and 75% of the mean value respectively. Finally, I took a fraction of the resultant dataset and randomly selected 10% of that data to be the sample data for the Isolation Forrest classifier.

### selecting variables
In order to select the variables for the model, I needed to first fully understand the dataset hence I started with plotting graphs and plots using seaborn library to be able to visualize the entire data. I decided not to use the name variables like "nameDest" for the calculation purposes as these variables cannot be fed to the Forrest Algorithm for the further calculations.

After that was done, I looked at the float variables and mapped them to find the correlation between them. I found that the relation between "oldbalanceDest", "newbalanceDest" and the "amount" was relatively higher so I decided to choose them as my major independent variables and choose "isFraud" as dependent variable.

I decided to first try implementing the isolation forest algorithm taking "isFraud" as dependent and all the other float type variables as independent to see the performance and observed that the performance of the model was coming out to be 99.79% hich was more than I expected. The modeling also took a lot of time in running so I decided not to filture out indipendent variables any further.

### Factors to predict fraudulant customers
The key factors to predict the fraudulant transactions, according to the data, are the amount of the transaction and the change in balance of the destination account.

These factors, when carefully pondered upon, makes a lot of sense. Firstly, the fraudulent coustomers usually know about the 200,000 limit so they will make sure that they do the transaction of an amount below that said amount but in these cases they tend to do multiple transactions of same amount in short period of time.

### Suggested Preventions
We can improve our detection model accuracy by increasing the sample size or by using deep learning algorithms that would end up detecting other types of anomalies in transaction, however at the cost of computational expense. A relatively new way to prevent these kinds of frauds is by using the edge technology and analyze the data that the user has entered in the real time. By doing this, one can easily pause the transaction before it even gets processed and the owner of the account can automatically notified about the same.

### How do we know that these prevention measures actually work?
The suggested prevention measures can be tested regularly by adding different kinds of fraudulant transactions to a testing account once every year and then check the relative accuracy of fraud prediction. We can also introduce different types of fraudulent activities to check the algorithm's accuracy in those cases.

*** 
