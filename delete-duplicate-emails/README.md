### Description

Write a SQL query to delete all duplicate email entries in a table named Person, keeping only unique emails based on its smallest Id.

| Id | Email            |
|----|------------------|
| 1  | john@example.com |
| 2  | bob@example.com  |
| 3  | john@example.com |

Id is the primary key column for this table.
For example, after running your query, the above Person table should have the following rows:

| Id | Email            |
|----|------------------|
| 1  | john@example.com |
| 2  | bob@example.com  |

Note:

Your output is the whole Person table after executing your sql. Use delete statement.

### Solution

```sql
delete `p1` from `Person` `p1`, `Person` `p2` where
`p1`.`Email` = `p2`.`Email`
and `p1`.`Id` > `p2`.`Id`;
```

### Note

If you have a better solution, you can star and fork [Leetcode-database-problem](https://github.com/xx19941215/Leetcode-database-problem) then create a pull request.