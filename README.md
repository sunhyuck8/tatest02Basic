# Spring Security Basic Project Study

이 문서는 Spring Security 학습 과정에서 코드 변경사항을 추적하고 분석하기 위한 README 파일입니다.

## 📋 프로젝트 개요

- **프로젝트명**: ratest02-basic
- **목적**: Spring Security의 기본 개념 및 설정 학습
- **Java 버전**: 17
- **Spring Boot 버전**: 3.4.3

## 🔧 주요 기술 스택

- Spring Boot 3.4.3
- Spring Security
- Spring Web
- Gradle 빌드 시스템

## 📁 프로젝트 구조

```
src
└── main
    └── java
        └── io.security.oauth2.ratest02basic
            ├── Ratest02BasicApplication.java     # 메인 애플리케이션 클래스
            ├── SecurityConfig.java               # 보안 설정 클래스
            └── CustomSecurityConfiguerer.java    # 커스텀 보안 설정 (현재 주석 처리됨)
```

## 📝 코드 변경 로그

### 1. 초기 설정 (Current)

현재 프로젝트는 Spring Security의 기본 설정만 포함하고 있습니다.

#### SecurityConfig.java
- `@EnableWebSecurity` 및 `@Configuration` 어노테이션을 사용하여 보안 설정
- 기본 보안 필터 체인 구성:
  - `/login` 경로는 모든 사용자에게 허용
  - 그 외 모든 요청은 인증 필요
  - Form 로그인 및 HTTP Basic 인증 활성화
  - 예외 처리 부분은 주석 처리됨 (향후 활성화 예정)

#### CustomSecurityConfiguerer.java
- 현재 전체 클래스가 주석 처리되어 있음
- 향후 구현 예정인 커스텀 보안 설정 클래스
- `AbstractHttpConfigurer`를 확장하여 구현:
  - `init()` 및 `configure()` 메서드 오버라이드
  - 플래그에 따라 HTTP 보안 설정 분기 처리

## 📚 학습 포인트

### Spring Security 기본 설정
- SecurityFilterChain 빈 설정 방법
- HttpSecurity 설정 사용법:
  - authorizeHttpRequests(): 요청별 접근 제어
  - formLogin(): 폼 로그인 설정
  - httpBasic(): HTTP Basic 인증 설정

### 주석 처리된 코드에서 배울 점
- ExceptionHandling 설정 방법
- 커스텀 EntryPoint 구현 방법 (인증 실패 시 처리)

### CustomSecurityConfiguerer (향후 구현 예정)
- AbstractHttpConfigurer 확장 방법
- init() 및 configure() 메서드의 역할
- 조건부 보안 설정 구현 방법

## 🔄 다음 작업 예정

1. 주석 처리된 ExceptionHandling 코드 활성화
2. CustomSecurityConfiguerer 구현 완료 및 적용
3. 사용자 인증 로직 추가
4. 권한 기반 접근 제어 구현

## 📌 참고 링크

- [Spring Security 공식 문서](https://docs.spring.io/spring-security/reference/index.html)
- [Spring Boot and OAuth2](https://spring.io/guides/tutorials/spring-boot-oauth2/)
- [Securing a Web Application](https://spring.io/guides/gs/securing-web/)
