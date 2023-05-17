[MySQL Docs](https://dev.mysql.com/doc/refman/8.0/en/innodb-locks-set.html)

locking read, update, delete는 일반적으로 레코드 락이 걸린다.
row을 제외하는 구문이 where 조건이 있는것은 상관없이 index range scan을 함

lock은 일반적으로 next key lock인데 `gap` 공간에 insert를 막는다.
