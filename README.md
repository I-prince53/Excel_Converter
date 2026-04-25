<img width="1559" height="518" alt="image" src="https://github.com/user-attachments/assets/040e5f82-51ed-496c-8ff2-a3bcce40ac03" />

# Retail Sales Data ETL & Automation (Pandas)
Project Overview
This project automates the consolidation and cleaning of monthly retail sales data. Using Python and Pandas, I developed a robust ETL pipeline that transforms multiple raw Excel workbooks into a single, analysis-ready dataset.

# Key Pipeline Features
1. Automated Multi-File Ingestion
Workflow: Developed a loop to programmatically read multiple monthly sales files (March through October) from a defined list.

Efficiency: Eliminated the need for manual copy-pasting, ensuring a scalable process for large-scale data consolidation.

2. Data Cleaning & Standardization
String Manipulation: Standardized CUSTOMER_NAME by stripping whitespace and converting to uppercase for consistent grouping and filtering.

Handling Missing Values: Applied dropna on critical date columns to ensure only valid transactional records are kept for the final report.

Column Selection: Filtered the dataset to focus on the top 33 essential features, reducing memory usage and clutter.

3. Advanced Error Correction & Logical Sorting
Fixing Excel Formula Errors: Identified #REF! errors in the "month" column and dynamically recalculated the correct month name by extracting it from the Date column using .dt.strftime('%b').

Chronological Sorting: Utilized pd.Categorical to force a logical calendar sequence (Mar, Apr, May...) instead of the default alphabetical sorting, ensuring accurate trend visualizations.

4. Smart Export Logic (Append vs. Create)
Persistence: Implemented a conditional export script using pd.ExcelWriter.

# Functionality: The script checks if final_net.xlsx exists. If so, it appends the new data to the next available row; otherwise, it creates a fresh file.

# Technical Stack
Python: Core logic and automation.

Pandas: Data manipulation and transformation.

Openpyxl: Engine for interacting with Excel workbooks and handling append modes.
