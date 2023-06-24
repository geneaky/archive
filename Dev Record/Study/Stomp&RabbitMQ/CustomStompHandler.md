
stomp conenction을 맺을 클라이언트와의 갑작스러운 연결 종료(에: 갑작스런 네트워크 단절)시 
현재 사용자의 연결 상태를 db에 가지고있고 그 정보로 notification을 보내기위한 처리를 하기 위해
기존 stompsubprotocolhandler를 확장해서 connection end time에 세션에서 사용자 정보를 가져와서
업데이트하는 방향으로 처리를 진행했다.

구독 라우터를 별도로 분리해서 구독 라우터에서 채팅방 connection status를 관리
