
# **Week 1: Hands-on Labs: Importing Data Sets**

## Lab: Importing Data Sets - Used Cars Pricing

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
