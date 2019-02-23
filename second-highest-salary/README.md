### Description

Write a SQL query to get the second highest salary from the Employee table.

| Id | Salary |
|----|--------|
| 1  | 100    |
| 2  | 200    |
| 3  | 300    |

For example, given the above Employee table, the query should return 200 as the second highest salary. If there is no second highest salary, then the query should return null.

| SecondHighestSalary |
|---------------------|
| 200                 |

### Solution

```sql
select ifnull((
    select distinct `Salary` from `Employee` order by `Salary` desc limit 1,1
), null) as SecondHighestSalary;
```

### Note

If you have a better solution, you can star and fork [Leetcode-database-problem](https://github.com/xx19941215/Leetcode-database-problem) then create a pull request.