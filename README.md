# Sunborn(Luxury Brand) - Customer Churn Prediction

<img width="700" alt="image" src="https://github.com/user-attachments/assets/9db02ea7-0d22-4bd0-a9ef-79bcea661352">

## About Sunborn

Sunborn is a family business group with a legacy spanning five decades, primarily focused on yacht hospitality. 

They engage in innovative maritime construction and development, manage healthcare assets, and own real estate across diverse sectors.

As competition intensifies and market saturation increases, customer retention has become essential, as acquiring new customers is significantly more costly. 

Research indicates that retaining existing customers can lead to substantial profit increases, highlighting the importance of investing in effective customer retention strategies.

## The Classification Problem

<img width="400" alt="image" src="https://github.com/user-attachments/assets/db79f6b0-9c79-42f7-b91b-ba93512801ce">

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

Mean Age: 44.03
Standard Deviation: 15.28
Median Age: 44.00
Variance: 233.49

<img width="531" alt="image" src="https://github.com/user-attachments/assets/cf936071-bc02-4aaf-8303-c00061401b7f">


Mean: 12.49
Median: 12.00
Max: 24.00
Min_usage: 1.00

<img width="412" alt="image" src="https://github.com/user-attachments/assets/313abec4-defe-4eab-a6e0-a4f99fc0595a">


Mean: 274.39
Median: 274.00
Max: 500.00
Variance: 17020.61
Std: 130.46

<img width="418" alt="image" src="https://github.com/user-attachments/assets/a970c83b-1d93-49f2-b0e2-746178b93f61">



Mean: 65.05
Median: 65.01
Max: 100.00
Variance: 409.28
Min: 30.00
Min_usage: 50.00


<img width="428" alt="image" src="https://github.com/user-attachments/assets/f66d163c-7eaa-4cca-a466-8e2b061aef85">


<img width="456" alt="image" src="https://github.com/user-attachments/assets/21b33d74-b1e8-464c-80ba-993d5cbb221e">


<img width="401" alt="image" src="https://github.com/user-attachments/assets/28b98dae-5c62-4a99-96d9-02a4f185a426">









