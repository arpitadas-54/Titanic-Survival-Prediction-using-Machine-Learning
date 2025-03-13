# Titanic-Survival-Prediction-using-Machine-Learning
The sinking of the RMS Titanic in 1912 remains one of the most infamous maritime disasters in history, leading to significant loss of life. Over 1,500 passengers and crew perished that fateful night. Understanding the factors that contributed to survival can provide valuable insights into safety protocols and social dynamics during crises. In this project, we will leverage machine learning techniques to predict the survival chances of Titanic passengers based on various features, such as sex, age, and passenger class. Using the Random Forest classification algorithm, we aim to build a predictive model that will allow us to estimate the likelihood of survival for each individual aboard the Titanic.
## Objective of the Project: Predicting Titanic Passenger Survival
The primary objective of this project is to develop a machine learning model capable of predicting the survival status of Titanic passengers based on available data. The dataset includes information such as demographic attributes (age, sex), socioeconomic status (fare, class), and other relevant features. By analyzing these features, we seek to identify patterns that could influence survival rates and subsequently use these insights to make predictions on unseen data.

There will be three main steps in this experiment:

.Feature Engineering

.Imputation

.Training and Prediction

For this project, we will utilize the Titanic dataset. The dataset consists of the following files:

1.train.csv: Contains information about the passengers and their survival status, which will be used for training our model. Serves as our primary data source for training and validation, providing both features and target labels.

2.test.csv: Includes details of passengers without survival labels, which we will use for making predictions. Allows us to assess the model’s performance on unseen data, simulating a real-world scenario where predictions must be made for new passengers.

3.gender_submission.csv: A sample submission file that demonstrates the format required for submitting predictions.

## Step-by-Step Implementation: Predicting Titanic Survival
1. Importing Libraries and Initial setup
Let’s read the training and test data using the pandas data frame.
To know the information about each column like the data type, etc we use the df.info() function.
Let’s see if there are any NULL values present in the dataset. This can be checked using the isnull() function. It yields the following output.
2.  Data Visualization: Understanding Survival Trends and Passenger Demographics
Now let us visualize the data using some pie charts and histograms to get a proper understanding of the data.
Let us first visualize the number of survivors and death counts
Analyzing the Impact of Sex on Survival Rates: Reflects the focus on exploring how the gender of passengers influenced their chances of survival.
3. Feature Engineering: Optimizing Data for Model Training
This section focuses on refining the dataset by removing irrelevant features and transforming categorical data into numerical formats. Key tasks include:

Dropping Redundant Features: Removing columns like Cabin that offer limited predictive value.
Creating New Features: Introducing a new column to indicate whether cabin information was assigned or not.
Data Transformation: Converting textual data into numerical categories for seamless model training.
We can also drop the Ticket feature since it’s unlikely to yield any useful information.

There are missing values in the Embarked feature. For that, we will replace the NULL values with ‘S’ as the number of Embarks for ‘S’ are higher than the other two.

We will now sort the age into groups. We will combine the age groups of the people and categorize them into the same groups. BY doing so we will be having fewer categories and will have a better prediction since it will be a categorical dataset.

In the ‘title’ column for both the test and train set, we will categorize them into an equal number of classes. Then we will assign numerical values to the title for convenience of model training.

Now using the title information we can fill in the missing age values.

Now assign a numerical value to each age category. Once we have mapped the age into different categories we do not need the age feature. Hence drop it

Drop the name feature since it contains no more useful information.

Assign numerical values to sex and embarks categories.

Fill in the missing Fare value in the test set based on the mean fare for that P-class

Now we are done with the feature engineering.

4. Model Training: Building the Predictive Model
In this phase, we employ Random Forest as our algorithm to train the model for predicting survival. Key steps include:

.Data Splitting: Dividing the dataset into 80% training and 20% testing subsets using train_test_split() from the sklearn library.

.Model Selection: Leveraging the Random Forest algorithm, known for its robustness and ability to handle diverse data.

.Performance Evaluation: Assessing the trained model’s accuracy on the test data to ensure it generalizes well.

Now import the random forest function from the ensemble module of sklearn and for the training set.
   
## Prediction: Generating Survival Predictions on Test Data
In this final phase, we use the trained Random Forest model to make predictions on the test dataset. The key steps are:

Running Predictions: Input the test dataset into the trained model to predict survival outcomes.
Preparing Results: Store the PassengerId from the test data and the corresponding Survival predictions (0 or 1).
Saving the Output: Export the predictions to a CSV file for submission, with two columns:
PassengerId: ID of each passenger from the test dataset.
Survival: Predicted survival status (0 = Did not survive, 1 = Survived).

## Conclusion
In this project, we successfully built a Random Forest classifier to predict the survival chances of Titanic passengers. Through data preprocessing, feature engineering, imputation, and model training, we were able to create a robust model with 83.8% accuracy on the training set.


