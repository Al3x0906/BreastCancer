# Breast Cancer Detection
## I. Definition

### Project Overview

Cancer occurs as a result of mutations, or abnormal changes, in the genes responsible for regulating the growth of cells and keeping them healthy. The genes are in each cell’s nucleus, which acts as the “control room” of each cell. Normally, the cells in our bodies replace themselves through an orderly process of cell growth: healthy new cells take over as old ones die out. But over time, mutations can “turn on” certain genes and “turn off” others in a cell. That changed cell gains the ability to keep dividing without control or order, producing more cells just like it and forming a tumor.

The term “breast cancer” refers to a malignant tumor that has developed from cells in the breast. Usually breast cancer either begins in the cells of the lobules, which are the milk-producing glands, or the ducts, the passages that drain milk from the lobules to the nipple. Less commonly, breast cancer can begin in the stromal tissues, which include the fatty and fibrous connective tissues of the breast.

Identifying correctly whether a tumor is benign or malignant is vital in deciding what is the best treatment, saving and improving the quality of life.  In this project, we used [Breast Cancer Wisconsin (Diagnostic) Data Set](https://archive.ics.uci.edu/ml/datasets/Breast+Cancer+Wisconsin+(Diagnostic)) to create a model able to predict if a tumor is or not dangerous based in characteristics that were computed from a digitized image of a [fine needle aspirate (FNA)](https://www.insideradiology.com.au/breast-fna/) of a breast mass.

Source: [BreastCancer.org](http://www.breastcancer.org/), [Inside Radiology](https://www.insideradiology.com.au/breast-fna/)


### Problem Statement
A tumor can be benign (not dangerous to health) or malignant (has the potential to be dangerous). Benign tumors are not considered cancerous: their cells are close to normal in appearance, they grow slowly, and they do not invade nearby tissues or spread to other parts of the body. Malignant tumors are cancerous. Left unchecked, malignant cells eventually can spread beyond the original tumor to other parts of the body. As the physical aspects of the malignant tumor differ from the benign tumor cells, we can measure the physical characteristics such as radius (mean of distances from center to points on the perimeter), texture (standard deviation of gray-scale values), perimeter, area, smoothness, compactness, concavity, concave points, symmetry or fractal dimension to understand and create two classes of tumor and identify which class each tumor belongs for new samples. 

### Metrics

In tumor cells classification is important to avoid false negatives because if a malignant tumor is predict as benign the patient will not receive treatment. That's why F1 is a ideal metric to score our model.

recall = True positive / (True positive + False negative)

precision = True positive / (True positive + False positive)


The final model I will analyze the model performance ploting a confusion matrix and score model using [F1 Score](<https://en.wikipedia.org/wiki/F1_score>) that is a methot to measure performance of binary classification, the F1 score is a measure of a test's accuracy, is the harmonic average of the precision and recall, where an F1 score reaches its best value at 1 (perfect precision and recall) and worst at 0.



Using [F1 Score](https://en.wikipedia.org/wiki/F1_score) formula.

In statistical analysis of binary classification, the F1 score  is a measure of a test's accuracy. It considers both the precision p and the recall r of the test to compute the score: p is the number of correct positive results divided by the number of all positive results returned by the classifier, and r is the number of correct positive results divided by the number of all relevant samples (all samples that should have been identified as positive). The F1 score is the harmonic average of the [precision and recall](https://en.wikipedia.org/wiki/Precision_and_recall), where an F1 score reaches its best value at 1 (perfect precision and recall) and worst at 0.
### Result
|index|Algorithm|Accuracy|Recall|Precision|F1\_score|
|---|---|---|---|---|---|
|0|SVC\(gamma=0\.01\)|63\.1578947368421|2\.3255813953488373|100\.0|0\.045454545454545456|
|1|SVC\(C=60, coef0=1, degree=2, kernel='poly'\)|96\.49122807017544|90\.69767441860465|100\.0|0\.951219512195122|
|2|LinearSVC\(C=50, loss='hinge'\)|92\.98245614035088|100\.0|84\.31372549019608|0\.9148936170212767|
|3|XGBClassifier\(\)|95\.6140350877193|93\.02325581395348|95\.23809523809523|0\.9411764705882352|
|4|RandomForestClassifier\(\)|95\.6140350877193|93\.02325581395348|95\.23809523809523|0\.9411764705882352|
|5|LogisticRegression\(C=63\)|99\.12280701754386|97\.67441860465115|100\.0|0\.988235294117647|
|6|DecisionTreeClassifier\(criterion='entropy', max\_depth=30\)|94\.73684210526315|90\.69767441860465|95\.1219512195122|0\.9285714285714285|
|7|AdaBoostClassifier\(\)|95\.6140350877193|93\.02325581395348|95\.23809523809523|0\.9411764705882352|
|8|GradientBoostingClassifier\(\)|95\.6140350877193|93\.02325581395348|95\.23809523809523|0\.9411764705882352|
|9|BaggingClassifier\(\)|94\.73684210526315|90\.69767441860465|95\.1219512195122|0\.9285714285714285|
|10|\<catboost\.core\.CatBoostClassifier object at 0x7fc18e04cc90\>|95\.6140350877193|93\.02325581395348|95\.23809523809523|0\.9411764705882352|
|11|DecisionTreeClassifier\(\)|92\.98245614035088|86\.04651162790698|94\.87179487179486|0\.9024390243902439|
