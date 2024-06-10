# Concise Report on Building a Machine Learning Model for Telecom Customer Churn Prediction

## Tasks Performed:


### Data Collection and preprocessing:
- Importing Libraries and Loading Data
  - The required libraries were imported, and the dataset was loaded from the Kaggle source into a pandas Data Frame.
- Data Understanding and Null Value Check
  - Upon examining the dataset, it was found that there were no null values, allowing us to proceed to the next step.
- Binary Encoding
  - Identified features with only two possible values and replaced them with binary values (1 for "Yes" and 0 for "No").
- Data Type Conversion
  - The Total charges feature was converted to a float to ensure accurate numerical operations.
- Outlier Detection and Distribution Check
  - All numerical variables were checked for outliers. As there were no outliers and the data was uniformly distributed, proceeded to Exploratory Data Analysis

### Exploratory Data Analysis (EDA):
- Univariate Analysis
  - Distribution of Numerical Features
    - Analyzed the distribution of numerical features across the dataset. Key observations include:
      - Many customers had low tenure, low monthly charges, and low total charges, as revealed by histograms.
  - Distribution of Categorical Features
    - Explored the distribution of categorical features within the dataset, leading to several insights:
      - 48.9% of churned customers are male, and 50.2% are female.
      - 25.5% of churned customers are senior citizens.
      - 35.8% of churned customers have partners.
      - 17.4% of churned customers are dependents.
      - 90.9% of churned customers have phone service.
      - 69.4% of churned customers opted for fiber optic internet.
      - 78.2% of churned customers did not opt for online security.
      - 66% of churned customers did not opt for online backup.
      - 64.8% of churned customers did not opt for device protection.
      - 50.4% of churned customers do not have streaming TV.
      - 50.2% of churned customers do not stream movies.
      - 88.6% of churned customers have a month-to-month contract.
      - 57.3% of churned customers pay via electronic check.
      - 74.9% of churned customers opt for paperless billing.
    - The above were identified by pie chart plotted among all categorical Features.
- Bivariate Analysis
  - Plotted Boxplot between monthly Charges and other categorical variables The box plots were used to visualize the relationship between monthly charges and various categorical variables. Some key findings from this analysis include:
    - Senior Citizens: Senior citizens have a monthly spending range of approximately 70-95, whereas other customers have a spending range of 25-50.
    - Phone Service: Customers who do not use phone service have a monthly spending range of around 35-50, while those who use phone service spend between 40-85 monthly.
    - Streaming Services: Customers who opt for streaming TV and streaming movies tend to have higher monthly spending compared to those who do not use these services.
    - Paperless Billing: Customers who opt for paperless billing generally have higher monthly spending compared with those who do not.
- Multivariate Analysis
  - Correlation Matrix
    - A correlation matrix was plotted to understand the relationships between numerical features. Key outcomes include:
      - Total Charges and Tenure: These features are positively correlated with a correlation coefficient of 0.83, indicating that customers with longer tenures tend to have higher total charges.
  - Pair Plot Analysis
    - A pair plot was created to examine the relationships among numerical features and identify customer churn patterns. Key insights include:
      - Low Tenure and High Monthly Charges: Customers with low tenure and high monthly charges are more likely to churn.
      - Low Tenure and Low Total Charges: Customers with low tenure and low total charges are also more prone to churn.
      - Low Total Charges and High Monthly Charges: Customers with low total charges but high monthly charges tend to churn as well.
      - These patterns suggest that customers who are new and either have high monthly costs or have low total charges are at a higher risk of churning.

### Feature Engineering:
- Identified all the categorical variables and creating their dummy Features which are helpful in Churn Prediction

### Model Building and Evaluation:
- Model Selection
  - Based on a review of various research papers, logistic regression and decision tree algorithms were chosen due to their relative performance advantages for the given dataset.
- Logistic Regression Model with Hyperparameter Tuning and GridSearch
  - Data Splitting: The dataset was split into training and test sets.
  - Data Scaling: Features were scaled to standardize the data.
  - Feature Selection: Highly correlated features were identified and removed using a correlation matrix to avoid multicollinearity.
  - Model Training: The logistic regression model was trained using hyperparameter tuning and GridSearch to optimize performance.
  - Confusion Matrix: A confusion matrix was created for the trained model to evaluate its performance.
  - Metrics Calculation: Key metrics were calculated, including sensitivity, specificity, false positive rate, positive predictive value, and negative predictive value.
  - ROC Curve: The Receiver Operating Characteristic (ROC) curve was drawn to visualize the model's performance.
- Decision Tree Model
  - Data Splitting: The dataset was split into training and test sets.
  - Data Scaling: Features were scaled to standardize the data.
  - Model Training: The decision tree model was trained.
  - Model Refinement: The decision tree model was retrained iteratively, adjusting parameters to ensure the model was appropriately fit without overfitting.
  - Confusion Matrix: A confusion matrix was created for the trained model to evaluate its performance.
  - Metrics Calculation: Key metrics were calculated, including sensitivity, specificity, false positive rate, positive predictive value, and negative predictive value.


- **Results:**
  | Metric                                      | Logistic Regression | Decision Tree Model |
  |---------------------------------------------|---------------------|---------------------|
  | Train Accuracy                              | 80.86%              | 77.69%              |
  | Test Accuracy                               | 79.85%              | 76.25%              |
  | Sensitivity                                 | 57.04%              | 54.46%              |
  | Specificity                                 | 88.54%              | 84.55%              |

### Challenges Faced
- Overfitting in Decision Tree: The model performed well on training data but poorly on test data, indicating overfitting. Iterative tuning did not resolve this issue.
- Logistic Regression Accuracy: Hyperparameter tuning had no significant impact on accuracy, which plateaued at 80.9%, below industry standards.
- Low Overall Accuracy: The highest achieved accuracy of 80.9% is insufficient compared to industry benchmarks.
### Conclusion:
- Sensitivity and specificity are critical metrics for evaluating model performance, particularly when dealing with imbalanced datasets. These metrics help measure the goodness of a model by assessing its ability to correctly identify positive and negative cases.
- The suitability of a model does not solely depend on high specificity or sensitivity. Instead, it should align with business requirements, which dictate the trade-off between these metrics. Depending on the specific business context, model parameters can be adjusted and the model retrained to meet desired performance standards.
- In this project, both logistic regression and decision tree models were trained and evaluated. The outcomes
