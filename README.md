# CustomerDataCleaning
A Python-based project for cleaning and standardizing customer data in a SQL Server database. The project includes scripts for removing invalid prefixes, cleaning special characters, updating database entries, and ensuring data consistency.

- Removing titles like "آقای", "خانم", "مهندس", etc.
- Cleaning up special characters and numbers
- Generating a cleaned `CleanFullName` column
- Updating data in-place in the database
- Preparing for further processes like generating unique Customer IDs

## Features

- Python-based data processing using `pandas` and `re`
- Efficient batch updating using `executemany` for better performance
- Resilient to connection issues using automatic reconnection

## Folder Structure

- `CleanFullName.ipynb`: Main script for cleaning names and updating the database
- `unique_customer_id.py`: (Coming soon) Script for generating unique customer IDs
- `sql/create_table.sql`: SQL commands to create the base `CustomerInfo` table

## How to Use

1. Create the database table using `sql/create_table.sql`
2. Insert test data using `sql/sample_data.sql`
3. Run `clean_fullname.py` to clean and update the data
4. (Optional) Run `unique_customer_id.py` for unique IDs

## Notes

> Sensitive information like database credentials must not be included. You can replace them with placeholders like:

```python
conn = pymssql.connect(
    server='YOUR_SERVER',
    user='YOUR_USER',
    password='YOUR_PASSWORD',
    database='YOUR_DATABASE'
)
