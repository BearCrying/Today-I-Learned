# Spring의 등장배경

- Spring이 등장하기 이전 EJB(Enterprise JavaBeans)는 어플리케이션의 업무 로직을 담당하는 표준 기술이였다.
- EJB의 등장으로 개발자는 비즈니스 로직에 집중 할 수 있는 환경을갖추었지만, 하나의 기능을 구현하기 위해, 클래스 간 상속 인터페이스의 구현 등 각 클래스간의 의존도가 커짐으로써 문제가 발생했다.
- 이로인해 마틴 파울러가 EJB에 반발하여 오래된 방식의 간단한 자바 오브젝트로 돌아가자는 말을 했고 이는 POJO(Plain Old Java Object)란느 용어의 기원이 되었다.

### EJB의 불편함을 통해 대표적으로 2가지의 오픈소스가 등장한다.

1. 로드 존슨의 J2EE Design and Development의 예제 코드들이 지금의 Spring 기본 코드가 되었다.
2. 개빈 킹의 하이버네이트 ORM(Object Relation Mapping)  프레임워크의 등장
   - EJB 엔티티 빈 기술을 대체하고, JPA의 새로운 표준 정의
   - JPA는 표준 인터페이스, 하이버네이트는 JPA의 구현체

### 2002년 로드 존슨이 EJB의 문제점을 지적하며 고품질 확장 가능한 애플리케이션을 개발 할 수 있음을 보여줌

- 30,000라인 이상의 기반 기술 예제코드를 선보이면서 시작됨
- 이 에제 코드에는 현재 스프링의 핵심 개념과 기반 코드인 BeanFactory, ApplicationContext, POJO, IoC(제어의 역전), DI(의존성 주입)등이 포함되었다.
- 이 책의 출간 이후 유겐휠러와 얀 카로프가 오픈소스 프로젝트를 제안하고 이후 지금까지 핵심 코드는 유겐 휠러가 개발하고 있다.

### 2003년 스프링 프레임워크 1.0 출시 이후 현재까지도 유겐 휠러가 개발하고 있음

# Spring Version

## Spring 3.2.x

→ 2016.12.31일 부로 개발 및 지원이 종료되었다.

- Spring 3.0부터 Java 5가 지원이 된다. 기존에 유지하던 하위호환성에 Generic이나 가변인자등과 같은 개선사항이 ㅈ추가되었다.
    - 이로인해 BeanFactory 등 핵심 API가 업데이트 되었다.
- 전체 프레임워크를 하나의 spring.jar 파일로 제공하던 부분을 여러개의 jar 파일로 나누어 제공한다.
    - e.g. spring-core / spring-web 등
- SPEL(Spring Expression Language)가 도입되었다.
    - XML 및 Annotation 기반 Bean 정의에서 사용할 수 있게 되었고, 외부 프로퍼티 파일이나 환경 변수에서 값을 가져오기 쉬워졌다.
- REST API에 대한 지워니 추가되었다.
    - 서버로서는 기존 MVC Framework 레벨에서 Annotation 기반 확장이 추가되었다.
    - 클라이언트로서는 RestTemplate을 추가해 지원한다.
- OXM(Object XML Mapping) 기능이 추가되어 설정을 XML 형태로 할 수 있게 지원한다.
- @Configuration,@Bean 등의 Java Annotation을 이용해서 직접 메타 데이터를 설정하고, DI 지원이 가능하다.
- H2가 지원되었다.
- @Async 주석을 통하여 비동기 메서드 호출을 지원했다.

## Spirng 4.x

→ 20년 12월 31일부로 개발 및 지원이 종료되었다.

- 기존에 사용하지 않지만 호환성을 위해 남겨져있던 Deprecated Package들이 제거되었다.
- Hibernate 3.6이상 EhChche 2.1 이상, Groovy 1.8 이상, Joda-Time 2.0이상 새로운 Dependency들에 대해 지원한다.
- Java 6,7,8의 고유 기능들에 대해 지원한다.
    - 람다식, Optional, Callback Interface 등의 기능을 Spring Framework 레벨에서 사용할 수 있다.
- Java EE 6,7에 대해 고려되어 있다. JPA 2.0과 Servlet 3.0에 대한 지원이 포함되어있다는 뜻
- Groovy DSL 이용한 외부 Bean 설정이 가능하다.
- Core 컨테이너들의 기능 지원이 확대되었다.
    - DI 시에 Generic이 지원된다.
    - Repository가 쉽게 Inject될 수 있으며, 각종 Metadat Anotation들을 이용한 Custom Annotation 작성이 가능하다.
- Bean 관리가 용이해졌다.
    - @Lazy를 이용한 Lazy Injection이나 @Order를 통한 Ordered Interface, @Profile을 통한 프로필 버전 관리가 쉬워졌다.
