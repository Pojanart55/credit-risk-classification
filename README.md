## Credit Risk Classification

This analysis aimed to develop a predictive model for assessing credit risk in loan applications. By examining historical data on past loans, the objective was to create a tool that could accurately classify new loan applications as either representing a healthy (low-risk) investment or posing a high risk of default. The ability to effectively distinguish between these two categories is vital for the lending company to optimize its lending strategy and mitigate potential financial losses associated with loan defaults.

The dataset analyzed contained a variety of financial indicators associated with each loan. These included details such as the loan amount, the interest rate assigned, the borrower's income, their debt-to-income ratio, the number of credit accounts held, any record of derogatory financial marks, their total outstanding debt, and, crucially, the final status of the loan (the target variable). The prediction target was the `loan_status`, where a value of 0 signified a loan that was repaid successfully (healthy), and a value of 1 indicated a loan that faced significant issues or resulted in default (high-risk).

To understand the nature of the prediction task, an examination of the distribution of healthy and high-risk loans within the dataset was conducted. This initial exploration helped to grasp the class balance and potential challenges in building a robust classification model.

The analytical process followed a standard machine learning workflow:

1.  **Data Acquisition and Preparation:** The lending data was loaded from a CSV file into a structured format using Pandas, and the features were separated from the loan status labels.
2.  **Data Partitioning:** The dataset was divided into two subsets: a training set used to teach the model the relationships between the features and the loan status, and a testing set used to evaluate how well the trained model generalizes to new, unseen data. The `train_test_split` function was employed, ensuring a random split and considering the preservation of the original class proportions.
3.  **Model Development:** A **Logistic Regression** model was implemented. This algorithm is well-suited for binary classification problems such as this, as it can estimate the probability of a loan belonging to either the healthy or high-risk category based on the input features.
4.  **Model Assessment:** After training the logistic regression model on the training data, the testing data was used to assess its predictive performance. A **confusion matrix** was generated to visualize the types of errors the model made, and a **classification report** was produced to quantify its precision, recall, F1-score, and overall accuracy.

The primary analytical tool was the **Logistic Regression** algorithm from the scikit-learn library. This method allowed for the modeling of the probability of loan default as a function of the various financial features provided in the dataset.

### Results

The performance of the Logistic Regression model is summarized below:

* **Logistic Regression Model:**
    * **Accuracy:** 0.99
    * **Precision (Healthy Loans - Class 0):** 1.00
    * **Precision (High-Risk Loans - Class 1):** 0.89
    * **Recall (Healthy Loans - Class 0):** 1.00
    * **Recall (High-Risk Loans - Class 1):** 0.93

### Summary

This **Credit Risk Analysis Report** details the performance of a Logistic Regression model developed for binary classification of loan applications into healthy (low-risk) and high-risk categories. The model achieved an overall accuracy of 99% on the test set, indicating a high level of correct classifications.

Specifically, the model demonstrated exceptional performance in identifying healthy loans (class 0), achieving a perfect precision of 1.00 and a perfect recall of 1.00. This signifies that all loans predicted as healthy were indeed healthy, and the model successfully identified all actual healthy loans in the test data.

For high-risk loans (class 1), the model attained a precision of 0.89 and a recall of 0.93. This indicates that 89% of the loans predicted as high-risk were truly high-risk, and the model successfully identified 93% of all actual high-risk loans in the test data.

Considering the critical nature of accurately identifying high-risk loans to mitigate financial losses, the model's high recall (0.93) for this class is a significant strength. While the precision of 0.89 suggests that approximately 11% of loans flagged as high-risk were actually healthy (false positives), the cost of failing to identify a truly high-risk loan (false negative) typically outweighs the cost of a false positive in this context.

**Recommendation:** The Logistic Regression model is recommended for implementation as an initial credit risk assessment tool. Its high accuracy and robust ability to identify both healthy and high-risk loans provide substantial value for informed lending decisions. While further refinement to improve the precision for high-risk loans could be explored, the current performance offers a strong balance between accurately identifying risky borrowers and minimizing missed opportunities with healthy applicants.

**Acknowledgement**

    * Logistic Regression: https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LogisticRegression.html
    * Classification Report: https://scikit-learn.org/stable/modules/generated/sklearn.metrics.classification_report.html
    * Google: for researching Linear Regression information and code debugging