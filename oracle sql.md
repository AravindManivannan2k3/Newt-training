-- Section 1: Database Basics
CREATE DATABASE warehouse_db;
USE warehouse_db;
DESCRIBE inventory;

-- Section 2: Single Table Queries
SELECT first_name, last_name, salary 
FROM employees 
WHERE salary >= 50000 AND dept_id = 10 
ORDER BY salary DESC;

-- Section 4: Single Table Exercises
SELECT name, price 
FROM products 
WHERE category IN ('Electronics', 'Hardware') 
  AND price BETWEEN 100 AND 500
  AND stock_qty > 0;

-- Section 6: Single Row Functions
SELECT 
    CONCAT(UPPER(last_name), ', ', first_name) AS full_name,
    ROUND(salary / 12, 2) AS monthly_pay,
    COALESCE(bonus, 0) AS actual_bonus,
    SUBSTR(email, 1, INSTR(email, '@') - 1) AS username
FROM staff;

-- Section 8: Grouping Functions
SELECT 
    dept_id, 
    COUNT(*) AS total_staff,
    AVG(salary) AS avg_dept_pay,
    SUM(salary) AS total_budget
FROM employees 
GROUP BY dept_id 
HAVING COUNT(*) > 2;

-- Section 10: Multi-Table Queries and Joins
SELECT e.name, d.dept_name, l.city
FROM employees e
INNER JOIN departments d ON e.dept_id = d.id
LEFT JOIN locations l ON d.loc_id = l.id;

-- Section 11: Subqueries
SELECT name, salary 
FROM employees 
WHERE salary > (SELECT AVG(salary) FROM employees)
  AND dept_id IN (SELECT id FROM departments WHERE region = 'North');

-- Section 12: Analytical Functions (Window)
SELECT 
    name, 
    salary,
    RANK() OVER (ORDER BY salary DESC) as rank_desc,
    SUM(salary) OVER (PARTITION BY dept_id) as dept_total_spend,
    AVG(salary) OVER (PARTITION BY dept_id ORDER BY hire_date) as rolling_dept_avg
FROM employees;

-- Section 13: Self Join
SELECT e.name AS worker, m.name AS manager
FROM staff e
JOIN staff m ON e.manager_id = m.emp_id
WHERE e.hire_date < m.hire_date;

-- Section 14: Creating, Altering, and Updating
CREATE TABLE clients (
    client_id INT PRIMARY KEY,
    company_name VARCHAR(100) NOT NULL,
    active_status BOOLEAN DEFAULT TRUE
);
ALTER TABLE clients ADD COLUMN contact_email VARCHAR(255);
UPDATE clients SET active_status = FALSE WHERE client_id = 501;
DELETE FROM clients WHERE company_name IS NULL;
