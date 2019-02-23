### Description
The Employee table holds all employees. Every employee has an Id, and there is also a column for the department Id.

| Id | Name  | Salary | DepartmentId |
|----|-------|--------|--------------|
| 1  | Joe   | 70000  | 1            |
| 2  | Henry | 80000  | 2            |
| 3  | Sam   | 60000  | 2            |
| 4  | Max   | 90000  | 1            |
| 5  | Janet | 69000  | 1            |
| 6  | Randy | 85000  | 1            |

The Department table holds all departments of the company.

| Id | Name     |
|----|----------|
| 1  | IT       |
| 2  | Sales    |

Write a SQL query to find employees who earn the top three salaries in each of the department. For the above tables, your SQL query should return the following rows.

| Department | Employee | Salary |
|------------|----------|--------|
| IT         | Max      | 90000  |
| IT         | Randy    | 85000  |
| IT         | Joe      | 70000  |
| Sales      | Henry    | 80000  |
| Sales      | Sam      | 60000  |

### Solution

```sql
select `d`.`Name` as `Department`, `e1`.`Name` as `Employee`, `e1`.`Salary` from `Employee` `e1`,
`Employee` `e2`, `Department` `d`
where `e1`.`DepartmentId` = `e2`.`DepartmentId`
and `e1`.`Salary` <= `e2`.`Salary`
and `d`.`Id` = `e1`.`DepartmentId`
group by `e1`.`Id`
having count(distinct `e2`.`Salary`) <= 3
order by `Department`, `Salary` desc;;
```

### Note

If you have a better solution, you can star and fork [Leetcode-database-problem](https://github.com/xx19941215/Leetcode-database-problem) then create a pull request.