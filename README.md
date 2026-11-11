
# [KNIME] Data Analytics & Machine Learning Exercises - Business Intelligence 

## I. Overview

This project showcases practical exercises completed as part of the Business Intelligence course, using **KNIME Analytics Platform**. It covers **data access**, preprocessing, transformation, visualization, data integration, statistical analysis, machine learning, and report generation.

### 1. Objectives

- Gain hands-on experience with **KNIME workflows** and nodes.
- Practice **data cleaning**, transformation, and integration.
- **Explore** and **visualize** datasets to identify patterns.
- Apply **regression** and **classification** models.
- Evaluate **model performance** and generate reports.

### 2. Who Is This Project For?

- **Business Intelligence Students:** To review practical KNIME applications and workflows.
- **Aspiring Data Analysts:** To explore data preparation, analysis, and visualization.
- **Beginners in Machine Learning:** To understand basic regression and classification workflows.

## II. Key Skills & Tools

- **Tool:** KNIME Analytics Platform
- **Data Processing:** Filtering, cleaning, transformation, aggregation
- **Data Integration:** Joins and concatenation
- **Visualization:** Data Explorer, Scatter Plot, Table View
- **Machine Learning:** Linear Regression, Decision Tree, model evaluation
- **Reporting:** BIRT Report

## III. Datasets

The exercises use the following datasets:

| Dataset | Description |
|---|---|
| `adult.csv` | Adult demographic and employment data |
| `adult_education.table` | Education-related data |
| `adult_income.xlsx` | Income-related data |
| `adult_joined.table` | Integrated dataset used for analysis and modeling |
| `adult_binned.csv` | Dataset containing age groups |
| `adult_w_commute.table` | Data including working hours and commute time |
| `WebActivity.sqlite` | SQLite database containing web activity records |
| `adult_scotland.table` | Records for Scotland |

## IV. Main Processes & Exercises

### 1. Read Data from File

Read the following files in the data folder using the appropriate reader nodes:
- adult.csv
- adult_education.table
- adult_income.xlsx

<img width="345" height="124" alt="Screenshot 2026-11-11 at 01 07 50" src="https://github.com/user-attachments/assets/e83b0638-57fc-4215-a2e0-e8016a179b24" />

### 2. Accessing Databases

Read the web_activity table on the WebActivity.sqlite database available in the data folder

<img width="372" height="115" alt="Screenshot 2026-11-11 at 01 18 30" src="https://github.com/user-attachments/assets/b1666a79-13f3-4495-b8f4-55833e4bce8e" />

### 3. Row and Column Filtering
#### 3.1. Row Filtering
1) Read the adult.csv file by executing the CSV Reader node
2) Filter out rows where the marital status is missing
3) Extract rows where 
- the marital status is divorced
- the marital status is never married and age is between 20 and 40 (both included)
- the workclass starts with "S"

-> How many adults are
- divorced? - 4441
- never married and between 20 and 40 years old? - 7908
- with work class State-gov - , Self-emp-not-inc, or Self-emp-inc?

<img width="259" height="353" alt="Screenshot 2026-11-11 at 01 25 46" src="https://github.com/user-attachments/assets/3994c6c3-4609-4af4-b25a-0ab827b76ba3" />

#### 3.2. Column Filtering
1) Read the adult_education.table file by executing the Table Reader node
2) Exclude the "education-num" column
- manually
- by including only string type columns

<img width="328" height="210" alt="Screenshot 2026-11-11 at 01 27 03" src="https://github.com/user-attachments/assets/47aaa1a7-e441-4c96-82e2-8cb8a6ce1710" />

### 4. Exercise: Data Transformation
1) Read the adult.csv file by executing the CSV Reader node
2) Create a new column "work-status" with the value "full-time" if the weekly working hours are >=40 and "part-time" otherwise
3) Replace the hyphen in "United-States" by a space character in the "native-country" column
4) Create a new column "year-of-birth" by substracting the age number from 1994, which is the year when the data were collected 
5) OPTIONAL: Replicate the tasks 3 & 4 with the Column Expressions node
6) Take a look at the first row in the data table (ID 177) after completing the data transformation operations. What is the work status, native country, and year of birth of this person?

<img width="514" height="285" alt="Screenshot 2026-11-11 at 01 41 11" src="https://github.com/user-attachments/assets/5dc64de3-7f0e-47cd-99a8-9cfb50cb11c1" />


### 5. Data Visualization
#### 5.1. Data Explorer
1) Read the adult.csv file by executing the CSV Reader node
2) Inspect the properties of the data with the Data Explorer node
- How many different native countries are represented in the data?
3) In the interactive view, exclude the nominal columns that contain missing values
- Which of the nominal columns contain missing values? How many missing values each?

<img width="201" height="102" alt="Screenshot 2026-11-11 at 01 43 36" src="https://github.com/user-attachments/assets/21f3ec9b-20d6-4cbf-97cc-2faa09de3517" />

#### 5.2. Scatter Plot and Composite View
1) Read the adult_w_commute.table file by executing the Table Reader node
2) Assign colors to the rows based on the marital status
3) Draw a scatter plot of hours per week vs. commute time
- Do you observe any particular relationship between these two columns?
- What can you say about the marital status of people who work <25 hours per week and commute the most?
4) Create an interactive table that displays the data. Use the Table View node.
5) Encapsulate the Scatter Plot and Table View nodes into a component. Open the component's interactive view.
6) Switch to the mouse mode "Select" in the scatter plot view and select the data points with <25 working hours and >120 min commuting time
7) Show only selected rows in the interactive table
- What is the native country of the selected data points?

