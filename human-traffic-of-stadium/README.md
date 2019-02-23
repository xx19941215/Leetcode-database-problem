### Description
X city built a new stadium, each day many people visit it and the stats are saved as these columns: id, date, people

Please write a query to display the records which have 3 or more consecutive rows and the amount of people more than 100(inclusive).

For example, the table stadium:

| id   | date       | people    |
|------|------------|-----------|
| 1    | 2017-01-01 | 10        |
| 2    | 2017-01-02 | 109       |
| 3    | 2017-01-03 | 150       |
| 4    | 2017-01-04 | 99        |
| 5    | 2017-01-05 | 145       |
| 6    | 2017-01-06 | 1455      |
| 7    | 2017-01-07 | 199       |
| 8    | 2017-01-08 | 188       |

For the sample data above, the output is:

| id   | date       | people    |
|------|------------|-----------|
| 5    | 2017-01-05 | 145       |
| 6    | 2017-01-06 | 1455      |
| 7    | 2017-01-07 | 199       |
| 8    | 2017-01-08 | 188       |

Note:
Each day only have one row record, and the dates are increasing with id increasing.

### Solution

```sql
select distinct `s4`.* from `stadium` `s1`, `stadium` `s2`, `stadium` `s3`, `stadium` `s4`
where `s1`.`people` >= 100
and `s2`.`people` >= 100
and `s3`.`people` >= 100
and `s1`.`id` + 1 = `s2`.`id`
and `s2`.`id` + 1 = `s3`.`id`
and `s4`.`id` in (`s1`.`id`, `s2`.`id`, `s3`.`id`);;
```

### Note

If you have a better solution, you can star and fork [Leetcode-database-problem](https://github.com/xx19941215/Leetcode-database-problem) then create a pull request.