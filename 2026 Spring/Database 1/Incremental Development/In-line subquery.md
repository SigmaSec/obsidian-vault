SELECT count(dept)
FROM(SELECT dept, avg(salary)
	FROM employees
	GROUP BY dept
	HAVING avg(salary) > 40000)
