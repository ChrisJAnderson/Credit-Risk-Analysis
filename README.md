# Credit-Risk-Analysis
## Overview
This analysis uses a variety of supervised machine learning models to predict credit risk, with the intention of finding the most accurate method to accomplish this task. We use logistic regression models using both over and undersampling, as well as a random forest classifier in BalancedRandomForestClassifier and a bag of balanced boosted learners in EasyEnsemble Classifier.
## Results
-Naive Random Oversampling:  
![](https://github.com/ChrisJAnderson/Credit-Risk-Analysis/blob/main/Images/NAIVESTATS.png)  
    I'll be treating the Naive Random Oversampling as a baseline for the others- we get an average .99 precision, and a 65% recall. If we look at the confusion matrix we see a higher number of true positives than false positives and a higher number of true negatives than false negatives. The difference in values between positives and negatives seems to make sense due to the imbalanced nature of our data. We're looking at a balanced accuracy score of .6486 to compare against our other models. 
       
-SMOTE Oversampling:  
![](https://github.com/ChrisJAnderson/Credit-Risk-Analysis/blob/main/Images/SMOTESTATS.png)  
 The SMOTE Oversampling shows us lower average recall with the same amount of precision. The confusion matrix backs this up, we see fewer true positives and true negatives than in our naive random oversampling. SMOTE performs worse than our baseline in this case. Our balanced accuracy score, .6205, is also lower than our baseline.  
-ClusterCentroids undersampling:   
  
![](https://github.com/ChrisJAnderson/Credit-Risk-Analysis/blob/main/Images/CLUSSY.png)  
Undersampling is once again proving worse than our baseline- at this point I'm beginning to question if I'm reading these stats right, or if I've done something wrong in my coding. We see an average 44% recall and a much higher value of false negatives and positives in the confusion matrix to confirm this. Balanced accuracy is considerably worse than naive oversampling, with a score of .5144.  
  
-SMOTEENN resampling:  
![](https://github.com/ChrisJAnderson/Credit-Risk-Analysis/blob/main/Images/SMOTEENNSTATS.png)  
Finally a bit of a breakthrough in SMOTEEN resampling. While our overall precision is still high and our overall recall is a little bit lower than usual, SMOTEEN does significantly better at predicting high risk customers, with a recall of 72% versus our baseline's 64%. Our balanced accuracy score is the closest to our baseline so far, although still lower, at .6291 Again, the confusion matrix contains more false negatives and positives than the naive random oversampling matrix- SMOTEEN isn't proving better overall, but it is proving better at identifying the high risk customers. 
   
-BalancedRandomForest:  
I was unable to produce scores due to an error  
  
-EasyEnsembleClassifier:  
I was unable to produce scores due to a confirmed bug  
  
## Summary
We can see that the Naive Random Oversampling produces the best overall results, with the highest average recall, the least amount of false negatives and false positives, and a slightly higher balanced accuracy score than the rest of our models.
Undersampling this data provides the least consistent results by far, with a 44% recall down from our baseline of 65%, and a balanced accuracy score of .5144 down from the .6486 of our baseline.
SMOTEEN provides marginally better results for high risk customers, but otherwise performs less consistently than naive random oversampling. My recommendation for a model to use in this case is actually SMOTEEN over naive random oversampling despite its slightly lower overall performance, as it has more probability of catching the high risk customers, and therefore saving the company from more risky lending than Naive Random Oversampling, which will in contrast assure that safer borrowers get approved more often at the cost of approving more high risk borrowers.
