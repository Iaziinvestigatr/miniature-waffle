# miniature-waffle
# prompt: give me readme file text for this project


## Usage

1.  **Ensure you have the `Copy of sonar data.csv` file** in the same directory as the script or update the file path in the script.
2.  **Run the Python script.**

The script will perform the following steps:

1.  Load the dataset.
2.  Perform basic data exploration (shape, descriptive statistics, value counts, group by).
3.  Separate the features (X) and the target variable (Y).
4.  Split the data into training and testing sets.
5.  Train a Logistic Regression model on the training data.
6.  Evaluate the model's accuracy on both the training and testing data.
7.  Demonstrate a predictive system using a sample input data point.

## Code Explanation

- **Data Loading and Processing:**
    - The data is loaded into a pandas DataFrame.
    - `sonar_data.head()`, `sonar_data.shape`, `sonar_data.describe()`, `sonar_data[60].value_counts()`, and `sonar_data.groupby(60).mean()` are used for initial data understanding.
    - The features (`X`) are created by dropping the target column (column 60).
    - The target variable (`Y`) is the column 60.

- **Training and Test Data:**
    - `train_test_split` is used to split the data into training (90%) and testing (10%) sets.
    - `stratify=Y` ensures that the proportion of 'R' and 'M' classes is maintained in both the training and testing sets.
    - `random_state=2` ensures reproducibility of the split.

- **Model Training:**
    - A `LogisticRegression` model is initialized.
    - The model is trained using the `fit()` method on the training data (`X_train`, `Y_train`).

- **Model Evaluation:**
    - The `predict()` method is used to get predictions on both the training and testing data.
    - `accuracy_score` is used to calculate the accuracy of the model on both sets.

- **Making a Predictive System:**
    - A sample `input_data` tuple is defined.
    - The input data is converted into a numpy array and then reshaped to have a single instance (`reshape(1,-1)`).
    - The trained model's `predict()` method is used to predict the class of the input data.
    - The result is printed, indicating whether the object is a rock or a mine.

## Results

The script will output the accuracy of the model on the training and test data, and the prediction for the sample input data.

