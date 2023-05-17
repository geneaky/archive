[MySQL Docs](https://dev.mysql.com/doc/refman/8.0/en/innodb-locks-set.html)

locking read, update, delete는 일반적으로 레코드 락이 걸린다.
row을 제외하는 구문이 where 조건이 있는것은 상관없이 index range scan을 함

lock은 일반적으로 next key lock인데 `gap` 공간에 insert를 막는다.

격리레벨이 `serializable`이 아니면 일반적으로 일관된 읽기로 동작을 하는데 serializable level에서는 
검색같은 경우 shared next-key lock을 인덱스 레코드에 건다. 
하나의 인덱스 레코드 락이 구문의  필요한 정보인데 그 구문에서 unique row을 검색하기 위한 unique index에 잠금을 건다.

select for update나 select for share 구문의 경우 유니크 인덱스를 사용하여 row를 스캔하기 위해 락을 취득한다.

