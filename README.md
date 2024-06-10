# Classification-Challenge

<div align='center'>
    <img src='https://images.pexels.com/photos/193003/pexels-photo-193003.jpeg' height='350', title= 'A phone with a lot of unread email, which may or may not be spam (image courtesy of Pexels)' alt='A zoomed-in view of the bottom of a smart phone, with icons for Google, email, and phone apps visible and a notification of "20" above the email app' />

*Spam Detector*[^1]

**Module 13 Challenge**

## READ ME
</div>

## Table of Contents

* [Overview](#Overview)
* [Execution](#Execution)

---

## Overview

### *The Assignment*

The Module 13 Challenge put us in the role of a worker at an ISP, tasked with improving the email filtering system. Using our understanding of the **Logistic Regression** and **Random Forest Classifier** models, we were to fit a given dataset and evalutate which model was more accurate at detecting spam.

We were provided the `spam_detector.ipynb` Jupyter Notebook with starter code to accomplish our assignment.

### *Written in*

Jupyter Notebook using Python v3.10.13, Pandas, and scikit-learn

### *Accessing the notebook*

To access the spam detector notebook, simply download the `.ipynb` file `spam_detector.ipynb` into a local directory, then load the `spam_detector.ipynb` file into Jupyter Notebook through your terminal.

---

## Execution

### *How to use*

Simply `Run All Cells` to execute the code in every cell of the notebook in sequence. Alternatively, each cell may be `Run` on its own, though it is still recommended to run them in order.

### *Breaking down the code*

Below is a more in-depth explanation of the various cells coded within the `spam_detector.ipynb` notebook.

| Cell (in sequence) | Notes[^2] |
| ---: | :--- |
| 1[^3] | Importing initial libraries and dependencies |
| 2[^3] | Importing data to the DataFrame (DF) `data` <br> <br> Displaying a sample of the data |
| **Predictions**[^4] | Predicting which model (Logistic Regression or Random Forest Classifier) will perform better <br> *Spoiler: My predictions based on experience from previous activities from the class, and they were correct in the end* |
| 3 | Declaring `y` as the `spam` column of `data` <br> <br> Declaring `X` as a copy of `data` with the `spam` column dropped |
| 4 | Checking the balance of values in `y` with `value_counts()` |
| 5[^5] | Splitting the dataset into `X_train`, `X_test`, `y_train`, and `y_test` with `train_test_split()` <br> *Note:* `random_state=13` *was used to maintain consistent testing during development* <br> <br> Displaying a sample of the data from `X_train` |
| 6[^6] | Importing `StandardScalar` from `sklearn.preprocessing` <br> <br> Declaring `scalar` as an instance of `StandardScalar()` |
| 7 | Declaring `X_scalar` to fit `scalar` to the training data `X_train` |
| 8 | Declaring `X_train_scaled` as a `scalar.transform()` of the training data `X_train` <br> <br> Declaring `X_test_scaled` as a `scalar.transform()` of the testing data `X_test` |
| 9[^6] | Importing `LogisticRegression` from `sklearn.linear_model` <br> <br> Declaring `lr_model` as an instance of `LogisticRegression()` with a `random_state` of `1`, and fitting to the training data `X_train_scaled` and `y_train` |
| 10 | Declaring `lr_predictions` as a `lr_model.predict()` on the testing data `X_test_scaled` <br> <br> Displaying a sample of the predicted data |
| 11[^7] | Calculating the `accuracy_score()` of the Logistic Regression model by evaluating `y_test` against `lr_predictions` |
| 12[^6] | Importing `RandomForestClassifier` from `sklearn.ensemble` <br> <br> Declaring `rf_model` as an instance of `RandomForestClassifier()` with a `random_state` of `1`, and fitting to the training data `X_train_scaled` and `y_train` |
| 13 | Declaring `rf_predictions` as a `rf_model.predict()` on the testing data `X_test_scaled` <br> <br> Displaying a sample of the predicted data |
| 14[^7] | Calculating the `accuracy_score()` of the Random Forest Classifier model by evaluating `y_test` against `rf_predictions` |
| **Evaluation**[^4] | Reviewing the findings and confirming the earlier predictions |
| ***NOTE:*** | *The following markdown and code cells were not required by the assignment, and were written to further support the earlier predictions* |
| **Additional Confirmation** | Declaring the purpose of the aforementioned additional cells |
| 15 | Importing `precision_score` from `sklearn.metrics` |
| 16 | Declaring `lr_precision` as the `precision_score()` of the Logistic Regression model by evaluating `y_test` against `lr_predictions` <br> <br> Declaring `rf_precision` as the `precision_score()` of the Random Forest Classifier model by evaluating `y_test` against `rf_predictions` |
| 17 | Displaying `lr_precision` for analysis <br> <br> Displaying `rf_precision` for analysis |
| **Final Confirmation** | Reviewing the additional findings through the used of `precision_score` and further confirming the earlier predictions |

[^1]: Image courtesy of the free source image site, <a href='https://www.pexels.com/photo/black-and-gray-digital-device-193003/' title='Link to Pexels listing for image'>Pexels</a>

[^2]: Markdown cells for instructions not annotated

[^3]: Denotes cells with completed code provided, no student coding contained

[^4]: Markdown cells for student responses

[^5]: Used of `random_state=13` chosen to maintain consistent testing during development, as no instruction to use any `random_state` argument was provided

[^6]: Denotes cells with `import`s provided, all remaining coding by student

[^7]: Provided variable `testing_predictions` renamed to `lr_predictions` or `rf_predictions` to maintain distinct prediction variables for both models