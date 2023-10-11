스프링에서 [WebSocketMessageBrokerConfigurer](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/socket/config/annotation/WebSocketMessageBrokerConfigurer.html#configureClientInboundChannel-org.springframework.messaging.simp.config.ChannelRegistration-) 구현하게되면 제공된 메서드를 구현할 수 있는데
websocket client로부터 전달받은 메시지를 처리하기 위한 inbound message channel에 대한 설정을 할 수 있다.

문서에 따르면 configureClientInboundChannel은 