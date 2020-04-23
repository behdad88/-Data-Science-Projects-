## Evaluating Classification Models Performance
In machine learning, we often use the classification models to get a predicted result of population data. Classification which is one of the two sections of supervised learning, deals with data from different categories. The training dataset trains the model to predict the unknown labels of population data. There are multiple algorithms, namely, Logistic regression, K-nearest neighbour, Decision tree, Naive Bayes etc. All these algorithms have their own style of execution and different techniques of prediction. But, at the end, we need to find the effectiveness of an algorithm. To find the most suitable algorithm for a particular business problem, there are few model evaluation techniques. 

### Confusion Matrix
Probably it got its name from the state of confusion it deals with. In hypothesis testing, we define two errors as type-I and type-II. Type-I error occurs when null hypothesis is rejected which should not be in actual. And type-II error occurs when although alternate hypothesis is true, you are failing to reject null hypothesis.

<img scr="https://miro.medium.com/max/1400/1*BVoaV9v4RMi6vAcinhvJKA.png">

It is depicted clearly that the choice of confidence interval affects the probabilities of these errors to occur. But the fun is that if you try to reduce either if these errors, that will result the increase of the other one.

**what is confusion matrix?**

 <img src="https://miro.medium.com/max/1260/1*sJJZnGduFsNxlqWLMsrmBw.png">

It is a matrix representation of the results of any binary testing. For example let us take the case of predicting a disease. We have done some medical testing and with the help of the results of those tests, We are going to predict whether the person is having a disease. So, actually we are going to validate if the hypothesis of declaring a person as having disease is acceptable or not. Say, among 100 people we are predicting 20 people to have the disease. In actual only 15 people to have the disease and among those 15 people we have diagnosed 12 people correctly. So, if we put the result in a confusion matrix, it will look like the following :

<img src="https://miro.medium.com/max/1078/1*qhZlyixE7wIj0sjOQqc_mA.png">

So, will find:

1. True Positive: 12 (We have predicted the positive case correctly!)
2. True Negative: 77 (We have predicted negative case correctly!)
3. False Positive: 8 (We have predicted these people as having disease, but in actual they do not have. But do not worry, this can be rectified in further medical analysis. So, this is a low risk error. This is type-II error in this case.)
4. False Negative: 3 (We have predicted these three poor fellows as fit. But actually they have the disease. This is dangerous! Be careful! This is type-I error in this case.)

But what is the accuracy of the prediction model what I followed to get these results, the answer should be the ratio of the accurately predicted number and the total number of people which is (12+77)/100 = 0.89. If we study the confusion matrix thoroughly we will find the following things —

- The top row is depicting the total number of prediction we did as having the disease. Among these predictions we have predicted 12 people correctly to have the disease in actual. So, the ratio, 12/(12+8) = 0.6 is the measure of the accuracy of our model in detecting a person to have the disease. This is called Precision of the model.
- Now, take the first column. This column represents the total number of people who are having the disease in actual. And we have predicted correctly for 12 of them. So, the ratio, 12/(12+3) = 0.8 is the measure of the accuracy of our model to detect a person having disease out of all the people who are having the disease in actual. This is termed as Recall.

**Why do we need to measure precision or recall to evaluate the model?**
The answer is it is highly recommended when a particular result is very much sensitive. For example we are going to build a model for a bank to predict fraudulent transactions. It is not very common to have a fraudulent transaction. In 1000 transactions, there may be 1 transaction which is fraud. So, undoubtedly our model will predict a transaction as non-fraudulent very accurately. So, in this case the whole accuracy does not matter as it will be always very high irrespective of the accuracy of the prediction of the fraudulent transactions as that is of very low percentage in the whole population. But the prediction of a fraudulent transaction as non-fraudulent is not desirable. So, in this case the measurement of precision will take a vital role to evaluate the model. It will help to understand out of all the actual fraudulent transactions how many it is predicting. If it is low, even if the overall accuracy if high, the model is not acceptable.

### Receiver Operating Characteristics (ROC) Curve
Measuring the area under the ROC curve is also a very useful method for evaluating a model. ROC is the ratio of True Positive Rate (TPR) and False Positive Rate (FPR). In our disease detection example, TPR is the measure of the ratio between the number of accurate predictions of people having disease and the total number of people having disease in actual. FPR is the ratio between the number of people who are predicted as not to have disease correctly and the total number of people who are not having the disease in actual. So, if we plot the curve, it comes like this:

<img src="https://miro.medium.com/max/578/1*jbf_0S8JA_YpwlEaN66MQA.png">

The blue line denotes the change of TPR with different FPR for a model. More the ratio of the area under the curve and the total area (100 x 100 in this case) defines more the accuracy of the model. If it becomes 1, the model will be overfit and if it is equal below 0.5 (i.e when the curve is along the dotted diagonal line), the model will be too inaccurate to use.