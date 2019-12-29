# Structuring-Machine-Learning-Projects
Coursera course Structuring Machine Learning Projects by deeplearning.ai
Course Webpage https://www.coursera.org/learn/machine-learning-projects/home/welcome

1.1 Train/Dev/test distributions
- Dev and test sets should come from the same distribution. Should randomly shuffle into dev/test; On contrary, it is not a problem to have different training and dev distribution. 
Guideline: choose a dev set and test set to reflect data you expect to get in the future and consider important to do well on.
- The introduction of new data into test set can have consistent x-> Y mapping, which is not the problem

1.2 When to change dev/test sets and evalution metrics
- When customer thinks your competetor's system is better, because even though you have higher overall accuracy, you could have more false negative, then you should rethink the appproiate metric for this task, and ask your team to tune to the new metric. 
- When the performance of your system slowly degrades because your data is being tested on a new data type of data, you should use the data you have to define a new evaluation metric (using a new dev/test set) taking into account the new species, and use that to drive further progress of your team. 

1.3 Generalize to a new system
- quick experiment
- faster computers 
- speed limit 
- can't just apply directly, have to iterate
