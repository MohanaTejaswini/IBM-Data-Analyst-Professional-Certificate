
## **Week 1: Hands-on Labs: Importing Data Sets**

### Lab: Importing Data Sets - Used Cars Pricing
[Lab reviewed Sheet](https://github.com/MohanaTejaswini/Project-1/blob/main/7%20-%20Data%20Analysis%20with%20Python/week%201-%20Lab%20Importing%20Data%20Sets%20(E)%20-%20Used%20Cars%20Pricing-%20DA0101EN-Review-Introduction.ipynb)

As part of a Lab we used Jupyter Notebook or a Python script that aims to demonstrate data acquisition and basic data exploration using the Pandas library. 

1. Data Acquisition:
   - The code mentions that data can be stored in various formats such as .csv, .json, .xlsx, and can be located either on a local machine or online.
   - It instructs how to install necessary libraries using `pip` when running the lab in the browser.

2. Importing Libraries:
   - The code installs several Python libraries using `piplite` and `micropip` for data analysis:
     - `pandas`: Used for data manipulation and analysis.
     - `matplotlib`: Used for data visualization.
     - `scipy`: Scientific library for various scientific and technical computing tasks.
     - `seaborn`: A data visualization library built on top of matplotlib.
     - `ipywidgets`: Provides interactive widgets for Jupyter notebooks.
     - `tqdm`: A progress bar for loops and processes.

3. Downloading the Dataset:
   - The code defines an `async` function called `download(url, filename)` which can be used to download a dataset from a specified URL. It uses the `pyodide` library to fetch the data and saves it as a local file.

4. Reading Data:
   - The code uses `pd.read_csv(path, header=None)` to read the downloaded CSV file into a Pandas DataFrame (`df`) without considering the first row as column headers. The DataFrame is then displayed using `df.head(5)` to show the first 5 rows.

   - A question is posed to check the bottom 10 rows of the DataFrame using `df.tail(10)`.

5. Adding Headers:
   - The code adds column headers to the DataFrame. It creates a list `headers` that contains the column names and then assigns this list to the DataFrame using `df.columns = headers`. This allows the DataFrame to have meaningful column names.

6. Handling Missing Values:
   - The code replaces "?" values with NaN in the DataFrame using `df.replace('?', np.NaN)`. This is done to handle missing values in the dataset.

   - The code also removes rows with missing values in the "price" column using `df = df1.dropna(subset=["price"], axis=0)`.

7. Basic Insights of the Dataset:
   - The code provides an example of how to obtain insights into the dataset, including data types, summary statistics, and additional information using the following Pandas functions:
     - `df.dtypes`: Displays the data types of each column.
     - `df.describe()`: Provides summary statistics for numeric columns.
     - `df.describe(include="all")`: Provides summary statistics for all columns.
     - `df.info()`: Prints a concise summary of the DataFrame, including non-null values and data types.

8. Additional Operations:
   - The code demonstrates how to select and describe specific columns within the DataFrame using the `.describe()` method.

### Lab: Importing Data Sets - Laptop Pricing
[Lab reviewed Sheet](https://github.com/MohanaTejaswini/Project-1/blob/main/7%20-%20Data%20Analysis%20with%20Python/week%201-%20Lab%20Importing%20Datasets%20(E)%20-%20Laptop%20Pricing-Practice_data_(Laptop%20pricing%20data)loading.ipynb)

This code performs various tasks related to loading and inspecting a dataset using the Pandas library in Python. Here's an explanation of each task:

**Task 1:** Load the dataset to a pandas dataframe named 'df' and print the first 5 entries of the dataset.
- The `pd.read_csv` function is used to read a CSV file and create a Pandas DataFrame from it. The `path` variable specifies the file path.
- `header=None` indicates that the CSV file doesn't have column headers, and Pandas should assign default column names.

**Task 2:** Add headers to the dataframe and print the first 10 rows of the dataset.
- This code defines a list of column headers and assigns them to the DataFrame using `df.columns`.
- It also prints the first 10 rows to confirm the insertion of column headers.

**Task 3:** Replace '?' with 'NaN' in the dataset.
- This code uses `df.replace` to replace all occurrences of '?' with 'NaN' (Not a Number) in the DataFrame. The changes are made in place.

**Task 4:** Print the data types of the dataframe columns.
- This code uses the `.dtypes` attribute of the DataFrame to display the data types of each column.

**Task 5:** Print the statistical description of the dataset, including that of 'object' data types.
- This code provides a statistical summary of the dataset using the `.describe` method. The `include='all'` parameter ensures that statistics for both numerical and object data types are displayed.

**Task 6:** Print the summary information of the dataset.
- This code uses `df.info()` to display a concise summary of the DataFrame, including information about the number of non-null values and data types for each column.

These tasks help you import the dataset, clean it by replacing missing values, assign column headers, and gain an initial understanding of the dataset's structure and characteristics.

----

## **Week 2: Hands-on Labs: Data Wrangling**

### Lab: Data Wrangling - Used Cars Pricing
[Lab reviewed Sheet](https://github.com/MohanaTejaswini/Project-1/blob/main/7%20-%20Data%20Analysis%20with%20Python/week%202-%20Lab%20Data%20Wrangling%20(E)%20-%20Used%20Cars%20Pricing-DA0101EN-2-Review-Data-Wrangling.ipynb)

**Data Wrangling Functions and Process:**

1. **Identify and Handle Missing Values:**
   - *Identify Missing Values:*
     - Function: `df.isnull()`
     - Explanation: Use this function to locate missing values in your DataFrame. It returns a DataFrame of the same shape as the input with True (missing) and False (non-missing) values.
   - *Deal with Missing Values:*
     - Functions: `df.dropna()`, `df.fillna()`, `df.interpolate()`, etc.
     - Explanation: Choose the appropriate function to handle missing values. 
       - `dropna()`: Removes rows or columns with missing values.
       - `fillna()`: Fills missing values with specified values.
       - `interpolate()`: Interpolates missing values based on surrounding data.

2. **Correct Data Format:**
   - Ensure that data is in the correct format, addressing data type conversions and formatting issues. This is not a specific function but part of data cleaning.

3. **Data Standardization:**
   - Explanation: Standardize data by scaling numerical values to have a specific mean and standard deviation. This often involves using the formula: `(x - mean(x)) / std(x)` for each value 'x'.

4. **Data Normalization:**
   - Explanation: Normalize data to a predefined range, such as [0, 1]. This can be done using the formula: `(x - min(x)) / (max(x) - min(x))` for each value 'x'.

5. **Binning:**
   - Function: `pd.cut()`
   - Explanation: Use `pd.cut()` to bin continuous data into discrete categories. You specify the number of bins and the range. Useful for converting continuous variables into categorical ones.
   - Example: `pd.cut(df['column_name'], bins, labels=labels)`.

6. **Indicator Variables:**
   - Function: `pd.get_dummies()`
   - Explanation: Employ `pd.get_dummies()` to perform one-hot encoding of categorical variables. It generates binary indicator variables for each category, allowing machine learning models to work with categorical data without ordinal relationships.
   - Example: `pd.get_dummies(df, columns=['categorical_column'])`.

These data wrangling steps are essential for cleaning, formatting, and preparing data for analysis, machine learning, or other data-related tasks. The choice of which function to use depends on the specific characteristics of your dataset and your analysis goals.

### Lab: Data Wrangling - Laptop Pricing
[Lab reviewed Sheet](https://github.com/MohanaTejaswini/Project-1/blob/main/7%20-%20Data%20Analysis%20with%20Python/week%202-%20Lab%20Data%20Wrangling%20(E)-%20Laptop%20Pricing-practice_data_wrangling.ipynb)

**Lab Objectives:**
1. **Handle Missing Data:**
   - Identify columns with missing values and visualize the missing data.
   - Replace missing values using appropriate strategies.

2. **Correct Data Types:**
   - Modify the data types of specific columns to match their actual data.

3. **Data Standardization:**
   - Standardize specific columns to a common unit.

4. **Data Normalization:**
   - Normalize a numerical attribute to a specific range (usually [0, 1]).

5. **Binning:**
   - Create categorical bins for a continuous variable, grouping similar values together.

6. **Indicator Variables:**
   - Convert a categorical attribute into binary indicator variables.

**Detailed Explanation:**

1. **Handle Missing Data:**
   - *Identify Missing Data:*
     - Used `df.isnull()` to create a DataFrame of the same shape with True (missing) and False (non-missing) values.
   - *Column-wise Analysis:*
     - Loop through columns and count missing values in each column using `missing_data[column].value_counts()`.
   
2. **Replace with Mean:**
   - Missing values in the "Weight_kg" attribute were replaced with the mean value of the column.
   - Used `df["Weight_kg"].replace(np.nan, avg_weight, inplace=True)` for this purpose.

3. **Replace with Most Frequent Value:**
   - Missing values in the "Screen_Size_cm" attribute were replaced with the most frequent value in the column.
   - Used `common_screen_size = df['Screen_Size_cm'].value_counts().idxmax()` for this task.

4. **Fixing Data Types:**
   - Corrected data types for "Weight_kg" and "Screen_Size_cm" by using `df[["Weight_kg","Screen_Size_cm"]] = df[["Weight_kg","Screen_Size_cm"]].astype("float")`.

5. **Data Standardization:**
   - Standardized "Weight_kg" to pounds and "Screen_Size_cm" to inches:
     - `df["Weight_kg"] = df["Weight_kg"] * 2.205`
     - `df.rename(columns={'Weight_kg':'Weight_pounds'}, inplace=True)`
     - `df["Screen_Size_cm"] = df["Screen_Size_cm"] * 2.54`
     - `df.rename(columns={'Screen_Size_cm':'Screen_Size_inch'}, inplace=True)`.

6. **Data Normalization:**
   - Normalized the "CPU_frequency" attribute by dividing each value by the maximum value in the column:
     - `df['CPU_frequency'] = df['CPU_frequency'] / df['CPU_frequency'].max()`.

7. **Binning:**
   - Created 3 bins for the "Price" attribute ("Low," "Medium," and "High"):
     - Defined the bins using `bins = np.linspace(min(df["Price"]), max(df["Price"]), 4)`.
     - Assigned labels using `group_names = ['Low', 'Medium', 'High']`.
     - Added a new column "Price-binned" with the bin labels using `pd.cut()`.

8. **Indicator Variables:**
   - Converted the "Screen" attribute into indicator variables "Screen-IPS_panel" and "Screen-Full_HD" using `pd.get_dummies()` and renaming the columns.
   - Dropped the original "Screen" attribute using `df.drop("Screen", axis=1, inplace=True)`.

The dataset was processed and transformed according to the objectives, and the changes were verified using `df.head()` to ensure data quality and consistency.

----

## **Week 3: Hands-on Labs: Exploratory Data Analysis**

### Lab: Exploratory Data Analysis - Used Car Pricing
[Lab reviewed Sheet](https://github.com/MohanaTejaswini/IBM-Data-Analyst-Professional-Certificate/blob/main/7%20-%20Data%20Analysis%20with%20Python/%E2%9C%8D%F0%9F%93%82Hands-on-Lab-FILES/week%203-%20Lab%20Exploratory%20Data%20Analysis%20(E)-%20Used%20Car%20Pricing-Exploratory_data_analysis_cars.ipynb)

In the provided code and explanation, various functions and concepts related to data analysis and visualization are used. I will explain each function and concept with examples:

1. Importing Libraries:
   - `import matplotlib.pyplot as plt` and `import seaborn as sns` are used to import the Matplotlib and Seaborn libraries for data visualization.
   - `%matplotlib inline` is a Jupyter Notebook magic command that allows plots to be displayed directly in the notebook.

2. Checking Data Types:
   - `df.dtypes` is used to check the data types of columns in a DataFrame `df`. It helps identify whether a variable is numeric or categorical.

3. Correlation Analysis:
   - `df.corr()` computes the correlation matrix between numeric columns in the DataFrame, indicating the strength and direction of linear relationships between variables.

4. Scatter Plots with Regression Lines:
   - `sns.regplot()` is used to create scatter plots with fitted regression lines. It helps visualize relationships between two continuous variables.
   - Example: `sns.regplot(x="engine-size", y="price", data=df)` creates a scatter plot for the "engine-size" vs. "price" relationship.

5. Box Plots:
   - `sns.boxplot()` is used to create box plots, which visualize the distribution of a variable within different categories.
   - Example: `sns.boxplot(x="body-style", y="price", data=df)` creates a box plot to compare "body-style" categories with "price."

6. Descriptive Statistical Analysis:
   - `df.describe()` provides summary statistics for continuous variables, including count, mean, standard deviation, minimum, maximum, and quartiles.
   - `df.describe(include=['object'])` does the same for categorical variables.

7. Value Counts:
   - `df['drive-wheels'].value_counts()` counts the number of occurrences for each category in a categorical variable.

8. Grouping Data:
   - The `groupby()` function groups data based on specific categories or variables.
   - Example: `df_group_one = df[['drive-wheels','body-style','price']]` selects specific columns for grouping.
   - Then, you can calculate statistics for each group, such as the average price for different drive-wheel categories.

9. Pivot Tables:
   - Pivot tables help organize grouped data into a tabular format.
   - `grouped_test1.pivot(index='drive-wheels', columns='body-style')` creates a pivot table with drive-wheels as rows and body-style as columns.

10. Pearson Correlation:
    - Pearson correlation measures the linear relationship between two variables.
    - `stats.pearsonr(x, y)` calculates the Pearson Correlation Coefficient and its associated p-value.
    - A high correlation coefficient (close to 1 or -1) indicates a strong linear relationship, while a low p-value suggests statistical significance.

11. Correlation and Causation:
    - Emphasizes that correlation does not imply causation. Correlation shows a relationship, but further analysis is needed to establish causation.

In your analysis, you've explored variables such as engine size, highway mpg, peak rpm, stroke, and more, assessing their relationships with car prices. This is a fundamental step in understanding which variables are important for building predictive models. You've also examined how to use various visualization techniques to convey these relationships effectively.

### Lab: Exploratory Data Analysis - Laptop Pricing
[Lab reviewed Sheet](https://github.com/MohanaTejaswini/IBM-Data-Analyst-Professional-Certificate/blob/main/7%20-%20Data%20Analysis%20with%20Python/%E2%9C%8D%F0%9F%93%82Hands-on-Lab-FILES/week%203-%20Lab%20Exploratory%20Data%20Analysis%20(E)-%20Laptop%20Pricing-%20Exploratory_data_analysis.jupyterlite.ipynb)

1. **Visualize individual feature patterns**:
   - In this part of the lab, you are visualizing the relationship between individual features and the target variable "Price."
   - `sns.regplot`: This function is used to create a regression plot. It shows the relationship between two variables by fitting a linear regression model and plotting the data points.
   - `x` and `y` parameters in `sns.regplot` specify the variables to be plotted on the x-axis and y-axis.
   - `plt.ylim(0,)` sets the y-axis limit to start from 0. This is used to ensure that the plot starts from 0 on the y-axis.

2. **Descriptive Statistical Analysis**:
   - In this part of the lab, you are generating statistical descriptions of the dataset, including both numeric and categorical data.
   - `df.describe()`: This function provides statistical information such as count, mean, standard deviation, minimum, and maximum values for numeric columns in the DataFrame.
   - `df.describe(include=['object'])`: This extends the description to include object (categorical) columns.

3. **GroupBy and Pivot Tables**:
   - Here, you are grouping the dataset by specific columns and creating a pivot table to visualize the connection between two categorical variables and the target variable.
   - `grouped_test1`: This DataFrame is created by grouping the dataset by 'GPU' and 'CPU_core' columns and calculating the mean of the 'Price' column within each group.
   - `grouped_pivot`: This is a pivot table created from the `grouped_test1` DataFrame to visualize the relationship between 'GPU' and 'CPU_core' with 'Price.'

4. **Pearson Correlation and p-values**:
   - You are calculating the Pearson correlation coefficients and p-values to understand the strength and significance of the relationships between various features and the target variable.
   - `stats.pearsonr`: This function from the `scipy` library calculates the Pearson correlation coefficient and a two-tailed p-value.
   - It measures the linear relationship between two datasets. The correlation coefficient ranges from -1 (perfect negative correlation) to 1 (perfect positive correlation), with 0 indicating no linear correlation.
   - A low p-value suggests that the correlation is statistically significant.

This lab guides you through exploring and analyzing the laptops pricing dataset, which includes data visualization, statistical analysis, and correlation measurements to understand how different features affect the price of laptops.


----

## **Week 4: Hands-on Labs: Model Development**

### Lab: Model Development - Used Car Pricing
[Lab reviewed Sheet](https://github.com/MohanaTejaswini/IBM-Data-Analyst-Professional-Certificate/blob/main/7%20-%20Data%20Analysis%20with%20Python/%E2%9C%8D%F0%9F%93%82Hands-on-Lab-FILES/week%204-%20Lab%20Model%20Development%20(E)%20-%20Used%20Car%20Pricing-DA0101EN-4-Review-Model-Development.ipynb)

1. **Import Libraries:**
   - `import pandas as pd`: Imports the Pandas library for data manipulation.
   - `import numpy as np`: Imports the NumPy library for numerical operations.
   - `import matplotlib.pyplot as plt`: Imports the Matplotlib library for data visualization.
   - `from sklearn.linear_model import LinearRegression`: Imports the LinearRegression class from scikit-learn for linear regression modeling.

2. **Loading Data:**
   - The data is loaded from a CSV file (in this case, "usedcars.csv") into a Pandas DataFrame using `pd.read_csv(path)`.

3. **Linear Regression:**
   - `LinearRegression()`: Creates a linear regression model object from scikit-learn.

4. **Fitting a Linear Model:**
   - `lm.fit(X, Y)`: Fits the linear regression model with input features `X` and target variable `Y`.

5. **Intercept and Coefficients:**
   - `lm.intercept_`: Accesses the intercept (a) of the linear model.
   - `lm.coef_`: Accesses the coefficients (b) of the linear model.

6. **Model Evaluation Metrics:**
   - `lm.score(X, Y)`: Computes the R-squared (coefficient of determination) to measure the goodness of fit.
   - `mean_squared_error(y_true, y_pred)`: Computes the Mean Squared Error (MSE) to measure the accuracy of the model's predictions.

7. **Visualization with Seaborn:**
   - `import seaborn as sns`: Imports the Seaborn library for data visualization.
   - `sns.regplot(x, y, data=df)`: Creates a scatter plot with a fitted regression line.
   - `sns.residplot(x, y)`: Creates a residual plot to visualize the spread of residuals.

8. **Polynomial Regression:**
   - Polynomial regression models are created and fitted using `np.polyfit(x, y, degree)` and `np.poly1d(f)` functions.

9. **Creating a Polynomial Features Object:**
   - `from sklearn.preprocessing import PolynomialFeatures`: Imports PolynomialFeatures for generating polynomial features.

10. **Data Pipelines:**
    - Data preprocessing pipelines are created to streamline data transformation and modeling steps.

11. **Creating a Pipeline:**
    - `from sklearn.pipeline import Pipeline`: Imports the Pipeline class for creating a sequence of data processing steps.
    - `pipe=Pipeline(steps)`: Initializes a data processing pipeline.

12. **Pipeline Steps:**
    - Data preprocessing steps, such as scaling and polynomial feature generation, are defined in a list of tuples and passed to the pipeline constructor.

13. **Fitting a Model with a Pipeline:**
    - `pipe.fit(X, y)`: Fits the data preprocessing steps and model simultaneously.

14. **Predictions with a Pipeline:**
    - `pipe.predict(X)`: Generates predictions using the fitted pipeline.

15. **Model Evaluation Metrics (R-squared and MSE):**
    - The lab uses R-squared and Mean Squared Error (MSE) to evaluate model performance.

16. **Visualizing Predictions:**
    - Predictions are visualized using Matplotlib by plotting input data against model predictions.

17. **Decision Making for Model Selection:**
    - Decision criteria are discussed based on R-squared and MSE for selecting the best-fitting model.

These notes provide an overview of the functions and concepts used in the lab. Please refer to the specific code blocks and explanations in the lab for more details and context.

### Lab: Model Development - Laptop Pricing
[Lab reviewed Sheet](https://github.com/MohanaTejaswini/IBM-Data-Analyst-Professional-Certificate/blob/main/7%20-%20Data%20Analysis%20with%20Python/%E2%9C%8D%F0%9F%93%82Hands-on-Lab-FILES/week%204-%20Lab%20Model%20Development%20(E)-%20Laptop%20Pricing-%20practice_model_development_laptops.jupyterlite.ipynb)

**Task 1: Single Linear Regression**

1. **LinearRegression() Function**:
   - Purpose: This function is used to create a linear regression model.
   - Notes: It's used to perform linear regression with one independent variable (in this case, 'CPU_frequency').

2. **lm.fit(X, Y)**:
   - Purpose: This function fits the linear regression model to the data.
   - Notes: It calculates the parameters of the linear model that best fits the relationship between the independent variable ('CPU_frequency') and the dependent variable ('Price').

3. **sns.distplot() Function**:
   - Purpose: This function is used to create a distribution plot.
   - Notes: In this lab, it's used to visualize and compare the distribution of actual prices ('Actual Value') with the distribution of predicted prices ('Fitted Values').

4. **mean_squared_error() Function**:
   - Purpose: This function calculates the mean squared error (MSE) of the model.
   - Notes: It measures the average squared difference between the actual prices and the predicted prices. A lower MSE indicates a better fit.

5. **R-squared (R^2) Score**:
   - Purpose: R-squared measures the goodness of fit of the linear regression model.
   - Notes: It quantifies the proportion of the variance in the dependent variable ('Price') that is predictable from the independent variable ('CPU_frequency'). An R^2 score closer to 1 indicates a better fit.

**Task 2: Multiple Linear Regression**

1. **LinearRegression() Function**:
   - Purpose: Same as in Task 1, this function is used to create a linear regression model.

2. **Multiple Independent Variables**:
   - Purpose: In this task, several independent variables are used.
   - Notes: Multiple features, including 'CPU_frequency', 'RAM_GB', 'Storage_GB_SSD', 'CPU_core', 'OS', 'GPU', and 'Category', are used to create a multiple linear regression model.

3. **Visualization of Distribution Plot**:
   - Purpose: Same as in Task 1, it's used to create a distribution plot for actual and predicted values.

4. **MSE and R^2 Evaluation**:
   - Purpose: Similar to Task 1, these metrics are used to evaluate the performance of the multiple linear regression model.

**Task 3: Polynomial Regression**

1. **Polynomial Feature Generation**:
   - Purpose: Polynomial features are generated for 'CPU_frequency'.
   - Notes: Polynomial regression is used to fit polynomials of different degrees (1, 3, and 5) to the data to capture non-linear relationships.

2. **PlotPolly() Function**:
   - Purpose: A custom function for plotting polynomial regression.
   - Notes: This function plots the polynomial response over the actual data points, providing visual insight into how well the polynomial fits the data.

**Task 4: Pipeline**

1. **Pipeline Creation**:
   - Purpose: A machine learning pipeline is created.
   - Notes: The pipeline includes three steps: scaling of parameters, generation of polynomial features, and linear regression. It's used to streamline the process.

2. **MSE and R^2 Evaluation**:
   - Purpose: Similar to previous tasks, these metrics are used to evaluate the performance of the pipeline, which combines scaling, polynomial features, and linear regression.

These notes provide an overview of the functions and concepts used in the lab without the specific Python code.

----

## **Week 5: Hands-on Labs: **

### Lab: 
[Lab reviewed Sheet](https://github.com/MohanaTejaswini/Project-1/blob/main/7%20-%20Data%20Analysis%20with%20Python/week%201-%20Lab%20Importing%20Data%20Sets%20(E)%20-%20Used%20Cars%20Pricing-%20DA0101EN-Review-Introduction.ipynb)

----

## **Week 6: Hands-on Labs: **

### Lab: 
[Lab reviewed Sheet](https://github.com/MohanaTejaswini/Project-1/blob/main/7%20-%20Data%20Analysis%20with%20Python/week%201-%20Lab%20Importing%20Data%20Sets%20(E)%20-%20Used%20Cars%20Pricing-%20DA0101EN-Review-Introduction.ipynb)
