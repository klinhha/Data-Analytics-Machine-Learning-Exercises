
# [KNIME] Data Analytics & Machine Learning Exercises - Business Intelligence 

## 1. Overview

This project showcases practical exercises completed as part of the Business Intelligence course, using **KNIME Analytics Platform**. It covers **data access**, preprocessing, transformation, visualization, data integration, statistical analysis, machine learning, and report generation.

## 2. Objectives

- Gain hands-on experience with **KNIME workflows** and nodes.
- Practice **data cleaning**, transformation, and integration.
- **Explore** and **visualize** datasets to identify patterns.
- Apply **regression** and **classification** models.
- Evaluate **model performance** and generate reports.

## 3. Who Is This Project For?

- **Business Intelligence Students:** To review practical KNIME applications and workflows.
- **Aspiring Data Analysts:** To explore data preparation, analysis, and visualization.
- **Beginners in Machine Learning:** To understand basic regression and classification workflows.

## 4. Datasets

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

## 5. Main Processes & Exercises

### 5.1. Data Access
- Read CSV, TABLE, and Excel files using appropriate Reader nodes.
- Connect to SQLite databases and retrieve the `web_activity` table.
- Configure workflow-relative file paths.

**Screenshot:** Reader nodes and database connection.

### 5.2. Data Filtering & Transformation
- Exclude columns manually and by data type.
- Create `work-status` based on weekly working hours.
- Replace hyphens in `native-country`.
- Calculate `year-of-birth` using 1994 minus age.

**Key Question:** What are the work status, native country, and year of birth of record ID 177?

**Answer:** [Add your result]

### 5.3. Data Exploration & Visualization
- Explore dataset properties and missing values using Data Explorer.
- Visualize weekly working hours against commute time using Scatter Plot.
- Color data points by marital status and interact with selected rows.

**Key Questions & Answers:**
- How many distinct native countries are represented? [Answer]
- Which nominal columns contain missing values, and how many? [Answer]
- What relationship can be observed between working hours and commute time? [Answer]
- What are the native countries of the selected records? [Answer]

### 5.4. Data Aggregation & Pivoting
- Calculate row counts and average age by gender using GroupBy.
- Calculate modes and missing-value statistics.
- Aggregate people by work class and age bin using Pivoting.

**Key Questions & Answers:**
- Which age-bin and work-class combination is most common? [Answer]
- What is the most common education level in the private work class? [Answer]

### 5.5. Data Integration
- Join datasets using ID with Inner Join.
- Compare row and column counts after joining.
- Concatenate datasets using Union or Intersection of columns.

**Key Questions & Answers:**
- How many rows and columns are in each joined table? [Answer]
- Were any rows discarded during joining? [Answer]
- Which column is missing from one table, and which concatenation option preserves it? [Answer]

### 5.6. Machine Learning
- **Linear Regression:** Predict weekly working hours using a 75/25 training-test split.
- **Decision Tree Classification:** Predict whether income exceeds $50K using stratified sampling.
- Evaluate model performance using Numeric Scorer, Scorer, and ROC Curve nodes.

**Key Results:**
- Linear Regression: R² = [Value], MAE = [Value]
- Decision Tree: Accuracy = [Value], AUC = [Value]
- Test dataset size: [Value]

### 5.7. Data Export & Reporting
- Aggregate average age by gender and income class.
- Export the resulting table to CSV.
- Create a BIRT report containing a title, pivot table, and bar chart.

**Key Questions & Answers:**
- Are women earning over $50K older or younger on average than men? [Answer]
- What are the imported table and image element names in BIRT? [Answer]

## 6. Key Skills & Tools

- **Tool:** KNIME Analytics Platform
- **Data Processing:** Filtering, cleaning, transformation, aggregation
- **Data Integration:** Joins and concatenation
- **Visualization:** Data Explorer, Scatter Plot, Table View
- **Machine Learning:** Linear Regression, Decision Tree, model evaluation
- **Reporting:** BIRT Report

## 7. Conclusion

These exercises provided hands-on experience with the core stages of a Business Intelligence workflow, from data preparation and exploration to machine learning and reporting. They strengthened practical skills in KNIME and demonstrated how data can be processed and transformed into useful analytical insights.
