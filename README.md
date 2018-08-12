# NaiveBayes
10-fold CV Naive Bayes Classifier on BoW and TF-IDF vectorized Reviews with Optimal Alpha

# Amazon Fine Food Reviews Analysis #

Data Source: https://www.kaggle.com/snap/amazon-fine-food-reviews

## Objective: ##
To find Precision, Recall, F1 Score, Confusion Matrix, Accuracy of 10-fold cross validation
Naive Bayes on vectorized input data, for BoW and TF-IDF featurizations. TPR, TNR, FPR
and FNR is calculated for both. The most frequent words in positive and negative class also
needs to eb found out

## At a glance: ##
Random Sampling is done to reduce input data size and time based slicing to split into training
and testing data. The metrics obtained by applying 10-fold cross validation with Naive Bayes
using BoW and tf-idf featurizations are compared to find optimal alpha for smoothing.
The accuracy for different alpha values are plotted. The performance metrics with both featurizations
are computed. Most frequent words in both classes are also enumerated.

## Laplace Smoothing: ##
Range of Alpha: taken values ranging from ** 10ˆ-6 to 10ˆ3**
To try out different values of alpha, Geometric Progression is used as step function in the
above alpha range.

## Plots ##

![nb1](https://github.com/AdroitAnandAI/NaiveBayes/blob/master/Images/nb1.PNG)

## Summary Table ##

![nb2](https://github.com/AdroitAnandAI/NaiveBayes/blob/master/Images/nb2.PNG)
![nb3](https://github.com/AdroitAnandAI/NaiveBayes/blob/master/Images/nb3.PNG)
![nb4](https://github.com/AdroitAnandAI/NaiveBayes/blob/master/Images/nb4.PNG)

## Observations ##
1. F1 Score of "Count based BoW with Multinomial NB" is slightly higher than "Binary BoW with Bernoulli NB" method. This indicates the loss of information when the count vector is made binary.

2. Accuracy of TF-IDF method is 2% less than that we got from BoW method.

3. TNR and Recall of TF-IDF with Multinomial NB method is as high as 99%. This indicates the negative reviews are identified properly with only 1% false positive rate. 

4. If we need a system with a prime requirement to correctly idenfity as many negative reviews as possible, then "Multinomial NB on tf-IDF" should be used (as TNR = 0.99)

5. TPR of TF-IDF with Multinomial NB method is low (26%). 74% of positive reviews are not identified correctly (FPR = 0.74)

6. TPR of "BoW with Multinomial NB" has the highest F1 Score, amongst all the three methods. Hence, Bag of Words featurization with multinomial Naive Bayes is the classifer of choice.

7. Naive Bayes algorithm is based on Bayes’ theorem with a strong (naive) conditional independence assumption between the features. Hence, working with w2v features which are completely dependent is not a good idea. Naive Bayes on W2V and tf-idf weighted W2v
is not done for this reason.
