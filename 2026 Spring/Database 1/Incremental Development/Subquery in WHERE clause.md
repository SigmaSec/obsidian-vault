SELECT lname, fname, phone, dept, salary
FROM employees
WHERE salary = (Select max(salary) as maxsal from employees)
