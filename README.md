# Bankruptcy detection
---

# 1.0 Aim
- To predict whether a given company can go **Bankrupt**.
![](https://github.com/sanjayd89/Bankruptcy_detection/blob/main/images/bankruptcy.jpg)
- The data were collected from the Taiwan Economic Journal for the years 1999 to 2009. Company bankruptcy was defined based on the business regulations of the Taiwan Stock Exchange.
- The dataset considered here has 95 independent features and 1 dependent feature.
- The aim here is to see the effect of various sampling techniques for handling Imbalanced Dataset.
![](https://github.com/sanjayd89/Bankruptcy_detection/blob/main/images/imbalancedata.jpg)

# 2.0 Approach
- Following will be approach towards the problem statement:
  - Handle Outliers
  - Reduce number of features using Feature Selection Techniques
  - Handle Imbalance data
 
# 3.0 Preprocessing
- Data Cleaning is the first step of any data analysis.
- Outliers were detected using Box plots. Below is the graph for the same.
![](https://github.com/sanjayd89/Bankruptcy_detection/blob/main/images/outlier.png)
- After careful analysis, it was found out that there were 5 features having more than 20% outliers. Hence, in order to prevent incorrect information gain thru outlier handling, these 5 columns were dropped. Graph below shows % no. of outliers in each feature:
![](https://github.com/sanjayd89/Bankruptcy_detection/blob/main/images/outlier_percentage.png)
- Using IQR technique, the outliers of remaining features were handled. Below is the box plot of cleaned data:
![](https://github.com/sanjayd89/Bankruptcy_detection/blob/main/images/cleaned_data.png)

 # 4.0 Feature Selection
 ![](https://github.com/sanjayd89/Bankruptcy_detection/blob/main/images/feature%20selection.png)
- Now, there are high number of features (95) within the dataset. 
- Various Statistical techniques like Chi-square, ANOVA, Mutual Information gain, Correlation was used to select features which are contributing the most for model prediction.
- For understanding purposes, two type of models were created
  - Logistic Regression Model : A Parametric Model
  - Random Forest Model : A Non-Parametric Model
- Logistic Regression model performance:
![](https://github.com/sanjayd89/Bankruptcy_detection/blob/main/images/Feature%20Selection%20-%20LR.png)
  - As can be seen from the graph, the Accuracy and F1 score for test data is better than the base model

- Random Forest model performance:
![](https://github.com/sanjayd89/Bankruptcy_detection/blob/main/images/Feature%20Selection%20-%20RF.png)
  - Feature Selection has negligible effect on model performance
  
# 5.0 Imbalanced dataset handling
- There are 2 methods of handling imbalanced dataset viz. Undersampling and Oversampling
![](https://github.com/sanjayd89/Bankruptcy_detection/blob/main/images/under-over-sampling.png)

- Following is the performance of sampling techniques on Logistic Regression Model:
![](https://github.com/sanjayd89/Bankruptcy_detection/blob/main/images/LR%20Performance.jpg)
- Observations:
  - Accuracy score is similar for a base model and a sampled model but the F1 score has increased by considering a combination of **SMOTE and ENN (Edited Nearest Neighbor)** sampling technique.
- Following is the performance of sampling techniques on Random Forest Model:
![](https://github.com/sanjayd89/Bankruptcy_detection/blob/main/images/RF%20Performance.jpg)
- Observations:
  - Accuracy score is similar for a base model and a sampled model but the F1 score has considerably improved considering **Edited Nearest Neighbor** sampling technique.
 
