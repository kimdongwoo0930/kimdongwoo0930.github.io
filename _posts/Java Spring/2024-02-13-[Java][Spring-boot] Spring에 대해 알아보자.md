---
date: 2024-02-13 10:00:00 +0900
categories: [Java / Spring-boot]
tags: [Java, Spring-boot, Spring]
---

## 스프링 프레임워크(Spring Framework)란

---

스프링을 사용하기전에 스프링 프레임워크가 무엇이고, 왜 사용하지는지 알아보자.

> ### Spring Framework
>
> 스프링 프레임워크는 Java 플랫폼을 위한 오픈소스 애플리케이션 프레임워크입니다.  
> 동적인 웹 사이트를 개발하기 위한 많은 서비스를 제공하고있고,  
> 우리나라 공공기간의 웹 서비스 개발에도 많이 사용되고 있는 전자정부 표준 프레임워크의 기반 기술로 사용되고 있다.

<br>

## 스프링 프레임워크 특징

---

- ### 스프링에는 3대 특징이 있다.
  - POJO를 기반으로 AOP, PSA, IoC/DI 등의 기술을 지원한다.

<br>

### 각각의 기술을 알아보자 ( 추후 수정 예정 )

- ### POJO(Plain Old Java Object)
  - 특정 기술에 종속되지 않는 순수한 자바 객체를 의미한다.
  - 스프링은 POJO를 사용하여 개발을 하기 때문에, 특정 기술에 종속되지 않는다.
  - 이러한 특징으로 인해, 스프링은 다른 프레임워크와 연동이 쉽다.
- ### AOP(Aspect Oriented Programming)
  - 관점 지향 프로그래밍이라고도 하며, 흩어진 관심사를 모듈화하여 효율적으로 개발할 수 있도록 도와주는 프로그래밍 기법이다.
  - 스프링은 AOP를 지원하여, 트랜잭션, 보안, 로깅 등의 관심사를 모듈화하여 개발할 수 있도록 도와준다.
  - 이러한 특징으로 인해, 코드의 중복을 줄이고, 유지보수성을 높일 수 있다.
- ### PSA(Portable Service Abstraction)
  - 서비스 추상화라고도 하며, 특정 기술에 종속되지 않도록 추상화된 인터페이스를 제공하는 것을 의미한다.
  - 스프링은 PSA를 지원하여, 특정 기술에 종속되지 않도록 추상화된 인터페이스를 제공한다.
  - 이러한 특징으로 인해, 특정 기술에 종속되지 않고, 유연한 코드를 작성할 수 있다.
- ### IoC(Inversion of Control) / DI(Dependency Injection)
  - 제어의 역전과 의존성 주입이라고도 하며, 객체간의 의존성을 외부에서 주입받는 것을 의미한다.
  - 스프링은 IoC/DI를 지원하여, 객체간의 의존성을 외부에서 주입받을 수 있도록 도와준다.
  - 이러한 특징으로 인해, 객체간의 결합도를 낮추고, 유연한 코드를 작성할 수 있다.

<br>

## Spring Framework의 MVC 패턴

![Alt text](<../../assets/img/Java Spring/SpringMvc.png>)

<br>

### Model

Model에서는 데이터처리를 담당합니다.  
Model부분은 비즈니스 로직을 처리하고, 데이터를 저장하고, 데이터를 가공하는 역할을 합니다.  
Model부분의 Service는 view에 종속적인 코드가 없어야 하고 View 부분이 변경되더라도 Service부분은 재사용할수 있어야 합니다.  
**Model에서는 View와 Controller에 대한 어떠한 정보도 알고 있어서는 안됩니다.**

<br>

### View

View부분은 사용자에게 보여지는 화면을 담당하고, 사용자의 요청을 Controller에 전달하는 역할을 합니다.  
**Model이 가지고 있는 정보를 저장해서는 안되며 Model의 정보를 가공해서도 안됩니다.**

<br>

### Controller

Controller부분은 사용자의 요청을 받아서 Model에게 전달하고,  
Model이 처리한 데이터를 View에게 전달하는 역할을 합니다.  
**Model과 View에 대한 정보를 알고 있어야 하며, Model과 View에 대한 정보를 가공해서는 안됩니다.**

<br>

## Spring Framework의 구조

![Alt text](<../../assets/img/Java Spring/SpringFramework.png>)

<br>

### Spring Framework의 구조는 크게 7가지로 나눌수 있습니다.

- #### Spring AOP
  - 스프링 AOP는 관점 지향 프로그래밍을 지원하는 모듈입니다.
  - 스프링 AOP는 트랜잭션, 보안, 로깅 등의 관심사를 모듈화하여 개발할 수 있도록 도와줍니다.
- #### Spring ORM
  - 스프링 ORM은 객체 관계 매핑을 지원하는 모듈입니다.
  - 스프링 ORM은 JPA, Hibernate, MyBatis 등의 ORM 프레임워크를 지원합니다.
- #### Spring Web
  - 스프링 Web은 웹 개발을 지원하는 모듈입니다.
  - 스프링 Web은 MVC, WebSocket, REST 등의 웹 개발을 지원합니다.
- #### Spring DAO
  - 스프링 DAO는 데이터 액세스 계층을 지원하는 모듈입니다.
  - 스프링 DAO는 JDBC, JPA, Hibernate, MyBatis 등의 데이터 액세스 기술을 지원합니다.
- #### Spring Context
  - 스프링 Context는 IoC/DI를 지원하는 모듈입니다.
  - 스프링 Context는 BeanFactory, ApplicationContext 등의 IoC/DI 컨테이너를 지원합니다.
- #### Spring Web MVC
  - 스프링 Web MVC는 웹 MVC를 지원하는 모듈입니다.
  - 스프링 Web MVC는 DispatcherServlet, HandlerMapping, Controller, ViewResolver 등의 웹 MVC 기술을 지원합니다.
- #### Spring Core
  - 스프링 Core는 스프링의 핵심 모듈입니다.
  - 스프링 Core는 IoC/DI, PSA, AOP 등의 핵심 기술을 지원합니다.
