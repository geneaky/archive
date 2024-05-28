###### runtimeOnly, compileOnly, implementation, api

gradle에서 프로젝트 의존성을 관리할때 사용하는 속성으로 compileClasspath, runtimeClasspath가 있는데

compileClasspath는 프로젝트 소스 코드를 컴파일할때 필요한 모든 클래스 파일과 라이브러리를 포함해, 이건 컴파일할때만 필요한 의존성이고 런타임시에 필요한게 아니야 그래서 이런 의존성은 빌드 결과물에 포함되지 않아.

runtimeClasspath는 프로젝트를 실행할 때 필요한 모든 클래스 파일과 라이브러리를 포함해, 즉 빌드 결과물에 포함이 되는거지
일반적으로 compileClasspath에는 runtimeClasspath에 포함되는 대부분의 의존성이 포함되어 있다 <- 이부분은 이해를 잘 못했네 컴파일시에 필요한 의존성이 interface이고 그 구현체중하나 runtimeClasspah