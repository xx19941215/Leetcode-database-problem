### Description

X city opened a new cinema, many people would like to go to this cinema. The cinema also gives out a poster indicating the movies’ ratings and descriptions.
Please write a SQL query to output movies with an odd numbered ID and a description that is not 'boring'. Order the result by rating.

For example, table cinema:

|   id    | movie     |  description |  rating   |
|---------|-----------|--------------|-----------|
|   1     | War       |   great 3D   |   8.9     |
|   2     | Science   |   fiction    |   8.5     |
|   3     | irish     |   boring     |   6.2     |
|   4     | Ice song  |   Fantacy    |   8.6     |
|   5     | House card|   Interesting|   9.1     |

For the example above, the output should be:

|   id    | movie     |  description |  rating   |
|---------|-----------|--------------|-----------|
|   5     | House card|   Interesting|   9.1     |
|   1     | War       |   great 3D   |   8.9     |


### Solution

```sql
select * from `cinema` where `id` % 2 = 1 and `description` != 'boring'
order by `rating` desc;
```

### Note

If you have a better solution, you can star and fork [Leetcode-database-problem](https://github.com/xx19941215/Leetcode-database-problem) then create a pull request.