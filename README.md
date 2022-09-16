# Credit-Risk-Analysis
## Overview
This analysis uses a variety of supervised machine learning models to predict credit risk, with the intention of finding the most accurate method to accomplish this task. We use logistic regression models using both over and undersampling, as well as a random forest classifier in BalancedRandomForestClassifier and a bag of balanced boosted learners in EasyEnsemble Classifier.
## Results
### Balanced Accuracy scores
-Naive Random Oversampling:  
```
0.6486003843504116
```  
-SMOTE Oversampling: 
```
0.6204640406750708
```  
-ClusterCentroids Undersampling:  
```
0.5144493999057254
```  
-SMOLTEENN resampling:  
```
0.6290686150090045
```  
-BalancedRandomForest:  
I was unable to produce a score due to an error  
-EasyEnsembleClassifier:  
I was unable to produce a score due to a confirmed bug  
### Precision and Recall scores
-Naive Random Oversampling: Balanced accuracy of .6486  
```
                   pre       rec    

  high_risk       0.01      0.64  
   low_risk       1.00      0.65  

avg / total       0.99      0.65
``` 
```
[   56,    31]
[ 5931, 11187]
```    
    I'll be treating the Naive Random Oversampling as a baseline for the others- we get an average .99 precision, and a 65% recall. If we look at the confusion matrix we see a higher number of true positives than false positives and a higher number of true negatives than false negatives. The difference in values between positives and negatives seems to make sense due to the imbalanced nature of our data. We're looking at a balanced accuracy score of .6486 to compare against our other models. 
-SMOTE Oversampling: Balanced Accuracy of .6205  
```
                  pre       rec    

  high_risk       0.01      0.61      
   low_risk       1.00      0.63     

avg / total       0.99      0.63     
```
[   53,    34]
[ 6304, 10814]  
```  
    The SMOTE Oversampling shows us lower average recall with the same amount of precision. The confusion matrix backs this up, we see fewer true positives and true negatives than in our naive random oversampling. SMOTE performs worse than our baseline in this case. Our balanced accuracy score, .6205, is also lower than our baseline.  
-ClusterCentroids undersampling:  Balanced Accuracy of .5144  
```
                  pre       rec       

  high_risk       0.01      0.59     
   low_risk       1.00      0.44     
avg / total       0.99      0.44     
```  
```
[  51,   36]
[9540, 7578]
```  
    Undersampling is once again proving worse than our baseline- at this point I'm beginning to question if I'm reading these stats right, or if I've done something wrong in my coding. We see an average 44% recall and a much higher value of false negatives and positives in the confusion matrix to confirm this. Balanced accuracy is considerably worse than naive oversampling, with a score of .5144.  
-SMOTEENN resampling:  Balanced Accuracy score of .6291
``` 
                pre       rec       
  high_risk       0.01      0.72     
   low_risk       1.00      0.53      

avg / total       0.99      0.53
```  
```
[  63,   24]
[7977, 9141]
```  
    Finally a bit of a breakthrough in SMOTEEN resampling. While our overall precision is still high and our overall recall is a little bit lower than usual, SMOTEEN does significantly better at predicting high risk customers, with a recall of 72% versus our baseline's 64%. Our balanced accuracy score is the closest to our baseline so far, although still lower, at .6291 Again, the confusion matrix contains more false negatives and positives than the naive random oversampling matrix- SMOTEEN isn't proving better overall, but it is proving better at identifying the high risk customers.  
-BalancedRandomForest:  
I was unable to produce scores due to an error  
-EasyEnsembleClassifier:  
I was unable to produce scores due to a confirmed bug  
