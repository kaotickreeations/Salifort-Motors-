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























