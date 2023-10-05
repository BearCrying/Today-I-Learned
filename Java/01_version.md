# 특정 자바 버전을 학습해야 하는가?

- 결론부터 말하면, 12,17과 같은 특정 java의 버전만을 학습할 필요는 없다
- 다른언어 E.g. Pyton과 같이 릴리스 사이에 심각한 문제가 있는 것과 달리
JAVA의 경우 하위 호환성이 매우 높기 때문이다
    - 예를들어 java 8의 프로그램은 java 8~17 가상 머신에서 실행되도록 보장이 된다.
- 그러므로 java 8의 기능들로 토대를 쌓고, java 9~17의 추가된 기능에 대해 알아보고 사용하면 문제 될 것이 없다!

# Java Distribution

- JDK 다운로드를 제공하는 다양한 사이트가 있으며, “:누가 어떤 라이선스로 무엇을 제공” 하는지가 불분명함

## OpenJDK 프로젝트

- Java 소스 코드의 경우 OpenJDK 프로젝트 사이트에 존재하는 유일한 소스코드
- 그러나 이것은 소스코드일 뿐 배포 가능한 빌드가 아님
    - 이론적으로, 해당 소스코드로 빌드를 만들 수 있다.
    - 예를 들어 ttJDK라고 부르며 배포하기 시작 가능
    - 하지만 합법적으로 자바 SE 호환이라고 부를 수 있는 우리의 배포판은 인증이 부족할 것
- 이러한 이유로 실제로 이러한 빌드를 만들고 인증을 받은 후 배포하는 벤더가 많지 않다.

## OpenJDK 빌드 및 OracleJDK 빌드

- 자바를 소스에서 빌드하는 벤더 중 하나가 오라클이다.
- Oracle JDK는 유료 이지만, OpenJDK는 오픈소스기반
- Oracle JDK의 라이선스는 Oracle BCL(Bianry Code License) Agrreement이지만, OpenJDK의 라이선스는 Oracle GPL v2
- Oracle JDK는 LTS(장기 지원) 업데이트를 지원 받을 수 있지만, OpenJDK는 LTS 없이 6개월 마다 새로운 버전이 배포된다.
- Oracle JDK는 Oracle이 인수한 Sun Microsystems 플러그인을 제공하지만, OpenJDK는 제공하지 않음
- Oracle JDK는 OpenJDK 보다 CPU 사용량과 메모리 사용량이 적고, 응답시간이 높다.

⇒ JAVA 8 이전 OpenJDK 빌드와 OracleJDK 빌드 사이에는 실제 소스 차이가 존재했는데, 최신의 두 버전은 본질적으로 동일하며 약간의 차이만 존재한다.

# JAVA 8-11 특징

## JAVA 8
- java 8은 대규모 릴리스여서 모든내용을 정리하긴 힘들다
주요 기능
- Lambada
- stream
- interface default method
- Optional
- new Date and Time API(LocalDateTime, …)

## JAVA 9
- 모듈 시스템의 등장
- 컬렉션
    - list, set, map을 쉽게 구성할 수 있는 몇 가지 추가 기능
- 스트림
    - takeWhile, dropWhile, iterate 메서드의 형태로 몇가지 추가 기능
- Optional
    - resentOrElse 추가 기능
- 인터페이스
    - 인터페이스에 private method 사용 가능

## JAVA 10
- 가비지 컬렉션
- var 키워드 추가
- 병렬 처리 가비지 컬렉션 도입으로 인한 성능 향상
- JVM 힙 영역을 시스템 메모리가 아닌 다른 종류의 메모리에도 할당 가능

## JAVA 11
- Oracle JDK와 OpenJDK 통합
- Oracle JDK가 구독형 유료 모델로 전환
- 서드파티 JDK 로의 이전 필요
- lambda 지역변수 사용법 변경
- 람다 표
