
spring container의 관리하는 빈은 크게  애플리케이션 빈과 컨테이너 인프라스트럭처 빈으로 구분이된다.

애플리케이션 빈은 개발자가 명시적으로 구성정보를 제공한 빈
컨테이너 인프라스트럭 빈은 스프링 컨테이너 자신이거나, 스프링 컨테이너를 확장하기 위한 빈

애플리케이션 빈은 다시 애플리케이션 로직(핵심 비즈니스 로직 관련) 빈과 애플리케이션 인프라스트럭처 빈으로 구분할 수 있음


스프링부트에서 애플리케이션 빈은 사용자 구성정보로, 컨테이너 인프라스트럭처 빈은 자동 구성정보로 구분을 한다


@Configuration의 proxyBeanMethods()가 default값인 true로 설정되어 있을 때는 클래스를 bean으로 
등록할때 해당 클래스가 직접 bean으로 등록되는 것이 아니라 proxy가 bean으로 등록된다. 
bean을 생성할때 의존하는 bean이 여러 bean에서도 의존성 주입이 되는 경우라면 default값으로 사용해도 무방하지만 그게 아니라 등록하는 bean이 어떠한 의존성이 없거나 의존하는 bean이 해당 bean과의 의존성만 가지고 있다고 굳이 proxy bean으로 등록할 필요없이 바로 객체를 bean으로 등록해도되기 때문에 false로 지정해도된다.

spring container에서 bean으로 등록된 오브젝트는 bean name이 부여가되는데  기본적으로 method명이 bean의 이름으로 따라간다 

import selector를 사용해서 자동 구성 configuration class를 로딩하는 방식으로 먼저 user 구성 정보를 로딩한 이후에  자동 구성정보를 로딩하기 위함이다.
-> user 구성 정보에서 우선적으로 등록된 bean이 없을시에 자동 구성정보에서 로딩을 하게된다. 

