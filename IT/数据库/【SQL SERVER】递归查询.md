

[【SQL SERVER】递归查询_MoFe1的博客-CSDN博客](https://blog.csdn.net/MoFe1/article/details/124429245)

```sql
with temp as(
	select * from [T] where id = 1
    union all
    select a.* from [T] a inner join temp on a.patientId = temp.id
)
select * from temp
```