<img width="353" height="222" alt="Screenshot 2026-11-11 at 01 45 04" src="https://github.com/user-attachments/assets/80487d08-67ba-4488-a337-95c29a0aa2e6" />

### 6. Aggregations
#### 6.1. GroupBy
1) Read the adult.csv file by executing the CSV Reader node
2) Calculate the total number of rows and average age by gender
3) Calculate the modes of all string columns separately for each native country
4) Calculate 
- the number of missing values in the occupation column (tick missing value counts, not count)
- the number of non-missing rows in the occupation column (no tick in missing value)
- the number of rows in the occupation column (=missing value + non-missing values)
- the number of rows in the marital-status column (count + tick missing value)

<img width="387" height="363" alt="Screenshot 2026-11-11 at 01 47 20" src="https://github.com/user-attachments/assets/097fba64-e95b-48c0-854e-7e3cb0bd2ea5" />

#### 6.2. Pivoting

1) Read the adult_binned.csv file by executing the CSV Reader node
2) Calculate the number of people in groups according to their work class and age bin
- What is the most common combination of age bin and work class?
- How many people belong to this group?
3) Calculate the mode of education level in groups according to their work class and age bin
- What is the most widespread education level in the private workclass independently of the age bin?

<img width="330" height="243" alt="Screenshot 2026-11-11 at 01 47 55" src="https://github.com/user-attachments/assets/6f9fad43-fd7a-4a1f-9037-9cca8e79e275" />


### 7. Join and Concatenate
#### 7.1. Joiner
1) Read the adult.csv, adult_education.table, and adult_income.xlsx files by executing the reader nodes
2) Join the adult.csv data with the adult_education.table data. Use the ID column as the joining column. Use inner join. 
3) Join the adult_income.xlsx data with the joined table. Apply the same settings. 
4) What is the number of rows and columns in the first joined table? And in the second? Were any rows discarded in the joining operations?

<img width="560" height="378" alt="Screenshot 2026-11-11 at 01 48 53" src="https://github.com/user-attachments/assets/7040aed1-aac2-4448-b75f-fef01713cf82" />

#### 7.2. Concatenate

1) Execute the Table Reader nodes below. The adult_joined.table file contains the records for all countries but Scotland. The records for Scotland are stored in a separate adult_scotland.table file.
2) Concatenate the two tables into one
3) Which column is missing in one of the tables? If you want to include this column in your concatenated table, do you select union or intersection of columns?

<img width="345" height="256" alt="Screenshot 2026-11-11 at 01 49 49" src="https://github.com/user-attachments/assets/acce842d-9dde-43e4-97af-65788f34dc11" />


### 8. Linear Regression and Numeric Scoring Metrics
1) Read the adult_joined.table file by executing the Table Reader and Missing Value nodes
2) Partition the data into a training set (75 %) and test set (25 %). Draw randomly.
3) Train a linear regression model on the training set to predict the weekly working hours. Use all other columns but the "ID" column for the prediction.
4) Apply the model to the test set
5) Evaluate the performance of the linear regression model with the Numeric Scorer node. Which proportion of the variance of the weekly working hours does the model explain? How many hours is the mean absolute error of the model?

<img width="723" height="197" alt="Screenshot 2026-11-11 at 01 51 42" src="https://github.com/user-attachments/assets/ae10ed0b-d05f-4fd0-a5f4-259051cb3223" />

### 9. Exercise: Decision Tree and Classification Model Evaluation
1) Read the adult_joined.table file by executing the Table Reader node
2) Partition the dataset into a training set (75%) and a test set (25%). Apply stratified sampling to the income column.
3) Train a Decision Tree model on the training set to predict whether or not a person earns more than 50K per year
4) Apply the model to the test set

5) Evaluate the accuracy of the model with scoring metrics
- What is the overall accuracy of the model?
6) Open the configuration dialog of the Scorer (JavaScript) node and exclude those statistics from the class prediction statistics table that are also present in the confusion matrix. Display the number of rows in the confusion matrix. 
- What is the number of rows in the test dataset?

7) Evaluate the performance of the model with an ROC curve
- What is the Area under the Curve statistics for the decision tree model?
8) OPTIONAL: Try out other parameter settings to reach a better performance. For example, change the quality measure, pruning method, or minimum number of records.

<img width="533" height="250" alt="Screenshot 2026-11-11 at 01 52 30" src="https://github.com/user-attachments/assets/cfda8ac7-71af-406a-8f1c-aabc390e13af" />

### 10. Write Data to a File
1) Read the adult_joined.table file by executing the Table Reader node
2) Calculate the total number of rows and average age by gender and income class. Are women with income >50K in average older or younger than men with income >50K?
3) Write the resulting table as a CSV file into the data folder 

<img width="364" height="149" alt="Screenshot 2026-11-11 at 01 53 23" src="https://github.com/user-attachments/assets/fe496969-0fdd-47d1-8d2c-f35e0f07d828" />

### 11. BIRT Report

1) Execute the workflow below. It preprocesses and visualizes the adult dataset. 
2) Send the sorted data and bar chart image to BIRT for use in a report
3) In the BIRT Report editor, use a grid to layout the following elements:
- A report title
- A formatted pivot table
- A bar chart image
4) What are the names of the imported elements (table and image) in the BIRT editor?

<img width="1040" height="363" alt="Screenshot 2026-11-11 at 01 54 23" src="https://github.com/user-attachments/assets/746c83ec-7b9c-4256-94ad-42d31f593460" />


## V. Conclusion

These exercises provided hands-on experience with the core stages of a Business Intelligence workflow, from data preparation and exploration to machine learning and reporting. They strengthened practical skills in KNIME and demonstrated how data can be processed and transformed into useful analytical insights.
