Employee Retention Project

Programming Languages: Python

Python Packages: numpy, Pandas, Scipy, seaborn, Matplotlib, statsmodels, scikit-learn

Machine Learning Models: regression (linear, logistic), Naive Bayes, decision trees, random forest, AdaBoost, XGBoost

Dataset from Kaggle

Business scenario and problem:
The HR department at Salifort Motors wants to take some initiatives to improve employee satisfaction levels at the company. They collected data from employees, but now they don’t know what to do with it. Provide data-driven suggestions based on understanding of the data. They have the following question: what’s likely to make the employee leave the company?

Goals in this project are to analyze the data collected by the HR department and to build a model that predicts whether or not an employee will leave the company.

Predict employees likely to quit, it might be possible to identify factors that contribute to their leaving. Because it is time-consuming and expensive to find, interview, and hire new employees, increasing employee retention will be beneficial to the company.

EDA

Exploratory Data Analysis showed that there wasn't any missing values in the dataset. There were 3008 rows that contained duplicate values. That accounted for 20% of the data. These were handled by dropping the duplicate rows as they were not needed.

There were outliers in the tenure variable. Lower Limit: 1.5, Upper Limit: 5.5, 824 rows in tenure contained outliers.

<img width="815" alt="image" src="https://github.com/user-attachments/assets/1905e682-d841-42e8-a5ad-0b5777b23afa" />

Visualizations:

<img width="979" alt="image" src="https://github.com/user-attachments/assets/d60b0c52-fab6-4d2c-800d-14ab00e6dcd1" />

People who have more projects are working more hours. Everyone who had seven projects ended up leaving the company. The average hours for employees per month is over the norm. It seems that many employees are getting burnt out and overworked, causing the low satisfaction level and turnover. Investigate further.

<img width="964" alt="image" src="https://github.com/user-attachments/assets/0362e944-87b3-4e52-a0c1-2419e8ce2a78" />

This scatterplot shows that there is a group of employees that worked around 240-315 hours per month. That is over 75 hours per week for these employees for a year. Those employees most likely contributed to the low satisfaction level close to 0.
Even for a group of employees who left, as shown on the scatterplot, had a low satisfaction level (0.4). They were most likely feeling pressure to work more hours.
Employees that worked around 210-280 hours per month had satisfaction levels ranging around 0.7-0.9. Investigate further.

<img width="960" alt="image" src="https://github.com/user-attachments/assets/ab4095fd-ebaa-4ecf-8335-b412270dee0a" />

These plots show that there are two groups of employees: 
Dissatisfied Employees with short tenures
Satisfied Employees with medium tenures

Longest tenured employees did not leave. Their satisfaction level was about the same as the newer employees that stayed.
There are few longer-tenured employees, it may be reasonable to assume that they haven't left because they are higher paid.

<img width="1206" alt="image" src="https://github.com/user-attachments/assets/a1229270-50f2-4990-ad6c-f95e3a449e9b" />

These graphs show that employees who have been with the company for a long time are not predominantly those who earn higher salaries.

<img width="1214" alt="image" src="https://github.com/user-attachments/assets/b779f1e3-d861-4275-8b86-e3bfe40fda43" />

This scatterplot is showing two groups of employees whp left:
Overworked employees who performed well
Employees who worked slightly less than the average hours and didn't perform well

There seems to be a link between hours worked and evaluation scores. Interestingly, not many employees in the upper left quadrant work long hours and get bad evaluations. Just because you work long hours, doesn't mean you will get a good evaluation score.

<img width="1202" alt="image" src="https://github.com/user-attachments/assets/3b614a4e-2c82-4f8d-aa60-b33c4ddfe972" />

Out of the employees that were promoted in the last five years, few of them left. Very few employees that worked long hours were promoted. All of the employees who left were working the longest hours.
There didn't seem to be any patterns related by department.

<img width="1193" alt="image" src="https://github.com/user-attachments/assets/fd27e667-53e4-4be2-b3b8-28c34545c18a" />

