1.문제상황 파악
2.원인 분석
3.해결


###### 문제 상황 파악
1. 모니터링 알람 확인
2. 클러스터 상태 확인
3. 노드에서 에러 로그 확인
4. 클라이언트에서 에러 로그 확인

###### 원인 분석
1. 주요 지표 살펴보기
2. 에러 로그 분석

###### 문제 해결
1. 원인 분석을 통해 확인한 원인을 제거하는 과정 진행


# 사례 분석

###### 사례 1. 클러스터의 상태가 green이 아닌 경우

인덱스들 중 누가 yellow, red인지 파악한다.
인덱스들 중 어떤 샤드에 문제가 생겼는지 파악한다.(장애의 범위 파악)


###### 사례 2. 클러스터 문서 색인이 되지 않는경우 ( 403 forbidden)

Disk Usage가 꽉 찾을때

ELS 노드의 디스크 사용량이 100%가 되면 노드의 운영 체제도 정상 동작하지 않기 때문에 ELS에는 디스크 사용량이 일정 수준 이상이 되면 더 이상 색인 하지 않도록 보호하는 장치가 있다.
`cluster.routing.allocation.disk.thredhold_enabled` : 보호장치를 사용 여부 설정
`cluster.routing.allocation.disk.watermark.low` : 기본값 85%, 이 값보다 높아지면 더이상 샤드를 배치하지 않는다.
`cluster.routing.allocation.disk.watermark.high` : 기본값 90%, 이 값보다 높아지면 샤드를 다른 데이터 노드로 옮기기 시작한다.
`cluster.routing.allocation.disk.watermark.flood_stage` : 기본값 95%, 이 값보다 높아지면 더이상 색인 하지 않는다.