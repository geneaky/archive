#### [CAT API](https://www.elastic.co/guide/en/elasticsearch/reference/current/cat.html)
Compact and Aligned Text(CAT) APIs

클러스터의 정보를 사람이 읽기 편한 형태로 출력하기 위한 용도로 만들어진 API

ui기반 모니터링 시스템이 원인 파악에 더 편하지만 cat API가 상황을 빠르게 판단하는데 더 도움이 되기 때문에 사용한다.

``` curl
GET /_cat/healt?v // ver_
```
- cat health
	- elasticsearch 클러스터의 전반적인 상태를 파악할 수 있다.