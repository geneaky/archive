데이베이스 성능, 장애상황을 대비해서 master, slave db를 사용하는 경우 spring에서 datasource를 2개 등록해야하는데 data 접근 기술로 jpa와 mybatis를 둘 다 사용하는 경우 트랜잭션의 관리는 어떻게 해야할지 고민이된다.

2개의 transaction manager를 각각 등록하는 경우? 

ex)


jpa와 mybatis 둘 다 platformtransactionmanager를 구현하는 transaction manager를 사용하기 때문에 jpa용 transaction manager 하나를 등록해서 사용해보았다.

##### mybatis

