### Description

Mary is a teacher in a middle school and she has a table seat storing students' names and their corresponding seat ids.

The column id is continuous increment.
Mary wants to change seats for the adjacent students.
Can you write a SQL query to output the result for Mary?

|    id   | student |
|---------|---------|
|    1    | Abbot   |
|    2    | Doris   |
|    3    | Emerson |
|    4    | Green   |
|    5    | Jeames  |

For the sample input, the output is:

|    id   | student |
|---------|---------|
|    1    | Doris   |
|    2    | Abbot   |
|    3    | Green   |
|    4    | Emerson |
|    5    | Jeames  |

Note:
If the number of students is odd, there is no need to change the last one's seat.

### Solution

```sql
select * from (
    select `id` + 1 as `id`, `student` from `seat`
    where `id`% 2 = 1 and `id` + 1 <= (select count(*) from `seat`)
    union
    select `id` - 1 as `id`, `student` from `seat`
    where `id`% 2 = 0
    union
    select `id`, `student` from `seat`
    where `id`% 2 = 1 and `id` + 1 > (select count(*) from `seat`)
) as `a` order by id;
```

### Note

If you have a better solution, you can star and fork [Leetcode-database-problem](https://github.com/xx19941215/Leetcode-database-problem) then create a pull request.