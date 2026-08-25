SQL supports principle of closure.
SELECT * from 
	(SELECT dep, avg(salary) as avsal
	From Employees
	Group by dept)
WHERE avsal > 50000
the intter produces a table with two columns: dept and avsal.
 the outer queries then queries that table to find rows where avsal is greater than 50000