Derived Columns
Creating a new column that is a combination of existing columns is known as a derived column (or "calculated" or "computed" column). Usually, you want to give a name, or "alias," to your new column using the AS keyword.

This derived column, and its alias, are generally only temporary, existing just for the duration of your query. The next time you run a query and access this table, the new column will not be there.

If you are deriving the new column from existing columns using a mathematical expression, then these familiar mathematical operators will be useful:

* (Multiplication)
+ (Addition)
- (Subtraction)
/ (Division)
Consider this example:

SELECT id, (standard_amt_usd/total_amt_usd)*100 AS std_percent, total_amt_usd
FROM orders
LIMIT 10;
Here we divide the standard paper dollar amount by the total order amount to find the standard paper percent for the order, and use the AS keyword to name this new column "std_percent." You can run this query on the next page if you'd like, to see the output.

Order of Operations
Remember PEMDAS from math class to help remember the order of operations? If not, check out this link on operations(opens in a new tab) as a reminder. The same order of operations applies when using arithmetic operators in SQL.

The following two statements have very different end results:

standard_qty / standard_qty + gloss_qty + poster_qty
standard_qty / (standard_qty + gloss_qty + poster_qty)
It is likely that you mean to do the calculation as written in statement number 2!

Code from the Video
SELECT account_id,
       occurred_at,
       standard_qty,
       gloss_qty + poster_qty AS nonstandard_qty
FROM orders
Below is the workspace where you can write the query. Click on the EVALUATE button at the bottom of the workspace once you have written the query.
