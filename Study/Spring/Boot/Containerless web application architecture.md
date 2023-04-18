
Serverless와 유사한 의미를 가지는데..

WebContainer는 web component를 관리해주는데 서버가 실행되는 동안 web component가 정상동작되도록 관리한다.

여러개의 web component를 관리할 수 있음

web client로부터 들어온 web request를 어떤 web component가 요청을 처리할 수 있는지 결정하고 전달하는지(routing, mapping) 판단한다.

web component == servlet
web container == servlet container

spring도 container인데 servlet container 뒷단에 존재하며 servlet을 통해 웹에서 들어온 요청을 container가 관리하는 bean중에서 해당 요청을 처리할 수 있는 bean에게 전달한다. (이과정에서 여러 bean들 간에 협력이 있음)

servlet container를 사용해야하는데 servlet container를 설치하고 관리하는데 너무 수고가 많으니까 이러한
servlet container 없이 spring을 개발할 수 있도록 하면 좋겠다.
==standalone application==
