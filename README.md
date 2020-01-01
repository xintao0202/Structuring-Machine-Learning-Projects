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

2.1 Error Analysis
- First ting to do when getting started on a project: Build your first system quickly, then iterate; Encourage you to build something quick and dirty and use that to do bias/variance analysis, do error analysis. And use the results of those analysis to help to prioritize where to go next. Applied ML is a highly iterative process. If you train a basic model and carry out error analysis (see what mistakes it makes) it will help point you in more promising directions.
- How to tell if traning data distribution is much easier than the dev/test distribution: If a algorithm does better on the distribution of data it trained on, it doesn't may train data distributin is easier. To get a better sense, measure human-level error separately on both distributions. 
- Prioritize fixing errors: if a category has the highest error, it doesn't mean that needs prioritized. This would depend on how easy it is to add this data and how much you think your team thinks it'll help.

2.2 Mismatched training and dev/test set
- split into train/dev/test sets: it is important that your dev and test set have the closest possible distribution to "real" data. It is also important for the training set to contain enough "real" data to avoid having a data- mismatch problem. E.g. (900,000 type A+20,000 Type B)/20,000 Type B/20,000 Type B is a good split.
- Artifical data synthesis: If the synthesized images look realistic, then the model will just see them as if you had added useful data to identify road signs and traffic signals in a foggy weather. It will very likely help.
- Deep learning algorithms are quite robust to having slightly different train and dev distributions; you want to make sure that your dev and test data come from the same distribution for your algorithm to make your team’s iterative development process is efficient.

2.3 Learning from multiple task
- Difference from multiclass classification: multiclass classification use softmax, which would be a good choice if one and only one of the possibilities (stop sign, speed bump, pedestrian crossing, green light and red light) was present in each image. But multi-task have more than one possibilities.
- Transfer learning:  start with a model with the same architecture as yours, change what is after the last hidden layer and initialize it with your trained parameters.You have trained your model on a huge dataset, and she has a small dataset. Although your labels are different, the parameters of your model have been trained to recognize many characteristics of road and traffic images which will be useful for her problem. e.g try using weights pre-trained on your dataset, and fine-tuning further with the yellow-light dataset.
- In multi-task learning, you can compute the cost such that it is not influenced by the fact that some entries haven't been labeled. E.g. if one example is [0 ? 1 1 ?], it can still be used.
- Prerequisit for transfer or multi-task learning: The problem he is trying to solve is quite different from yours. The different dataset structures make it probably impossible to use transfer learning or multi-task learning.

2.4 End-to-End Deep learning
- End-to-end approach maps directly the input (x) to the output (y).
- In many fields, it has been observed that end-to-end learning works better in practice, but requires a large amount of data.
