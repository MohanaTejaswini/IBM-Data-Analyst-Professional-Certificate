
## **Week 1: Hands-on Labs: Importing Data Sets**

### Lab: Importing Data Sets - Used Cars Pricing
[Lab reviewed Sheet](https://github.com/MohanaTejaswini/Project-1/blob/main/7%20-%20Data%20Analysis%20with%20Python/DA0101EN-executed-Review-Introduction.jupyterlite.ipynb)

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

### Lab: Importing Data Sets - Used Cars Pricing
[Lab reviewed Sheet](https://github.com/MohanaTejaswini/Project-1/blob/main/7%20-%20Data%20Analysis%20with%20Python/Practice_data_(executed-Laptop%20pricing%20data)loading.jupyterlite.ipynb)

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
[Lab reviewed Sheet](https://github.com/MohanaTejaswini/Project-1/blob/main/7%20-%20Data%20Analysis%20with%20Python/DA0101EN-2-Review-executed-Data-Wrangling-20231003-1696291200.jupyterlite.ipynb)

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
