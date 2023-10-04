#### [CAT API](https://www.elastic.co/guide/en/elasticsearch/reference/current/cat.html)
Compact and Aligned Text(CAT) APIs

클러스터의 정보를 사람이 읽기 편한 형태로 출력하기 위한 용도로 만들어진 API

ui기반 모니터링 시스템이 원인 파악에 더 편하지만 cat API가 상황을 빠르게 판단하는데 더 도움이 되기 때문에 사용한다.

``` curl
GET /_cat/healt?v // verbose_
```
- cat health
	- elasticsearch 클러스터의 전반적인 상태를 파악할 수 있다.

| header name           | meaning                                   |
| --------------------- | ----------------------------------------- |
| cluster               | 클러스터 이름                             |
| status                | 클러스터 상태                             |
| node.total            | 총 노드 수                                |
| node.data             | 데이터 노드 수                            |
| shards                | 샤드 수                                   |
| pri                   | 프라이머리 샤드 수                        |
| relo                  | 재배치가 일어나고있는 샤드 개수           |
| init                  | 초기화중인 샤드 수                        |
| unassign              | 샤드 중 아직 노드에 배치되지 않은 샤드 수 |
| pending_tasks         | pending걸린 작업 수                       |
| max_task_wait_time    | 가장 오래 대기한 태스크의 대기시간        |
| active_shrads_percent | 전체 샤드중 active상태 샤드의 비율        |
|                       |                                           |

status
- green: 프라이머리 샤드, 레플리카 샤드 모두 정상적으로 각 노드에 배치되어 동작하고 있는 상태
- yellow: 프라이머리 샤드는 정상적으로 동작하지만 일부 레플리카 샤드가 정상적으로 배치되지 않은 상태
- red: 일부 프라이머리 샤드와 레플리카 샤드가 정상적으로 배치되지 않은 상태 색인 성능, 검색 성능에 모두 영향을 주며 문서 유실이 발생할 수 있다.

