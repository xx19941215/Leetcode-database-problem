### Description
Write a SQL query to get the nth highest salary from the Employee table.

| Id | Salary |
|----|--------|
| 1  | 100    |
| 2  | 200    |
| 3  | 300    |

For example, given the above Employee table, the nth highest salary where n = 2 is 200. If there is no nth highest salary, then the query should return null.

| getNthHighestSalary(2) |
|------------------------|
| 200                    |

### Solution

```sql

BEGIN
declare m int;
set m = n - 1;
  RETURN (
      # Write your MySQL query statement below.
      select ifnull(
          (select distinct `Salary` from `Employee` order by `Salary` desc limit m,1)
          , null) as `getNthHighestSalary`
      
  );
END
```

### Note

If you have a better solution, you can star and fork [Leetcode-database-problem](https://github.com/xx19941215/Leetcode-database-problem) then create a pull request.