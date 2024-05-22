# airbnb_project

Data project about the Airbnb market in Chicago.

# Objective

The objective of this project was to create an end-to-end data pipeline, from data loading and cleaning, to creating a report in PowerBI.<br />
Additionnally, my secondary goal was to integrate sqlalchemy and pyodbc in this data pipeline to interact with the database using only Python.
- [Python file](https://github.com/FlorianLD/airbnb_project/blob/main/airbnb_notebook.ipynb)
- [PowerBI report](https://github.com/FlorianLD/airbnb_project/blob/main/airbnb_report.pbix)

# Tools

- Python ([pandas](https://pandas.pydata.org/), [sqlalchemy](https://www.sqlalchemy.org/), [pyodbc](https://github.com/mkleehammer/pyodbc))
- SQL
- Microsoft SQL Server (MSSQL)
- PowerBI

# Context

The rental and vacation industry of the last 15 years is an interesting case since it has been disrupted with the arrival of new actors through the spread of internet usage. Traditional actors such as hotels and bed & breakfasts have seen Airbnb join the market as a new competitor.

One of the first steps of this project was to spend some time on the [Airbnb website](https://www.airbnb.com/) as a way to get domain knowledge, to understand what the main entities of this domain are: hosts, guests, rentals, roomtypes.<br />
To ensure consistency, these entities are always refered to with their domain name throughout the data pipeline: in the code, in the data model, and in the PowerBI report. This means that when working on data about "hosts", the "hosts" entity is consistently refered to as such in the code, in the data model and in the PowerBI report.


# Data pipeline

The file used for this project is a csv file that was loaded as a dataframe using pandas in Python.<br />
Data was then cleaned and transformed by handling NaN values, deleting useless columns, assigning correct datatypes.<br />
Once cleaned and properly transformed, the main dataframe was used to create the different tables of the data model, which was then imported in a MSSQL DB.<br />
Finally, the data model was imported in PowerBI to build the report.

![Test](/data_pipeline.png)


# Data model

The data used does not contain any "fact" data. 
Consequently, the data model was not designed in a traditional star schema but was instead turned into what could be deemed a "dimension analysis model".<br />
This data model focuses on offering high-level insights about the dimensions used such as "hosts" and "roomtypes".

![Test](/data_model.png)

# PowerBI report

While this project focuses on data cleaning and data modeling in Python, the final step of the data pipeline was to load the data model in PowerBI to create a report.
Building and using the report was the last step to make sure the data model was built properly for business use.

![Test](/powerbi_report.png)
