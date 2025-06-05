# EL_Task6

1. Setting the Database

CODE: 
use exel;

Meaning: This tells the SQL system to use the "exel" database for all upcoming queries.

2. select Query

These are used to retrieve data from a table.

CODE:
select * from online_sales_data;

Meaning: Get all columns and all rows from the online_sales_data table. The result includes:

Transaction_ID, Date, Product_Category, Product_Name, Units_Sold, Unit_Price, Total_Revenue, Region, Payment_Method

3. extract Query

This query is used to extract a specific data.

CODE:
select extract(year from Date) as year from online_sales_data;

Here we are extracting the year from the Date column as year from the online_sales_data.

4. group by month

Here we will extract the month from the Date column as a month and group by with other columns.

CODE:
select extract(month from Date)as month,sum(units_sold)as Total_Sales, count(product_category) as Product_Category from online_sales_data group by month;

We will group by the extracted month column with sum of Units_Sold as Total_Sales and count of Product_Category as Product_Category from the online_sales_data.

5. Use sum() for revenue

Sum funtion is used to get sum of a numeric column.

CODE:
select sum(total_revenue) from online_sales_data;

Here we are using the sum() for getting the sum of Total_Revenue for Revenue of the Sales.

6. count(distinct order_id) for volume

Here  we are using the Transaction_ID instead of order_id.

count function is used to count the values of a categorical column.

The distinct in a count function is used to getting the count of unique values in a categorical column.

CODE:
select count(distinct transaction_id) from online_sales_data;

The result of this code is 240.
It shows that we have the 240 unique Transaction_ID

7. Use order by for sorting

Here we are using the order by for sorting the data by any numeric value.

Example:

Query 1. 

If we use only order by it arrage the data in an ascending order.

CODE:
select  product_category, units_sold from online_sales_data order by units_sold;

In this we are getting two columns 1-Product_Category and 2-Units_Sold from the online_sales_data and sorting it by using order by in Units_Sold.

It will arrange the resulted table in an ascending order.

Query 2.

If we will use the desc along with the order by it will sort the data in descending order.

CODE:
select product_category, unit_price,date from online_sales_data order by unit_price desc;

In this we are getting two columns 1-Product_Category and 2-Unit_Price from the online_sales_data and sorting it by using order by in Unit_Price.
