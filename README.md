# Acquiring and Processing Information on the World's Largest Banks

## Project Overview
This project involves building a script that automates the acquisition and transformation of financial data for the world's top 10 largest banks, ranked by market capitalization. The data is extracted from a Wikipedia page, processed into various currencies, and stored both locally as a CSV file and in a database table. This script is designed to be reusable for generating updated reports every financial quarter.

## Project Scenario
You have been hired as a data engineer by a research organization. Your boss has asked you to create a code that can be used to compile the list of the top 10 largest banks in the world ranked by market capitalization in billion USD. Further, the data needs to be transformed and stored in GBP, EUR, and INR as well, in accordance with the exchange rate information that has been made available to you as a CSV file. The processed information table is to be saved locally in a CSV format and as a database table.

Your job is to create an automated system to generate this information so that it can be executed in every financial quarter to prepare the report.

### Project Parameters

| Parameter                         | Value                                                                                                                                                             |
|-----------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Code name**                     | `banks_project.py`                                                                                                                                                |
| **Data URL**                      | [List of largest banks](https://web.archive.org/web/20230908091635/https://en.wikipedia.org/wiki/List_of_largest_banks)                                             |
| **Exchange rate CSV path**        | [Exchange Rate CSV](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMSkillsNetwork-PY0221EN-Coursera/labs/v2/exchange_rate.csv)                |
| **Table Attributes (Initial)**    | `Name`, `MC_USD_Billion`                                                                                                                                           |
| **Table Attributes (Final)**      | `Name`, `MC_USD_Billion`, `MC_GBP_Billion`, `MC_EUR_Billion`, `MC_INR_Billion`                                                                                      |
| **Output CSV Path**               | `./Largest_banks_data.csv`                                                                                                                                         |
| **Database name**                 | `Banks.db`                                                                                                                                                        |
| **Table name**                    | `Largest_banks`                                                                                                                                                   |
| **Log file**                      | `code_log.txt`                                                                                                                                                    |

## Project Tasks

### Task 1: Logging Function
Write a function `log_progress()` to log the progress of the code at different stages in a file `code_log.txt`. Use the list of log points provided to create log entries at every stage of the code.

### Task 2: Data Extraction
Extract the tabular information from the given URL under the heading 'By market capitalization' and save it to a dataframe.

- **Step 1:** Inspect the webpage and identify the position and pattern of the tabular information in the HTML code.
- **Step 2:** Write the code for a function `extract()` to perform the required data extraction.
- **Step 3:** Execute a function call to `extract()` to verify the output.

### Task 3: Data Transformation
Transform the dataframe by adding columns for Market Capitalization in GBP, EUR, and INR, rounded to 2 decimal places, based on the exchange rate information shared as a CSV file.

- **Step 1:** Write the code for a function `transform()` to perform the required task.
- **Step 2:** Execute a function call to `transform()` and verify the output.

### Task 4: Load to CSV
Load the transformed dataframe to an output CSV file. Write a function `load_to_csv()`, execute a function call, and verify the output.

### Task 5: Load to Database
Load the transformed dataframe to an SQL database server as a table. Write a function `load_to_db()`, execute a function call, and verify the output.

### Task 6: Run Queries on the Database Table
Write a function `run_query()` to execute the given set of queries and verify the output.

### Task 7: Verify Log Entries
Verify that the log entries have been completed at all stages by checking the contents of the file `code_log.txt`.

## Preliminaries: Installing Libraries and Downloading Data
Before building the code, you need to install the required libraries.

### Required Libraries:
- **requests**: For accessing the information from the URL.
- **bs4**: Contains the `BeautifulSoup` function used for web scraping.
- **pandas**: For processing the extracted data, storing it in required formats, and communicating with the databases.
- **sqlite3**: Required to create a database server connection.
- **numpy**: For the mathematical rounding operations.
- **datetime**: Contains the `datetime` function used for extracting the timestamp for logging purposes.

### Importing the Required Libraries
```python
import requests
import pandas as pd
import numpy as np
import datetime as dt
import sqlite3
from bs4 import BeautifulSoup
```

## Known Entities for the Code

- **url** = 'https://web.archive.org/web/20230908091635/https://en.wikipedia.org/wiki/List_of_largest_banks'
- **table_attr** = ["Name", "MC_USD_Billion"]
- **output_csv_path** = "./Largest_banks_data.csv"
- **db_name** = "Banks.db"
- **table_name** = "Largest_banks"
- **log_file_path** = "./code_log.txt"


# Authors
David Acosta Diaz
Data Engineer & Software Developer

# License
This project is licensed under the MIT License.
