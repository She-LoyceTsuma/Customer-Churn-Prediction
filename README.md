# Sunborn(Luxury Brand) - Customer Churn Prediction
The CRISP DM(Cross -Industry Standard Process for Data Mining) Approach

![image](https://github.com/user-attachments/assets/ce8e3adc-dbac-4327-8436-4b4baa2a423f)




## About Sunborn

Sunborn is a family business group with a legacy spanning five decades, primarily focused on yacht hospitality. 

They engage in innovative maritime construction and development, manage healthcare assets, and own real estate across diverse sectors.

As competition intensifies and market saturation increases, customer retention has become essential, as acquiring new customers is significantly more costly. 

Research indicates that retaining existing customers can lead to substantial profit increases, highlighting the importance of investing in effective customer retention strategies.

## The Classification Problem


<img width="500" alt="image" src="https://github.com/user-attachments/assets/34b22cdf-83f6-4d1d-83a0-5d3494ffeca5">





The task is to predict whether a customer will continue living in their rental yatch or vacate (i.e., churn). This model could be critical for luxury real estate and maritime hospitality developers to understand customer behavior and implement retention strategies

The project aims to:

- Identify key features influencing customer churn.

- Develop an accurate predictive model for churn classification.

- Recommend strategies for customer retention.

Key research questions include :

- Identifying significant predictors of churn

- The accuracy of predictions

- Investigate the relationship between service features and customer retention strategies.

By focusing on these areas, the project seeks to help Sunborn effectively mitigate customer churn and enhance overall business performance.

# The Data

The data obtained from Kaggle: [Customer Churn Dataset](kaggle/input/sunborn-customer-churn/customer_churn_large_dataset.csv')

Data consists of the below column features:

`CustomerID`- Unique identifier

`Name`- Client name 

`Age`- Client Age minimum being 18 years

`Gender`- Either Male or Female

`Location`- A state in USA

`Subscription_Length_Months`- How long the client has used the Yatch premises

`Monthly_Bill`- monthly rent charged

`Total_Usage_GB` - Total amount in Sterling pounds

`Churn` -Whether a client left or not 0(still present) 1(left)

### Data Preparation and Cleaning

We  imported all the necessary libraries, load the dataset using pandas library, preview the data (how many features and records, as well as statistical features), and conduct thorough data preprocessing (checking and removing any missing values and transforming data)

### Univariate Analysis 

<img width="582" alt="image" src="https://github.com/user-attachments/assets/a70a92ca-d520-4c85-a0eb-a0ecbb5e4f5e">



 <img width="401" alt="image" src="https://github.com/user-attachments/assets/28b98dae-5c62-4a99-96d9-02a4f185a426"> <img width="428" alt="image" src="https://github.com/user-attachments/assets/f66d163c-7eaa-4cca-a466-8e2b061aef85">




<img width="412" alt="image" src="https://github.com/user-attachments/assets/313abec4-defe-4eab-a6e0-a4f99fc0595a"> <img width="418" alt="image" src="https://github.com/user-attachments/assets/a970c83b-1d93-49f2-b0e2-746178b93f61">





 <img width="456" alt="image" src="https://github.com/user-attachments/assets/21b33d74-b1e8-464c-80ba-993d5cbb221e"> <img width="531" alt="image" src="https://github.com/user-attachments/assets/cf936071-bc02-4aaf-8303-c00061401b7f">

 #### Summary Statistics
- This is a balanced dataset(non-churn = 50,221 churn 49,779)- Sunborn looses almost 50% of their acquired  clients
  
- Most clients are female
  
- Average monthly bill is GBP 65

- Average total income is GBP 274
  
- Average client age clientele is 44 years

- Average client usage is 12 months max being 24 months

- Most of the companies Clientele comes from Houston State and Los Angeles.

  ### Multivariate Analysis

No significant correlation or linearity among predictor features against Target feature

To reconfirm we used

-  Pearsons Correlation Matrix
- Log transformation

Results indicated no linear relationship between variables

### Model Selection
Opted to use DecisionTreeClassifier Model as no linearity was observed

Methodology involved:

Splitting the Data into Trainset 80% and Test set 20%

Data normalization using StandardScaler

Creation of a Baseline Model

### Evaluating the Metrics

The test accuracy is only 50%, indicating that the model is not generalizing well to unseen data.

This discrepancy suggests overfitting, where the model has learned the training data too well, including noise and outliers, but fails to perform adequately on new data.
    
True Negatives (TN): 5,031 (correctly predicted class 0)

False Positives (FP): 5,048 (incorrectly predicted class 1)

False Negatives (FN): 4,896 (incorrectly predicted class 0)

True Positives (TP): 5,025 (correctly predicted class 1)

The test confusion matrix indicates a significant number of misclassifications.

The model is struggling to differentiate between the two classes, leading to a high number of false positives and false negatives.

The training confusion matrix shows that the model perfectly classified all training examples, with no misclassifications.

Test Classification Report:

- Precision for class 0: 0.51, for class 1: 0.50

- Recall for class 0: 0.50, for class 1: 0.51

- F1-score for both classes: 0.50

The test report shows that the model's performance is poor on unseen data, with both precision and recall around 50%. 

This indicates that the model is not effectively distinguishing between the two classes.

#### To Address Overfitting

1.Pruning the Decision Tree: 

Limit the depth of the tree by setting the max_depth parameter. 

2.Increase Minimum Samples for Splits and Leaves:

Adjusting parameters such as min_samples_split and min_samples_leaf to require a minimum number of samples for a split or leaf node, will help generalize better.

We used GridSearchCv.


3.Feature Engineering:
    
Review Features:  Consider removing irrelevant or noisy features thinking of  avoid scaling the data ..will make dataset and model simpler not complex

#### Model two- Hyperparameter Tuning with GridSearchCV

Training Performance

The model achieves a reasonably good accuracy of 0.62 on the training set, which is not too high as previous baseline model to indicate severe overfitting.

Test Performance

The model achieves a much lower accuracy of 0.50 on the test set, which is significantly lower than the training accuracy.

The confusion matrix for the test set shows a more imbalanced distribution compared to the training set, with higher false positives and false negatives.

The classification report for the test set shows a drop in precision, recall, and F1-score for both classes compared to the training set.

Avoiding scaling the data did not improve the test data

#### Final Model

**Accuracy Test:** 0.50

**Confusion Matrix:**

True Positives (TP): 5143

True Negatives (TN): 4788

False Positives (FP): 5291

False Negatives (FN): 4778

**Classification Report:**
              precision   recall  f1-score  support

           0       0.50      0.48      0.49     10079
           1       0.49      0.52      0.51      9921

    accuracy                           0.50     20000
   macro avg       0.50      0.50      0.50     20000
weighted avg       0.50      0.50      0.50     20000

#### Objectives Evaluation

**Identify Key Features Influencing Customer Churn:**

The current model’s performance does not provide clear insights into the key features influencing churn due to its low accuracy and balanced precision and recall.Although exhaustive hyperparameter tuning technique was applied through GridSearchCV.

Further feature importance analysis or using more sophisticated models like Random Forests or Gradient Boosting might help identify significant predictors.

**Develop an Accurate Predictive Model for Churn Classification:**

The model’s accuracy of 0.50 indicates it performs no better than random guessing.
    
This suggests the need for trying different algorithms.
                      
**Recommend Strategies for Customer Retention:**

With the current model’s performance, it is challenging to derive actionable insights for customer retention strategies.
    
Improving the model’s predictive power is crucial before making reliable recommendations.

#### Key Research Questions

**Identifying Significant Predictors of Churn:**

The model needs to be refined to accurately identify significant predictors. 
    
Complex Techniques like feature importance analysis and SHAP values can be useful once a better-performing model is developed.

**The Accuracy of Predictions:**

The current accuracy of 0.50 is insufficient for reliable predictions. 

Enhancing the model’s accuracy is essential to meet this objective.

**The Relationship Between Service Features and Customer Retention Strategies:**

The model’s current performance does not provide clear insights into the relationship between service features and retention strategies.

#### Recommendations for Improvement

Algorithm Selection: We should consider trying more complex models like Random Forests, Gradient Boosting, or Neural Networks.

Data Augmentation:
    
Collect More Data: Increase the dataset size to improve model training.

# Conclusion

There is need for additional data eg accommodation type, reservation type etc.The Stakeholder-Sunborn to provide additional data 

A much more complex algorithm is needed and not a DecisionTreeClassifier or LogisticRegression Model(as the features do not exhibit linearity)

By addressing these areas, you can work towards developing a more accurate predictive model for customer churn and derive actionable insights for retention strategies. 

A more accurate model is needed to explore these relationships effectively.















