---
date: 2024-02-13 10:00:00 +0900
categories: [Java / Spring-boot]
tags: [Java, Spring-boot, Spring]
---

# 프로젝트 시작하기

---

### 스프링 부트 프로젝트를 생성하는 방법에는

- Spring Initializr를 이용한 방법
- IDE를 이용한 방법

이 두가지 방법이 있다.
처음 프로젝트를 생성할때는 Spring Initializr를 이용한 방법을 추천한다.

- **하지만 IntelliJ IDEA Ultimate 버전을 사용하고 있다면 IDE를 이용한 방법도 가능하다.**

글쓴이 본인도 IntelliJ IDEA Ultimate 버전을 사용하고 있기 때문에, IntelliJ 에서 프로젝트를 생성하는 방법을 알아보자.

<br>

# IntelliJ IDEA에서 프로젝트 생성하기

1. #### IntelliJ IDEA를 실행하고, Create New Project를 클릭한다.

   ![Alt text](<../../assets/img/Java Spring/create_project.png>)
   <br>

2. #### New Project에서 Spring Initializr를 선택하고, 프로젝트 정보를 입력한 후 Next를 클릭한다.

   ![Alt text](<../../assets/img/Java Spring/project_setting.png>)

3. #### 그 후 사용할 의존성을 추가한 후 Finish를 클릭한다.

   - 여기서는 Spring Web, Lombok, Spring Data JPA, MySql Driver을 많이 사용하기 때문에 추가 해준 후 Create를 클릭한다.

4. ##### 프로젝트가 생성되면, src/main/java에 Application.java 파일이 생성된 것을 확인할 수 있다.

   ![Alt text](<../../assets/img/Java Spring/project_structure.png>)

5. ##### Application.java 파일을 실행하면, 스프링 부트 프로젝트가 실행된다.

<br>

---

- **이렇게 프로젝트를 생성하면 Spring initializr를 이용하는 방법보다 쉽게 프로젝트를 생성할 수 있다.**

#### 다음 포스팅에서는 스프링 부트 컨트롤러를 만들어보는 방법에 대해 알아보자.

<br>
