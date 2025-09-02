# Skills Used

- Python (Juypter Notebook, Pandas, Numpy, Faker)
- Power BI (Power Query, Power BI Desktop, Data Modeling, Data Visualization)
- Data Storytelling

# Process
## Create sample data with python
I cannot use enterprise inbound sales data for a public portfolio project, so I created my own random sample data.
1) made agent table (explain hierarchy)
2) added calls and sales (explain randomization process)


# Import data into Power BI with Power Query
I needed to do a small bit of work to recreate the star/data warehouse schema from the CSV files.
1) Duplicate the CALL + SALES table to split them into their 2 respective tables, like they would be in an enterprise.
2) Calculate integer fields where necessary from the percentage fields, then remove them.  As we will be aggregating dynamically in Power BI, we only needed the percentage fields to help realistically randomize the data in the CSV.
3) Remove any columns no longer required

# Setup the Power BI Data Model
1) Ensure the Employee ID on our DIM__Agents table is related correctly to the fact tables.
2) Use CALENDARAUTO() with ADDCOLUMNS() to create a DIM_Dates table based on our randomly generated data's dates.  Relate this date key to the fact date keys.
3) Ensure the default aggregations are set up how we want them in the data model. Ex: We will never sum a month number or primary key.
