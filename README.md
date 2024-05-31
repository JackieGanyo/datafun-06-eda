# Project 6 EDA Notebook

## Jackie Ganyo

## Purpose: Exploratory Data Analysis (EDA) Jupyter Notebook Project

This Jupyter Notebook project aims to perform Exploratory Data Analysis (EDA) on a ______given______ dataset. The purpose of this project is to gain insights, discover patterns, and identify trends in the data through various statistical and visual exploration techniques. By analyzing the data, we can better understand its characteristics, uncover potential relationships between variables, and make informed decisions for further analysis or modeling.

Please note that this documentation comment is specific to the Jupyter Notebook project mentioned in the filepath provided.

### Link to Module 6 Specifications

<https://github.com/denisecase/datafun-06-spec>

## Requirements

### 1. Environment Setup

Create and activate the project virtual environment.
Install all required packages into your local project virtual environment.
After installing the required dependencies, update or generate a requirements.txt file.
Add a .gitignore file to your project with useful entries. See .gitignore example.
Document the steps and commands in your README.md.

### 2. Project Start

Make sure Jupyter is installed and working in your project virtual environment. Document the process and commands you used in your README.md.

Then create, open, and start a new notebook in your root project repository folder:

Create the Notebook: In the VS Code Explorer, create a new file i.e., yourname_eda.ipynb. Ensure it has a .ipynb extension.
Verify your new notebook is open for editing. If needed, view the project files in VS Code Explorer and double-click the notebook file to open it for editing.
Add a Markdown cell at the top of your notebook with the introduction (include the title, author, date and the purpose of the project).

### 3. Import Dependencies (At the Top, After the Introduction)

Add a Python cell next with the import statements for the libraries you will use in the project. Follow conventional package import organization and alias. Import each package just once near the top of the file. Be sure you have INSTALLED any external packages (outside the Python Standard Library) into your active project virtual environment first.

Jupyter Notebook / Python cell example:

import matplotlib.pyplot as plt
import pandas as pd
import seaborn as sns

Execute the cell to ensure everything works. If you get errors on one of the statements above, the most common issue is that package has not been installed into the active project virtual environment. When you find you need a new package, first install it into the active project virtual environment and then import it near the top of your Python or Notebook file.

### 4. Exploratory Data Analysis

Perform a unique exploratory data analysis project using the tools and skills covered previously.

#### Step 1. Data Acquisition

Load the data into a pandas DataFrame. Use the pd read functions such as pd.read_csv() or pd.read_excel() as appropriate. To read from the Seaborn dataset, we'll use sns.load_dataset() function and pass in the 'iris' (the name without .csv) to populate our DataFrame.

Jupyter Notebook / Python cell example:

Load the dataset into a pandas DataFrame - adjust this process for your custom data
df = sns.load_dataset('iris')

Inspect first rows of the DataFrame
print(df.head())

#### Step 2. Initial Data Inspection

Display the first 10 rows of the DataFrame, check the shape, and display the data types of each column using df.head(10), df.shape, and df.dtypes.

Jupyter Notebook / Python cell example:

print(df.head(10))
print(df.shape)
print(df.dtypes)

#### Step 3. Initial Descriptive Statistics

Use the DataFrame describe() method to display summary statistics for each column.

Jupyter Notebook / Python cell example:

print(df.describe())

#### Step 4. Initial Data Distribution for Numerical Columns

Choose a numerical column and use df['column_name'].hist() to plot a histogram for that specific column. To show all the histograms for all numerical columns, use df.hist().

Jupyter Notebook / Python cell example:

Inspect histogram by numerical column
df['sepal_length'].hist()

Inspect histograms for all numerical columns
df.hist()

Show all plots
plt.show()
Afterwards, use a Markdown cell to document your observations.

#### Step 5. Initial Data Distribution for Categorical Columns

Choose a categorical column and use df['column_name'].value_counts() to display the count of each category. Use a loop to show the value counts for all categorical columns.

Jupyter Notebook / Python cell example:

Inspect value counts by categorical column
df['species'].value_counts()

Inspect value counts for all categorical columns
for col in df.select_dtypes(include=['object', 'category']).columns:
    # Display count plot
    sns.countplot(x=col, data=df)
    plt.title(f'Distribution of {col}')
    plt.show()

Show all plots
plt.show()
Afterwards, use a Markdown cell to document your observations.

#### Step 6. Initial Data Transformation and Feature Engineering

Use pandas and other tools to perform transformations. Transformation may include renaming columns, adding new columns, or transforming existing data for more in-depth analysis.

For this project, you must:

Rename at least one column.
Add at least one column.

#### Step 7. Initial Visualizations

Create a variety of chart types using seaborn and matplotlib to showcase different aspects of your data. For each chart, include the goal - what you want to learn/explore, the type of chart you choose, display the chart, and tell your data story. Use Markdown cells and Python cells. Create at least 3 subsections - each subsection should have the following parts:

Goal: The question you are exploring.
Chart Type: Tell us what kind of chart you choose to illustrate this goal.
Chart: Display the chart.
Story: Use Markdown cell(s) to document your observations and insights.

#### Step 8. Initial Storytelling and Presentation

Present your notebook with an opening that introduces yourself and your topic. Use Markdown section headings to introduce each step. Interpret the visualizations and statistics to narrate a clear and compelling data story. Present your findings in a logical and engaging manner.
