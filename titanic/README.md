# Titanic

## Problem:

Titanic: Machine learning from Disaster
Prediction of who survived in Titanic disaster - This is one of the most popular Kaggle-competition for Data scientists

More info:
- https://www.kaggle.com/c/titanic
- https://www.kaggle.com/c/titanic-survival

### My result: Top 21% score

Current Kaggle rank 2046 out of 9870


## My solution

### Dependencies:
Requires Jupyter Notebook, can be installed https://jupyter-notebook-beginner-guide.readthedocs.io/en/latest/install.html

### How to run:

`` jupyter notebook ``

and then select project.ipynb 


## Cross-validation


I used cross-validation to decide on classifier that gives me highest accuracy. 
The classifiers I considered were:
Logistic Regression, KNN, Decision Tree, Naive Bayes, Random Forest, SVM and Kernel SVM. 
K-fold cross-validation method shows that Kernel SVM delivers highest accuracy of predictions, thus I proceeded with this classifier. 

```
  # Kernel SVM
  classifier = SVC(kernel = 'rbf',  # Gaussian kernel
                 random_state = 0)
  scoring = 'accuracy'
  score = cross_val_score(classifier, X_train, y_train, cv=k_fold, n_jobs=1, scoring=scoring)
  round(np.mean(score)*100,2)
```

 accuracy:
```
  Out: 83.16
```

Further, I run the model on test set and write predictions to result.csv in output folder. 