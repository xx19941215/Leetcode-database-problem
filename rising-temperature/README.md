### Description

Given a Weather table, write a SQL query to find all dates' Ids with higher temperature compared to its previous (yesterday's) dates.

| Id(INT) | RecordDate(DATE) | Temperature(INT) |
|---------|------------------|------------------|
|       1 |       2015-01-01 |               10 |
|       2 |       2015-01-02 |               25 |
|       3 |       2015-01-03 |               20 |
|       4 |       2015-01-04 |               30 |

For example, return the following Ids for the above Weather table:

| Id |
|----|
|  2 |
|  4 |

### Solution

```sql
select `w2`.`Id` from `Weather` `w1`, `Weather` `w2`
where datediff(`w2`.`RecordDate`, `w1`.`RecordDate`) = 1
and `w2`.`Temperature` > `w1`.`Temperature`;
```

### Note

If you have a better solution, you can star and fork [Leetcode-database-problem](https://github.com/xx19941215/Leetcode-database-problem) then create a pull request.