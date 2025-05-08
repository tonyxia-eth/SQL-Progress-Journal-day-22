# SQL-Progress-Journal-day-22

# 📅 Day 22 – SQL Subqueries & HAVING Clauses

Today was a big one. I tackled advanced SQL concepts and finally wrapped my head around two key topics:

## ✅ What I Practiced
- Subqueries (SB): Selecting a value from a secondary query to use in a `WHERE` or `HAVING` clause.
- Filtering data based on:
  - `AVG()` subquery results
  - `MAX()` and `MIN()` salary comparisons
- Writing clean JOINs with table aliases (e.g., `players p`, `salaries s`)
- Switching from `WHERE` to `HAVING` when using `GROUP BY` and aggregate functions.
- Debugging errors from invalid aliases and subquery logic.

## 🧠 Key Concepts Reinforced
- Use `HAVING` when filtering aggregated results.
- Table aliases (e.g., `p`, `s`) help shorten queries and improve readability.
- You **must** use `HAVING` (not `WHERE`) to compare `SUM()`, `COUNT()`, `AVG()` results.
- Subqueries can be as simple as:
  ```sql
  salary > (SELECT AVG(salary) FROM salaries WHERE year = 2001)

SELECT teams.name, SUM(salaries.salary) AS total_salary
FROM teams
JOIN salaries ON teams.id = salaries.team_id
WHERE salaries.year = 2001
GROUP BY teams.name
HAVING total_salary > 10000000
ORDER BY total_salary DESC
LIMIT 10;

🧭 What's Next
Finish the final step of Task 7, which includes combining GROUP BY, HAVING, and subqueries to compare total team salaries against the average.

🧠 Confidence Note: This was tough at first, but I now understand subqueries and HAVING well enough to debug and write my own logic. Time to wrap up Task 7!