- Web을 개발하기 위한 도구들이 생겼다.
    - @ResController 사용이 가능하다.
    - Web Socket이나 SockJS, STOMP등의 라이브러리 및 프로토콜을 같이 지원한다.
    - Web Socket : 커넥션을 연결한 상태에서 양방향 통신을 할 수 있는 TCP/IP 기반의 프로토콜
    - SockJS : WebSocket을 지원하지 않는 브라우저에서도 WebSocket과 같은 통신 방법을 제공하기 위한 라이브러리
    - STOMP : WebSocket을 이용한 pub-sub 기반의 메시징 프로토콜
- Test 환경이 객선되었다.
    - @ContextConfiguration, @WebAppConfiguration, @ContextHierarchy, @ActiveProfiles 와 같은 spring-text에 있는 Annotation들을 meta-annotation으로 사용할 수 있게 되었다.
    - Framework 레벨에서 Mock을 위한 ServletContext를 별도로 지원한다.

### Spring 4.1

- JMS(Java Message Service)
    - JavaConfig로 설정할 수 있는 부분이 증가했다.
    - JmsListener로 listen를 간편하게 추가 가능하다.
    - Spring Messaging abstraction이 JMS를 지원하기 시작했다.
- Chching 기능이 향상되었다.
    - CacheResolver를 사용해 캐시를 런타입에 결정하는 것이 가능해졌다.
    - @CacheConfig를 이용해 annotation 레벨에서의 공통 세팅이 활성화 되었다.
    - cache resolver, cache manager, key generator 등의 커스터마이징이 가능하다.
- @RequestParam, @RequestHeader, @MatrixVariable에 Optional 사용이 가능하다.
- ResponseEntity가 builder 형식의 API를 제공한다.
    - e.g. ResponseEntity.ok()

### Spring 4.2

- @Bean 이 default method를 감지한다.
- @Import 로 @Configuration class 나 @Component class를 임포트 할 수 있다.
- @Order 로 @Configuration class 가 로딩되는 순서 설정이 가능하다.
- annotation attribute를 위한 @AliasFor를 제공한다.

### Spring 4.3

- Java 8 기능을 완전히 지원하기 시작
- Starter Pack.이 생겨서 POM 설정을 도와준다.
- Groovy를 통한 Bean 설정이 가능하다.
- 생성자 주입시 @Autowired 키워드를 생략할 수 있다.
- @Configuration 에서 생성자 주입을 지원한다.
- @Scheduled, @Schedules를 metat-annotation으로 사용 가능하다.
- @Cacheable의 sync 속석ㅇ을 통한 동시성을 지원한다.
- @RequestMapping의 다양한 형태를 제공한다.
    - GET, POST, PUT, DELETE, PATCH 등
- @PathVariable Optional 사용이 가능하다.
- MvcExceptionHandler에 지속적인 혹은 커스텀 에러 처리가 가능한다.

### Spring 5.0

- Java 8 버전이 기본으로 설정되고, Java EE 7 API 이상 사용이 가능하다.
    - JDK 9와도 호환이 가능하다.
- Java 8이 기본이 되면서 코어 스프링 인터페이스들이 디폴트 메서드 기반의 선택적 정의를 제공한다
- @Nullable, @NotNull annotation을 사용해서 명시적으로 nullable 인자를 표시하고 값을 얻어올 수 있다.
- 컴파일 타임에 널값을 다룰 수 있게 되었다.
- spring-jcl 이라는 공통 로깅 브릿지 모듈이 추가되었다.
- Core Contatinerㄹ에 후보 컴포넌트 인덱스 기능이 추가되었다.
    - classpath 기반의 component 스캔을 대체할 수 있다.
- Spring WebFlux가 추가되었다. (Reactive Programming 모델)
- Kotlin을 사용한 함수형 프로그래밍이 가능하다.
- Junit 5의 Jupiter를 지원한다.
- TestContext Framework를 통한 병렬 테스트 실행이 가능하다.
- Reqctive programming model을 위해 spring-test에 webtestClient가 포함되었다.

  

  # **Impressions.**

- 스프링의 탄생 배경과, 버전 별 차이점들에 대해 알게 되었다.
- 이를 공부하게 된 이유는 내가 프로젝트를 할 때, 버전을 찾는 근거를 만들고 싶어서 였는데 스프링버전에 있어서는 아무래도 현재는 5.x 버전을 계속해서 사용하게 될 것 같다. 그럼에도, 스프링부트, java 버전을 선택할 때에 함께 참고해서 결정하는 역할은 할 것 같다.
- EJB라는 기술이 자바의 겨울이라는 문학적인 이름을 가지고 있었고, Spring이 이제 자바의 봄이 왔다는 표현이라는 것에 개발자 갬성..? 을 느낄 수 있었다ㅋㅋㅋ..
- 앞으로 JAVA 버전 및 springboot 버전도 정리해봐야겠다.

