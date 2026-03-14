Cover image for Demystifying SQL Joins & Window Functions
EditManageStats
Edwin Omondi 
Edwin Omondi
Posted on 14 Mar

Demystifying SQL Joins & Window Functions
#
sql
#
database
#
datascience
#
productivity
1. SQL Joins
The Structure Query Language (SQL) Join is a command clause that combines records from two or more tables in database. It is a means of combining data fields from two tables by using values common to each table.

If you work with databases, you'll likely need to use SQL Joins to retrieve data from multiple tables at some point in your work. These impactful clauses allow you to get information from separate tables so that you get the right information you need to make the best possible decision.

What is a Join in Sql?
In Structure Query Language (SQL), a Join is used to connect two or more records within a relational database. As their name suggests, relational databases organize data based on pre-established relationships, which define how data contained in one table relates to data contained within another (or several others).

 
Fig.1.0

The Join clause retrieves data from related tables in a database. Because it retrieves data from multiple tables, however, the SQL Join clause is more complex than a simple query that retrieves data from a single table.

Types of Sql Joins
There are many different use cases for SQL Joins, and they are crucial when mapping out relationships between tables in your database.

There are four primary types of SQL Joins that you can use: Inner Join, Left Outer Join, Right Outer Join, and Full Outer Join. Explore these four types of JOINs along with some sample SQL Join clauses below:

a) Inner Join
Inner Joins combine two tables based on a shared key. For example, if you have a table with a column called "user id" and each user id is unique to each user, this you could join that table to another table with a "user id" column to find the information associated with each user. This example shows how to use an Inner JOIN clause to join two tables

 

Fig 1.1

An Inner Join returns only the rows that have matching values in both tables.

SELECT c.first_name, c.last_name
FROM assignment.customers c
JOIN assignment.sales s
ON c.customer_id = s.customer_id;

 
Fig 1.2

b) Left Outer Join
Left Outer Joins return all rows from the first table and only the rows in the second table that match.

 
Fig 1.3

A Left Join returns all rows from the left table and the matched rows from the right table. If there is no match, NULL values are returned for columns from the right table.
For example, we would use the previous syntax that joins the ‘film’ and ‘film_category’ tables. However, this time, we would make two changes. First, we would use a left join instead of an inner join. Second, we would exclude the first three rows from the ‘film_category’ table.

 

 
Fig 1.4

The result clearly conveys that there are null values in the first three category_id entries. This is because the first three rows in the ‘film_category’ table are excluded before the left join occurs

c) Right Outer Join
Right Joins are logically the opposite of Left Joins—they return all rows from the second table, and only the rows in the first table that match

 
Fig 1.5

A RIGHT JOIN returns all rows from the right table and the matched rows from the left table. If there is no match, NULL values are returned for columns from the left table.
For example, we would use the previous syntax. However, this time, we would make two changes. First, we would use a right join instead of a left join.

d) Full Join
Full Joins combine both left and right joins by returning all rows from both tables, as long as there is at least one match between them

2. Window Functions
Window functions, also known as windowing or analytic functions, are a category of functions in SQL that perform calculations across a specified range of rows related to the current row within a result set. These functions operate on a “window” of rows defined by an OVER() clause. Window functions are often used in conjunction with the ORDER BY clause to define the window.

Now, let’s look at some common window functions

SQL Aggregate functions
SQL Aggregate Functions allow summarizing large sets of data into meaningful results, making it easier to analyze patterns and trends across many records. They return a single output value after processing multiple rows in a table.

Perform calculations like totals, averages, minimum or maximum values on data.
Ignore NULL values in most functions except COUNT(*), improving result accuracy.
Work with clauses such as GROUP BY, HAVING and ORDER BY for analysis.
Example: First, we create a demo SQL database and table, on which we use the Aggregate functions.

Aggregate Functions in SQL
Below are the most frequently used aggregate functions in SQL.

a). Count()
It is used to count the number of rows in a table. It helps summarize data by giving the total number of entries. It can be used in different ways depending on what you want to count:

COUNT(*): Counts all rows.
COUNT(column_name): Counts non-NULL values in the specified column.
COUNT(DISTINCT column_name): Counts unique non-NULL values in the column.
Query:

COUNT(*) returns the total number of rows in the table, including rows with NULL values.
COUNT(Salary) counts only the rows where Salary is not NULL.
COUNT(DISTINCT Salary) counts unique non-NULL salary values, ignoring duplicates.

b). SUM()
It is used to calculate the total of a numeric column. It adds up all non-NULL values in that column for Example, SUM(column_name) returns sum of all non-NULL values in the specified column.

SUM(Salary) adds all non-NULL salary values to get the total salary amount.
SUM(DISTINCT Salary) adds only unique non-NULL salary values, avoiding duplicates.
NULL values are ignored in both SUM calculations.

c). AVG()
It is used to calculate average value of a numeric column. It divides sum of all non-NULL values by the number of non-NULL rows for Example, AVG(column_name) returns average of all non-NULL values in the specified column.

AVG(Salary) calculates the average of all non-NULL salary values.
AVG(DISTINCT Salary) computes the average only from unique non-NULL salary values.
Both ignore NULL values when performing the calculation.

d). MIN() and MAX()
The MIN() and MAX() functions return the smallest and largest values, respectively, from a column.

MAX(Salary) returns the highest non-NULL salary value from the Employee table.
MIN(Salary) returns the lowest non-NULL salary value from the Employee table.
Both functions ignore NULL values while determining the result.