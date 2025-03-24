# Automated-ETL-Pipeline-for-Financial-Data-Integration-and-Analysis

## Project Overview
This project is an **Automated ETL (Extract, Transform, Load) Pipeline** designed to download, process, and store monthly financial data reports from AMFI (Association of Mutual Funds in India). It streamlines the extraction of raw data, transforms it into a structured format, and uploads it into a MySQL database for seamless storage and analysis.

The system leverages Python's powerful libraries for data manipulation and database operations, creating an end-to-end workflow for financial data integration.


## Features
- **Dynamic Data Extraction**: Automatically constructs download URLs for the previous month's report.
- **Data Transformation**:
  - Cleans, filters, and structures raw data.
  - Maps scheme types to human-readable descriptions.
  - Filters unwanted rows (e.g., totals, subtotals) for better usability.
- **Database Integration**:
  - Tests MySQL connection before any operations.
  - Creates a database table with the required schema (if not already present).
  - Uploads transformed data into the MySQL database.
- **Error Handling**: Comprehensive exception handling ensures robustness.


## Technologies Used
- **Programming Language**: Python
- **Libraries**:
  - `os`: For folder and file operations.
  - `requests`: For HTTP requests to download data.
  - `pandas`: For data manipulation and transformation.
  - `mysql.connector`: For MySQL database connectivity.
  - `datetime` and `timedelta`: For date calculations.
- **Database**: MySQL


## How It Works
1. **Extract**:  
   The script dynamically generates the URL for the AMFI Excel report based on the previous month and downloads it to a local directory.

2. **Transform**:  
   - Reads and processes the Excel file.
   - Renames columns for clarity.
   - Maps scheme types and detailed scheme types.
   - Filters out irrelevant rows and fills forward missing values.
   - Cleans and structures the data for analysis.

3. **Load**:  
   - Connects to a MySQL database.
   - Creates the necessary table schema (if not already created).
   - Inserts the transformed data into the database.


## Prerequisites
Before running the project, ensure the following:
1. **MySQL Setup**:
   - Install MySQL Server.
   - Create a database (e.g., `AMFI`) and provide the connection credentials in the script.
2. **Python Environment**:
   - Install Python 3.x.
   - Install required libraries using `pip install -r requirements.txt`.
3. **Folder Path**:  
   Set the folder path (`C:\AMFI`) in the code where the reports will be downloaded.


## How to Run
1. Clone this repository or copy the source code into your local environment.
2. Update the MySQL database credentials (host, user, password, database) in the script.
3. Run the script using the command:
   ```
   python main.py
   ```
4. Verify that the data is successfully uploaded to the MySQL database.


## Potential Enhancements
- Add a **data visualization dashboard** for real-time financial insights.
- Implement **unit tests** for validating data transformations.
- Enable **real-time scheduling** using a job scheduler (e.g., `cron` or `Airflow`).
- Add support for other data formats such as JSON or CSV.
