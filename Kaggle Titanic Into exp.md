# Kaggle Titanic Tutorial Experience
## Part 1: Getting Started
It covers details about :
1. The challenges present in kaggle 
2.  How to enter the challenge
3.  About  the data

### About the data
One of the most import steps in the data science life cycle is to understand the type of data you are dealing with.
Even though  most of the data present in kaggle is clean, understanding the featuresi important step.

#### Data provided by kaggle
1. train.csv - Contains features as column header and values as content in the tabular structure.
 
2. Test.csv - This data is provided to make the prediction which will be used predict the column /feauture which is present in Train ( but missing from the test set) 
 3. submission file(gender_submission.csv) - The submission file is provided to understand the format in which the kaggle judge system expects for evaluation.

## Part 2 : Coding Environment
It covers the details about :
1. Interaction with kaggle notebook
2.  Basic library import like numpy, pandas and os
3.  Interaction with data


### Basic Library and their application area

* numpy - Linear algebra
* pandas - Data Processing , fille I/0
* OS - Interaction with OS via python commands 

Following is the code for knowing the file directory contents
```
import os
for dirname, _, filenames in os.walk('/kaggle/input'):
    for filename in filenames:
        print(os.path.join(dirname, filename))
```
** Output **
/kaggle/input/titanic/train.csv
/kaggle/input/titanic/test.csv
/kaggle/input/titanic/gender_submission.csv

### Interaction with data

```
train_data = pd.read_csv("/kaggle/input/titanic/train.csv")
train_data.head()
``` 
  Output will contain the first 5 rows with headers which is useful to understand the way test and train data is present

## Part 3: Submission

It covers details about :
1.  Exploring the pattern
2.  Building Machine learning model 

### Exploring the pattern for prediction

You can make assumptions about the data and predict with basic pattern.
In this particular case considering a pattern like all the females will survive a can be tested with train data.
Following code was written to test the hypothesis:
```
women = train_data.loc[train_data.Sex == 'female']["Survived"]
rate_women = sum(women)/len(women)

print("% of women who survived:", rate_women)
```
** Output**
% of women who survived: 0.7420382165605095

### Building Machine learning Model

It has demonstrrated particular case of classification using the random forest classifier.
```
from sklearn.ensemble import RandomForestClassifier

y = train_data["Survived"]

features = ["Pclass", "Sex", "SibSp", "Parch"]
X = pd.get_dummies(train_data[features])
X_test = pd.get_dummies(test_data[features])

model = RandomForestClassifier(n_estimators=100, max_depth=5, random_state=1)
model.fit(X, y)
predictions = model.predict(X_test)

output = pd.DataFrame({'PassengerId': test_data.PassengerId, 'Survived': predictions})
output.to_csv('submission.csv', index=False)
print("Your submission was successfully saved!")
```

After the export of csv file save the version. For submission
