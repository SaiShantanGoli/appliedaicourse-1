
How to increase model accuracy of LR

Since machine learning is more about experimenting with the features and the models, there is no correct answer to your question. Some of my suggestions to you would be:

1. Feature Scaling and/or Normalization - Check the scales of your gre and gpa features. They differ on 2 orders of magnitude. Therefore, your gre feature will end up dominating the others in a classifier like Logistic Regression. You can normalize all your features to the same scale before putting them in a machine learning model.This is a good guide on the various feature scaling and normalization classes available in scikit-learn.

2. Class Imbalance - Look for class imbalance in your data. Since you are working with admit/reject data, then the number of rejects would be significantly higher than the admits. Most classifiers in SkLearn including LogisticRegression have a class_weight parameter. Setting that to balanced might also work well in case of a class imbalance.

3. Optimize other scores - You can optimize on other metrics also such as Log Loss and F1-Score. The F1-Score could be useful, in case of class imbalance. This is a good guide that talks more about scoring.

4. Hyperparameter Tuning - Grid Search - You can improve your accuracy by performing a Grid Search to tune the hyperparameters of your model. For example in case of LogisticRegression, the parameter C is a hyperparameter. Also, you should avoid using the test data during grid search. Instead perform cross validation. Use your test data only to report the final numbers for your final model. Please note that GridSearch should be done for all models that you try because then only you will be able to tell what is the best you can get from each model. Scikit-Learn provides the GridSearchCV class for this. This article is also a good starting point.

5. Explore more classifiers - Logistic Regression learns a linear decision surface that separates your classes. It could be possible that your 2 classes may not be linearly separable. In such a case you might need to look at other classifiers such Support Vector Machines which are able to learn more complex decision boundaries. You can also start looking at Tree-Based classifiers such as Decision Trees which can learn rules from your data. Think of them as a series of If-Else rules which the algorithm automatically learns from the data. Often, it is difficult to get the right Bias-Variance Tradeoff with Decision Trees, so I would recommend you to look at Random Forests if you have a considerable amount of data.

6. Error Analysis - For each of your models, go back and look at the cases where they are failing. You might end up finding that some of your models work well on one part of the parameter space while others work better on other parts. If this is the case, then Ensemble Techniques such as VotingClassifier techniques often give the best results. Models that win Kaggle competitions are many times ensemble models.

7. More Features _ If all of this fails, then that means that you should start looking for more features.

8. You could start by tuning the C parameter of logistic regression. You could also try different classification methods like SVMs and trees

9. You should not try to be optimising the accuracy on your test set. You should optimise on the training set and use the test set as an object evaluation of the method. Check accuracy score based on the training set?

10. Evaluating a model on the training set is a bad practice in general since a model fits the training data and such a score would not say anything about its generalizing ability. You should opt for cross-validation. (ii) I agree with the points of Abhinav below. try normalizing your gre and gpa, because their values dominate your feature vector
