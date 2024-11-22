# Crowdfunding_ETL
This repository has been created for the fulfilment of Project 2 within the GW Bootcamp

Instructions

The instructions for this mini project are divided into the following subsections:
	•	Create the Category and Subcategory DataFrames
	•	Create the Campaign DataFrame
	•	Create the Contacts DataFrame
	•	Create the Crowdfunding Database

Create the Category and Subcategory DataFrames

Extract and transform the crowdfunding.xlsx Excel data to create a category DataFrame that has the following columns:
	•	A “category_id” column that has entries going sequentially from “cat1” to “catn”, where n is the number of unique categories
	•	A “category” column that contains only the category titles

Export the category DataFrame as category.csv and save it to your GitHub repository.

Extract and transform the crowdfunding.xlsx Excel data to create a subcategory DataFrame that has the following columns:
	•	A “subcategory_id” column that has entries going sequentially from “subcat1” to “subcatn”, where n is the number of unique subcategories
	•	A “subcategory” column that contains only the subcategory titles

Export the subcategory DataFrame as subcategory.csv and save it to your GitHub repository.

Create the Campaign DataFrame

Extract and transform the crowdfunding.xlsx Excel data to create a campaign DataFrame has the following columns:
	•	The “cf_id” column
	•	The “contact_id” column
	•	The “company_name” column
	•	The “blurb” column, renamed to “description”
	•	The “goal” column, converted to the float data type
	•	The “pledged” column, converted to the float data type
	•	The “outcome” column
	•	The “backers_count” column
	•	The “country” column
	•	The “currency” column
	•	The “launched_at” column, renamed to “launch_date” and with the UTC times converted to the datetime format
	•	The “deadline” column, renamed to “end_date” and with the UTC times converted to the datetime format
	•	The “category_id” column, with unique identification numbers matching those in the “category_id” column of the category DataFrame
	•	The “subcategory_id” column, with the unique identification numbers matching those in the “subcategory_id” column of the subcategory DataFrame

Export the campaign DataFrame as campaign.csv and save it to your GitHub repository.

Create the Contacts DataFrame

Choose one of the following two options for extracting and transforming the data from the contacts.xlsx Excel data:

Option 1: Use Python dictionary methods.
	•	Import the contacts.xlsx file into a DataFrame.
	•	Iterate through the DataFrame, converting each row to a dictionary.
	•	Iterate through each dictionary, doing the following:
	•	Extract the dictionary values from the keys by using a Python list comprehension.
	•	Add the values for each row to a new list.
	•	Create a new DataFrame that contains the extracted data.
	•	Split each “name” column value into a first and last name, and place each in a new column.
	•	Clean and export the DataFrame as contacts.csv and save it to your GitHub repository.

Option 2: Use regular expressions.
	•	Import the contacts.xlsx file into a DataFrame.
	•	Extract the “contact_id”, “name”, and “email” columns by using regular expressions.
	•	Create a new DataFrame with the extracted data.
	•	Convert the “contact_id” column to the integer type.
	•	Split each “name” column value into a first and a last name, and place each in a new column.
	•	Clean and then export the DataFrame as contacts.csv and save it to your GitHub repository.

Create the Crowdfunding Database

	•	Inspect the four CSV files, and then sketch an ERD of the tables by using QuickDBD.
	•	Use the information from the ERD to create a table schema for each CSV file.
	•	Save the database schema as a Postgres file named crowdfunding_db_schema.sql, and save it to your GitHub repository.
	•	Create a new Postgres database, named crowdfunding_db.
	•	Using the database schema, create the tables in the correct order to handle the foreign keys.
	•	Verify the table creation by running a SELECT statement for each table.
	•	Import each CSV file into its corresponding SQL table.
	•	Verify that each table has the correct data by running a SELECT statement for each.

Hints

	•	To split each “category & sub-category” column value into “category” and “subcategory” column values, use df[["new_column1","new_column2"]] = df["column"].str.split().
	•	To get the unique category and subcategory values from the “category” and “subcategory” columns, create a NumPy array where the array length equals the number of unique categories and unique subcategories from each column.
	•	To create the category and subcategory identification numbers, use a list comprehension to add the “cat” string or the “subcat” string to each number in the category or the subcategory array, respectively.
	•	To convert the “goal” and “pledged” columns to the float data type, use the astype() method.
	•	To convert the “launch_date” and “end_date” UTC times to the datetime format, see the Transform_Grocery_Orders_Solved.ipynb activity solution.
	•	To add the “category_id” and “subcategory_id” unique identification numbers to the campaign DataFrame, use the pandas.DataFrame.merge method.

Deliverables

	1.	category.csv: Contains category_id and category.
	2.	subcategory.csv: Contains subcategory_id and subcategory.
	3.	campaign.csv: Contains details about campaigns with references to categories and subcategories.
	4.	contacts.csv: Contains cleaned contact data with split names and IDs.
	5.	crowdfunding_db_schema.sql: PostgreSQL schema for the crowdfunding database.
	6.	Fully populated PostgreSQL database: crowdfunding_db.


