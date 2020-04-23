## Evaluating Classification Models Performance
In machine learning, we often use the classification models to get a predicted result of population data. Classification which is one of the two sections of supervised learning, deals with data from different categories. The training dataset trains the model to predict the unknown labels of population data. There are multiple algorithms, namely, Logistic regression, K-nearest neighbour, Decision tree, Naive Bayes etc. All these algorithms have their own style of execution and different techniques of prediction. But, at the end, we need to find the effectiveness of an algorithm. To find the most suitable algorithm for a particular business problem, there are few model evaluation techniques. 

### Confusion Matrix

<img scr="https://miro.medium.com/max/1780/1*LQ1YMKBlbDhH9K6Ujz8QTw.jpeg">

Probably it got its name from the state of confusion it deals with. In hypothesis testing, we define two errors as type-I and type-II. Type-I error occurs when null hypothesis is rejected which should not be in actual. And type-II error occurs when although alternate hypothesis is true, you are failing to reject null hypothesis.

<img scr="https://miro.medium.com/max/1400/1*BVoaV9v4RMi6vAcinhvJKA.png">

It is depicted clearly that the choice of confidence interval affects the probabilities of these errors to occur. But the fun is that if you try to reduce either if these errors, that will result the increase of the other one.

**what is confusion matrix?**

 <img src="https://miro.medium.com/max/1260/1*sJJZnGduFsNxlqWLMsrmBw.png">

It is a matrix representation of the results of any binary testing. For example let us take the case of predicting a disease. We have done some medical testing and with the help of the results of those tests, We are going to predict whether the person is having a disease. So, actually we are going to validate if the hypothesis of declaring a person as having disease is acceptable or not. Say, among 100 people we are predicting 20 people to have the disease. In actual only 15 people to have the disease and among those 15 people we have diagnosed 12 people correctly. So, if we put the result in a confusion matrix, it will look like the following :

<img src="https://miro.medium.com/max/1078/1*qhZlyixE7wIj0sjOQqc_mA.png">

So, will find:

