# 6242_VisualizingH1BVisas

DESCRIPTION

Data on H-1B visa applications is used to develop an interactive and user-friendly visualization tool that provides interstate and intrastate differences between job functions, number of H-1B visas accepted, average salaries per job function, and other variables.

The data is also used to build a model that predicts whether an H-1B visa application is approved or rejected based on annual wage, type of position (full time versus part time), job category, and work-site state. Various classification algorithms (logistic regression, support vector machines, and k-nearest neighbors) are combined, as well as various approaches to handling the large training dataset. This ensemble predictive model has an accuracy of 88.5%.

The visualization tool and predictive model will assist international students in making more informed decisions when seeking employment within the United States.

Data on H-1B visa applications from 2011-2016 can be found at https://www.kaggle.com/nsharan/h-1b-visa. It contains approximately 3 million rows and 52 columns. This data is for training the models. Data on H-1B visa applications from 2017 can be found at https://www.kaggle.com/jonamjar/h1b-data-set-2017. It contains approximately 600,000 rows and 10 columns. This data is for testing the models. As not all columns are necessary and some rows have missing and/or inconsistent information, this data is first cleaned and filtered with OpenRefine.

With the refined data, the predictive model is built with the following codes.

-6242_preprocessing.R -6242_category_reduction.ipynb -6242_modeling.R

INSTALLATION

The following software must be installed.

-OpenRefine -R Studio -Python

EXECUTION

Using OpenRefine, the following data cleaning tasks with both datasets must be done.

Remove columns which contain irrelevant and/or redundant information.
Remove rows with missing values.
Remove rows which provide hourly, weekly, biweekly, or monthly wages.
Remove rows which pertain to other types of visas.
Remove rows which pertain to certified-withdrawn or withdrawn statuses.
Resolve spelling inconsistencies within the job category and work-site state columns.
Group similar categories within the job category column.
The cleaned data can then be downloaded and imported into R Studio for preprocessing with 6242_preprocessing.R. Using 6242_category_reduction.ipynb with the preprocessed data reduces the number of categories within the categorical variables. 6242_modeling.R can then be used on the data to build the models and get predicted values, and accuracy can be calculated after exporting the actual and predicted values to a csv file.
