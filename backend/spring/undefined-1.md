# 배경



* 2004년: 스프링 프레임워크 V1 릴리즈
* 2009년: Jakarta Contexts & Dependency Injection(CDI) 소개

{% code overflow="wrap" %}
```
🔍 Spring 5 - Java EE 였지만, ㅇSpring 6+ & Spring Boot 3+ 는 오늘날의 자바 규격은 Jakarta EE(JSP, JSTL, EJB, JAX_RS, Validation, CDI, JPA)로 불립니다.

🔍 CDI는 구현부가 없는 인터페이스입니다. CDI를 사용하여 스프링 어노테이션 @Component -> @Named, @Autowired -> @Inject를 대체 할 수 있습니다.
```
{% endcode %}







_<mark style="background-color:yellow;">과거 스프링 환경 설정 및 빈을 등록했던 방법은 무엇이었을까?</mark>_

Java Spring XML은 Spring Framework의 초기 버전에서 사용되었던 설정 파일 형식입니다. Spring Framework는 Java에서 기반으로 하는 오픈소스 프레임워크로, 애플리케이션 개발을 위한 다양한 기능과 모듈을 제공합니다.

Spring Framework의 초기 버전에서는 Java 클래스를 사용하여 애플리케이션을 설정하였지만, 이는 복잡하고 유지보수가 어려워지는 문제가 있었습니다. 이에 따라 Spring Framework 2.0 버전부터 XML 기반의 설정 파일을 사용하게 되었습니다. XML은 태그 형식으로 구성되어 있으며, Spring Framework XML도 이와 같은 구조를 가지고 있습니다. XML 파일 안에는 스프링 빈 객체의 설정 정보가 담겨 있으며, 스프링 컨테이너는 이 파일을 읽어 빈 객체를 생성하고 관리합니다. 스프링 XML의 기본적인 사용법은 다음과 같습니다.

1. 스프링 설정 파일 생성
   * XML 파일을 생성하고 스프링 빈 객체를 정의합니다.
   * 스프링 빈 객체는 id와 class 속성을 필수로 가지며, 다양한 속성을 추가할 수 있습니다.
2. 스프링 설정 파일 로딩
   * 스프링 컨테이너는 스프링 설정 파일을 로딩하여 빈 객체를 생성하고 관리합니다.
   * 스프링 설정 파일을 로딩하기 위해서는 ClassPathXmlApplicationContext 클래스나 XmlWebApplicationContext 클래스를 사용합니다.
3.  빈 객체 사용

    * 스프링 컨테이너는 스프링 설정 파일에서 정의된 빈 객체를 생성하고, 빈 객체를 필요로 하는 클래스에서 DI(Dependency Injection)를 통해 주입합니다.
    * DI를 통해 주입된 빈 객체는 클래스 내에서 일반적인 객체와 동일하게 사용할 수 있습니다.



Spring Framework 3.0 버전 이후부터는 XML 설정 파일 대신 자바 어노테이션 기반의 설정 방식이 주로 사용되고 있습니다. 하지만 여전히 일부 프로젝트에서는 XML 설정 파일을 사용하고 있으며, 이를 이해하고 사용할 수 있는 것은 스프링 개발자로서 필수적인 역량 중 하나입니다.

