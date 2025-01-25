
Postgress 

MySql

Mongo

Different ways to delete duplicate rows in emp table

```sql
with empCte (ID, FirstName, LastNAme,Country, rankVal, denseRank,rowNumber)
AS
(
  select ID, FirstName, LastNAme,Country, rank() over(partition by FirstName, LastNAme,Country order by id) as rankVal,
  dense_rank() over(partition by FirstName, LastNAme,Country order by id) as denseRank,
  row_number() over(partition by FirstName, LastNAme,Country order by id) as rowNumber
  from EmployeeDup
)
select * from empCte where rankVal > 1 order by id
```

Different ways to find nth highest salary

```sql
select * from (
SELECT emp_name, emp_salary, DENSE_RANK() OVER( ORDER BY emp_salary desc) as r from empSal
) as rootEmp
where r = 2

SELECT emp_name, emp_salary, RANK() OVER(ORDER BY emp_salary desc) as r from empSal

SELECT * from empSal Order by emp_salary desc 
offset 2 rows fetch next 1 rows only
```


Row_number vs rank vs dense_rank
Top selling products
https://medium.com/@LoriLu/whats-the-difference-rank-vs-dense-rank-vs-row-number-3aca5ecfb928

```sql
with cteSales(rank,denseRank,rowNumber,product_price,items_sold, revenue)
as(
select 
rank() over(order by product_price * items_sold desc) as rank,
dense_rank() over(order by product_price * items_sold desc) as denseRank,
row_number() over(order by product_price * items_sold desc) as rowNumber,
product_price, items_sold, product_price * items_sold as revenue
from ProductSales
)
select * from cteSales
```


Why Stored procedure is can't be called from a function?

Difference among index scan, index seek, table scan
https://medium.com/silenttech/table-scan-vs-index-scan-vs-index-seek-f5cbb4e93478

CTE vs temp table

