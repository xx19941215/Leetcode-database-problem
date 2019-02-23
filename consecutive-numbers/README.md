### Description

Write a SQL query to find all numbers that appear at least three times consecutively.

| Id | Num |
|----|-----|
| 1  |  1  |
| 2  |  1  |
| 3  |  1  |
| 4  |  2  |
| 5  |  1  |
| 6  |  2  |
| 7  |  2  |

For example, given the above Logs table, 1 is the only number that appears consecutively for at least three times.

| ConsecutiveNums |
|-----------------|
| 1               |

### Solution

```sql
select distinct `l4`.`Num` as `ConsecutiveNums` from `Logs` `l1`, `Logs` `l2`, `Logs` `l3`, `Logs` `l4`
where `l1`.`Num` = `l2`.`Num` and 
`l2`.`Num` = `l3`.`Num`
and `l1`.`Id` + 1 = `l2`.`Id`
and `l2`.`Id` + 1 = `l3`.`Id`
and `l4`.`Id` in (`l1`.`Id`, `l2`.`Id`, `l3`.`Id`);
```

### Note

If you have a better solution, you can star and fork [Leetcode-database-problem](https://github.com/xx19941215/Leetcode-database-problem) then create a pull request.