The correlation heatmap does confirm that evaluation scores, monthly hours, and number of projects all have some positive correlation to each other and if an employee leaves is negatively correlated with the satisfaction level.

Insights

Leaving seems to be tied to long working hours, low satisfaction levels and too many projects. AKA Burn Out. Could be because of poor management. Employees that have been with the company 6 years or more tend not to leave.

Let's build some models

Logistic Regression:



<img width="735" alt="image" src="https://github.com/user-attachments/assets/b22ad47e-494c-41b3-9f33-66fddf8ceb17" />

<img width="554" alt="image" src="https://github.com/user-attachments/assets/559e1ff7-4523-4611-b3b4-83438d90a5bb" />

Tenure was removed due to the many outliers discovered. Logistic Regression is sensitive to outliers.

<img width="404" alt="image" src="https://github.com/user-attachments/assets/c27e6e04-b955-4ad7-b190-e37cfb2a803a" />

A perfect model would yield all true negatives and true positives, and no false negatives or false positives.

Checking class balance in data and creating a classification report with precision, recall, f1-score, and accuracy metrics.

<img width="734" alt="image" src="https://github.com/user-attachments/assets/c7bc7aa0-efb2-422e-bcf9-52bed04c0c81" />

The model needs to be better to be able to accurately predict employees that leave.

Tree-Based Model

<img width="866" alt="image" src="https://github.com/user-attachments/assets/6d04058a-aa0c-4a45-a6ea-a614a4e1ab63" />

AUC score is pretty good at around 0.97, which means this model's prediction power is pretty good.
Write a function to extract all scored from the GS.
Strong model performance is shown.

<img width="574" alt="image" src="https://github.com/user-attachments/assets/f77e19eb-dd77-4e4f-ac37-35bb6c4c3223" />

Random Forest Model and set up cross-validation

<img width="822" alt="image" src="https://github.com/user-attachments/assets/b86dbb19-1a6a-450d-9ee2-d73e59a8f315" />

<img width="766" alt="image" src="https://github.com/user-attachments/assets/f1489f88-aad3-476d-a676-23e34d8ba34a" />

Random Forest Model scores are better than the Decision-Tree Model overall. Recall only slightly lower (0.001). Overall the Random Forest Model is superior to the Decision-Tree Model.

Time to evaluate the final models.

Round 2 - Decision-Tree

<img width="770" alt="image" src="https://github.com/user-attachments/assets/ea6fc257-8be7-412e-8ee9-62fd8fa8b88c" />

Scores are still very good even though some scores did fall. This is to be expected being as there are fewer features.

Round 2 - Final Random Forest

<img width="752" alt="image" src="https://github.com/user-attachments/assets/f12c9762-7259-4e39-aa41-bdc6aa205478" />

Scores did fall on round two for the Random Forest Final Model as well.

Get Predictions on testing data:

<img width="712" alt="image" src="https://github.com/user-attachments/assets/9c4893d5-a47b-46b0-b1c6-aa509f3e2f83" />

Overall a stable model. 

Now Plot the confusion Matrix.
Does seems to predict more false positives than the other way around. Still solid.

<img width="598" alt="image" src="https://github.com/user-attachments/assets/65141503-286b-4a5d-8eef-794fadddb499" />

Plotting the tree:

<img width="1208" alt="image" src="https://github.com/user-attachments/assets/20268d23-8cd0-4a2b-81bd-4efe0d7cfc6e" />

Taking a look at feature importance

<img width="638" alt="image" src="https://github.com/user-attachments/assets/29daf5a1-464b-4e03-a4b9-ca1f916d63e7" />

<img width="649" alt="image" src="https://github.com/user-attachments/assets/2fd606b4-aee7-410f-aefe-7c4abb5b38ba" />

As suspected, from our best model Random Forest, we see that number of projects, last evaluation and being overworked seems to be the highest importance in contributing to employee churn. Leadership is going to have to take a good look into the managers and how they are leading their teams.























