### Description

Suppose that a website contains two tables, the Customers table and the Orders table. Write a SQL query to find all customers who never order anything.

Table: Customers.

| Id | Name  |
|----|-------|
| 1  | Joe   |
| 2  | Henry |
| 3  | Sam   |
| 4  | Max   |

Table: Orders.

| Id | CustomerId |
|----|------------|
| 1  | 3          |
| 2  | 1          |

Using the above tables as example, return the following:

| Customers |
|-----------|
| Henry     |
| Max       |

### Solution

```sql
select `Name` as `Customers` from `Customers`
where `Id` not in
(select `CustomerId` from `Orders`);
```

### Note

If you have a better solution, you can star and fork [Leetcode-database-problem](https://github.com/xx19941215/Leetcode-database-problem) then create a pull request.