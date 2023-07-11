# API-Data-Extraction-and-Transformation-for-ERP-Integration

The script is a Python-based data extraction, transformation, and loading (ETL) project. Here is what the script does:

Data Extraction (API calls):

It defines a function get_all_resources_url(url). This function fetches all the data from an API URL provided by a report builder. It fetches all pages of data until there's no more data to fetch. It stores the data in a list, then converts this list to a pandas DataFrame, and returns it.
The function fetch_combine_store_data(urls, table_name, key) uses the get_all_resources_url(url) function to fetch data from a list of URLs, combines this data into a single DataFrame, and stores this DataFrame as a CSV file on the specified path.
Data Transformation (Cleaning and reshaping the data):

The remove_high_null_columns(df, col_null_threshold=0.05) function removes columns from a DataFrame that have a high percentage of null values based on a specified threshold. It returns a cleaned DataFrame.
The function clean_store_data(df, table_name, col_null_threshold=0.05) utilizes the above function to clean a DataFrame, then it stores the cleaned DataFrame as a CSV file on the specified path.
Following the cleaning, it performs additional transformations on the DataFrame like splitting column values, removing certain characters, and adjusting leading and trailing spaces.
It also deals with duplicates in the data by adding a count number in brackets for duplicated values.
Data Loading:

The final DataFrame is saved to a CSV file.
As a part of this ETL pipeline, the cleaned and transformed data is prepared for uploading into another system (for example, an ERP system or a database).

The purpose of this script is to pull data from multiple APIs, clean and transform the data as needed, and finally, prepare it for loading into another system or application. This kind of process is common in data analysis and data science projects, where data needs to be moved and transformed between different systems.
