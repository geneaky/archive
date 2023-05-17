
[MySQL Docs](https://dev.mysql.com/doc/refman/8.0/en/innodb-consistent-read.html)

InnoDB가 multi versioning을 통해 특정 시점의 데이터베이스 스냅샷을 표현하는 것을 consistent read라고 하는데 
쿼리는 커밋되거 전의 시점은 확인하고 이후의 변화나 커밋되지 않은 트랜잭션의 변경사항은 확인하지 않는다.


