# Excel-Based-Customer-Transaction-Analysis
Cleaned and transformed multi-month customer transaction data in Excel using formulas to extract structured info. Calculated key metrics like total and average spend per customer, categorized them via VLOOKUP, and built summary tables. Demonstrated strong skills in data cleaning, aggregation, and dashboard reporting.


Sheet1: Contains a pivot table showing the count of transactions by month for various customer IDs.

TASK 1 :Extract all the headers below from the data in column A. Please note that they are separated with"_". 
The data in COLUMN D-G contains all the Data you need to answer Task 2-Task 6>>>>>DO NOT USE TEXT TO COLUMN INSTEAD USE FORMULA TO EXTRACT
(a) Formular used : 

1 . =TRIM(LEFT(A4, FIND("_",A4) -1)) to extract the "CustomerId" seperated by delimetres from
Customer ID_Month & Year_Volume_tranx val
9b73-4682_43952_6_446718

2. =TEXT(TRIM(MID(A4,FIND("_",A4)+1,FIND("_",A4,FIND("_",A4)+1)-FIND("_",A4)-1)),"mmm-yyyy") to seperate the "Month & Year" using (_) as the delimeter
from Customer ID_Month & Year_Volume_tranx val
9b73-4682_43952_6_446718

3. =TRIM(MID(A4, FIND("_", A4, FIND("_", A4) + 1) + 1, FIND("_", A4, FIND("_", A4, FIND("_", A4) + 1) + 1) - FIND("_", A4, FIND("_", A4) + 1) - 1))
   to seperate the "Volume" using (_) as the delimeter from
   Customer ID_Month & Year_Volume_tranx val
    9b73-4682_43952_6_446718
.
5. =TRIM(MID(A4, FIND("_", A4, FIND("_", A4, FIND("_", A4) + 1) + 1) + 1, LEN(A4))) to seperate the "tranx val" using (_) as the delimeter from
   Customer ID_Month & Year_Volume_tranx val
     9b73-4682_43952_6_446718
   
TASK 2
       What is the total transaction Value for each of these customers in each month?
       Find the average for each customers across the 3 months? What is the Total sum for each customers across the 3months?				

  1. Contains raw transaction data, including customer IDs, dates, volumes, and transaction values using pivot table to get the sum and average volume of customers per month

TASK 3
    BASED ON THE AVERAGE VALUE YOU CALCULATED IN TASK 1, CLASSIFY EACH CUSTOMERS INTO THE DIFFERENT 4 CATEGORIES IN TASK 3. (To avoid spelling mistakes, reference the categories in task 3. DO NOT TYPE BEST CUSTOMER, GOOD CUSTOMER, AVERAGE CUSTOMER & POOR CUSTOMER).                                                                               If the customer average value is above 1.5million, BEST CUSTOMER. If the average value is between 1million and 1.5million, GOOD CUSTOMER. If the customer transaction value is less than 1million but above 500k, AVERAGE CUSTOMER. All customers from 500k and below are "POOR CUSTOMERS".	

  1. A simple list of store IDs extracted for potential lookups and references from the pivoted table ,
     Formular: =LOOKUP(N4, {0,0.5,1,1.5}, {"POOR CUSTOMER","AVERAGE CUSTOMER","GOOD CUSTOMER","BEST CUSTOMER"}) used to lookup based on the value and categorizing them into
     "POOR CUSTOMER","AVERAGE CUSTOMER","GOOD CUSTOMER","BEST CUSTOMER"

TASK 4
   How many customers from Task 2 fall into each category?	using the countif formular to know the number of customers that falls under the Best,Good, Average and Poor Customers
   
Formular used to count for the Best Customer - =COUNTIF(S4:S9344, "BEST CUSTOMER") 
Formular used to count for the Good Customer =COUNTIF(S4:S9344, "GOOD CUSTOMER")
Formular used to count for the Average Customer =COUNTIF(S4:S9344, "AVERAGE CUSTOMER")
Formular used to count for the Poor Customer =COUNTIF(S4:S9344, "POOR CUSTOMER")

TASK 5
     How many times did each of these customers did a transaction in each month?			
using pivot table to calculate and sort the volume per customer

TASK 6
    Using Vlookup, from Task 2, what category does the customer with the Customer ID ''1fc2-413a'' fall into?			
Formular Used =VLOOKUP(AG3, $R$4:$S$9344, 2,FALSE)