1. **True Positive**: 12 (We have predicted the positive case correctly!)
2. **True Negative**: 77 (We have predicted negative case correctly!)
3. **False Positive**: 8 (We have predicted these people as having disease, but in actual they do not have. But do not worry, for example this can be rectified in further medical analysis. So, this is a low risk error. This is type-I error. It is some kind of 'warning'.)
4. **False Negativ**e: 3 (We have predicted these three poor fellows as fit. But actually they have the disease. This is dangerous! Be careful! Because once you say something is not going to happen but it actually does happen then you can't even be prepared for it. This is type-II error.)

<img src="https://strata.uga.edu/8370/lecturenotes/images/errors.png">


> In statistical hypothesis testing, a type `I error` is the rejection of a true null hypothesis (also known as a "false positive" finding or conclusion), while a type `II error` is the non-rejection of a false null hypothesis (also known as a "false negative" finding or conclusion).

- **Type-I error**: The first kind of error is the rejection of a true null hypothesis as the result of a test procedure. This kind of error is called a type I error and is sometimes called an error of the first kind.


- **Type-II error**: The second kind of error is the failure to reject a false null hypothesis as the result of a test procedure. This sort of error is called a type II error and is also referred to as an error of the second kind.

But what is the accuracy of the prediction model what I followed to get these results, the answer should be the ratio of the accurately predicted number and the total number of people which is (12+77)/100 = 0.89. If we study the confusion matrix thoroughly we will find the following things —

- The top row is depicting the total number of prediction we did as having the disease. Among these predictions we have predicted 12 people correctly to have the disease in actual. So, the ratio, 12/(12+8) = 0.6 is the measure of the accuracy of our model in detecting a person to have the disease. This is called Precision of the model.
- Now, take the first column. This column represents the total number of people who are having the disease in actual. And we have predicted correctly for 12 of them. So, the ratio, 12/(12+3) = 0.8 is the measure of the accuracy of our model to detect a person having disease out of all the people who are having the disease in actual. This is termed as Recall.

**Why do we need to measure precision or recall to evaluate the model?**
The answer is it is highly recommended when a particular result is very much sensitive. For example we are going to build a model for a bank to predict fraudulent transactions. It is not very common to have a fraudulent transaction. In 1000 transactions, there may be 1 transaction which is fraud. So, undoubtedly our model will predict a transaction as non-fraudulent very accurately. So, in this case the whole accuracy does not matter as it will be always very high irrespective of the accuracy of the prediction of the fraudulent transactions as that is of very low percentage in the whole population. But the prediction of a fraudulent transaction as non-fraudulent is not desirable. So, in this case the measurement of precision will take a vital role to evaluate the model. It will help to understand out of all the actual fraudulent transactions how many it is predicting. If it is low, even if the overall accuracy if high, the model is not acceptable.

**In summary we can find these from confusion matrix:**

- **Accuracy**: Overall, how often is the classifier correct?
    - (TP+TN)/total
- **Misclassification Rate**: Overall, how often is it wrong?
    - (FP+FN)/total
    - equivalent to 1 minus Accuracy
    - also known as "Error Rate"
- **True Positive Rate**: When it's actually yes, how often does it predict yes?
    - TP/actual yes 
    - also known as "Sensitivity" or "Recall"
- **False Positive Rate**: When it's actually no, how often does it predict yes?
    - FP/actual no 
- **True Negative Rate**: When it's actually no, how often does it predict no?
    - TN/actual no
    - equivalent to 1 minus False Positive Rate
    - also known as "Specificity"
- **Precision**: When it predicts yes, how often is it correct?
    - TP/predicted yes
- **Prevalence**: How often does the yes condition actually occur in our sample?
    - actual yes/total 
    
### Receiver Operating Characteristics (ROC) Curve and cumulative accuracy profile (CAP)
While there are several metrics such as Accuracy and Recall to measure the performance of a Machine Learning model, ROC Curve and CAP Curve are great for classification problems.

#### Receiver Operating Characteristic (ROC) Curve
The Receiver Operating Characteristic Curve, better known as the ROC Curve, is an excellent method for measuring the performance of a Classification model. The True Positive Rate (TPR) is plot against False Positive Rate (FPR) for the probabilities of the classifier predictions.
Measuring the area under the ROC curve is also a very useful method for evaluating a model. ROC is the ratio of True Positive Rate (TPR) and False Positive Rate (FPR). In our disease detection example, TPR is the measure of the ratio between the number of accurate predictions of people having disease and the total number of people having disease in actual. FPR is the ratio between the number of people who are predicted as not to have disease correctly and the total number of people who are not having the disease in actual. So, if we plot the curve, it comes like this:

<img src="https://miro.medium.com/max/578/1*jbf_0S8JA_YpwlEaN66MQA.png">

The blue line denotes the change of TPR with different FPR for a model. More the ratio of the area under the curve and the total area (100 x 100 in this case) defines more the accuracy of the model. If it becomes 1, the model will be overfit and if it is equal below 0.5 (i.e when the curve is along the dotted diagonal line), the model will be too inaccurate to use.
Simply, after calculating the area under the plot. More the area under the curve, better is the model at distinguishing between classes.


#### Cumulative Accuracy Profile (CAP) Curve
The CAP Curve tries to analyse how to effectively identify all data points of a given class using minimum number of tries.
To understand the intuition behind it, You have to follow me in the following scenarios:
- Scenario-1 — Imagine that you as a data scientist work in a company that want to promote its new product so they will send an email with their offer to all the customers and usually 10% of the customer responses and actually buys the product so they though that that will be the case for this time and that scenario is called the Random Scenario.

<img src="https://miro.medium.com/max/938/1*hyy93x3O33xAkD2i_MKl4A.png">

- Scenario-2 — You still work in the same company but this time you decided to do it in a more systematic way:
     1. Inspect your historical data and take a group of customers who actually bought the offer and try to extract those information (browsing device type (mobile or laptop), Age, Salary, Savings)
     2. Measure those factors and try to discover which of them affects the number of Purchased products or in other words fit the data to a Logistic Regression model.
     3. Make a prediction of which customers are more likely to purchase the product.
     4. Then specially target those people which you predicted are more likely to buy the product.
     5. Then by measuring the response of those targeted group represented in that curve ‘CAP Curve’.

We definitely can notice the improvement; when you contacted 20,000 targeted customers you got about 5,000 positive responses where in scenario#1 by contacting the same number of customers, you got only 2,000 positive responses.

<img src="https://miro.medium.com/max/894/1*u8LCJT0W8L4vK7-zcrauJA.png">

So, the idea here is to compare your model to the random scenario and you can take it to the next level by building another model maybe a Support Vector Machine (SVM)/ Kernel SVM model to compare it with your current logistic regression model.

<img src="https://miro.medium.com/max/1258/1*MwMkGKBRrl69ydF7MfJ9OQ.png">

But, How to analyze the resulting graph ?
The better your model, the larger will be the area between its CAP curve and the random scenario straight line.
Hypothetically we can draw the so called The Perfect Model which represents a model which is kind of impossible to build unless you have some sort of a Crystal Ball . It shows that when sending the offer to 10,000 possible customer you got a perfect positive response where all contacted people bought the product.
Plotting such a hypothetical model will help us as a reference to evaluate your models CAP curves.

<img src="https://miro.medium.com/max/1222/1*mZ6QpPsIyIZ-1SDz6L-HeA.png">


#### There are 2 approaches to analyze the previous graph:
**First**:
- Calculate area under the Perfect Model Curve (aP)
- Calculate area under the Cap Curve (aR)
- Calculate Accuracy rate(AR) = aR/ aP; as (AR)~1 (The better is your model) and as (AR)~0 (The worse is your model).

**Second**:
Draw a line from the 50% point (50,000) in the Total Contacted axis up to the Model CAP Curve. Then from that intersection point, Project it to the Purchased axis. This X% value represents how good your model is:
- If X < 60% /(6000) then you have a rubbish model
- If 60% < X < 70% /(7000) then you have a poor model
- If 70% < X < 80% /(8000) then you have a good model
- If 80% < X < 90%/ (9000) then you have a very good model
- If 90% < X < 100% / (10,000) then your model is too good to be true! what I mean is that, this usually happens due Overfitting which is definitely not a good thing as your model will be good in classifying only the data it is trained on but very poor with new unseen instances.

#### A couple other terms are also worth mentioning:

- **Null Error Rate**: This is how often you would be wrong if you always predicted the majority class. This can be a useful baseline metric to compare your classifier against. However, the best classifier for a particular application will sometimes have a higher error rate than the null error rate, as demonstrated by the Accuracy Paradox.
- **Cohen's Kappa**: This is essentially a measure of how well the classifier performed as compared to how well it would have performed simply by chance. In other words, a model will have a high Kappa score if there is a big difference between the accuracy and the null error rate. 
- **F Score**: This is a weighted average of the true positive rate (recall) and precision.

Refrencee and more info : [wikipedia-False-positives-and-false-negatives](https://en.wikipedia.org/wiki/False_positives_and_false_negatives),[wikipedia-Type-I-and-type-II-errors](https://en.wikipedia.org/wiki/Type_I_and_type_II_errors) and  [wikipedia-Confusion-matrix](https://en.wikipedia.org/wiki/Confusion_matrix)