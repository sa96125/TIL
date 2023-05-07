# 코어

_<mark style="background-color:yellow;">Tight coupling and Loose coupling?</mark>_

결합도는 좋은 소프트웨어를 만드는데 매우 중요한 개념입니다. 이는 소프트웨어 컴포넌트나 모듈 내부의 요소들이 얼마나 밀접하게 연결되어 있는지를 말합니다. 높은 결합도는 한 요소의 변경이 다른 요소에 큰 영향을 미치는 것을 의미합니다. 반면에 낮은 결합도는 한 요소의 변경이 다른 요소에 미치는 영향이 적다는 것을 의미합니다.



결합도는 실제 생활과 큰 연관이 있습니다. 예시를 한번 들어볼게요.

* 자동차에서 엔진은 매우 중요한 부품으로 조립하기가 어렵습니다. 반면에 바퀴는 매우 쉽게 붙였다 뗄 수 있습니다.
* 노트북은 장소구분없이 들고 다닐 수 있지만, 데스크탑은 그럴 수 없습니다.



&#x20;개발을 하면 알겠지만, 비지니스에도 변화가 있을 수 있고 프레임 워크, 코드등 모든 것이 변경될 수 있습니다. <mark style="color:blue;">가능한 코드를 적게 변경하면서 기능을 변경</mark>할 수 있어야합니다. 왜냐하면 모듈의 내부 구성 요소가 서로 강하게 결합되어 있으면 코드를 이해하거나 수정하기 어렵고 유지보수가 어려워집니다. 따라서 가능한 느슨한 결합을 사용해야합니다.&#x20;



자바에서는 인터페이스를 사용하여 강한 결합을 느슨한 결합으로 만들 수 있습니다. 인터페이스를 중간에 넣음으로서 각 모듈의 의존성을 하나로 만들어 독립적으로 변경할 수 있게 됩니다.







_<mark style="background-color:yellow;">Dependency Injection</mark>_

의존성 주입이란 클래스간 의존성을 연결하는 행위를 말합니다.&#x20;

```java
// Object creation
var game = new PacmanGame();

// Object creation + Wiring of dependencies
// game is a dependency of gameRunner
var gameRunner = new GameRunner(game);
```







_<mark style="background-color:yellow;">대규모 어플리케이션의 경우, 수천개의 의존성이 생성되며 필요한 곳에 주입됩니다. 이러한 행동을 일일히 수동으로 하는 것보다, Spring 프레임워크에게 위임할 수 없을 까요?</mark>_

@Configuration , @Bean을 통해 스프링에게 위임할 수 있습니다.&#x20;

스프링에서 관리하는 일(자바 객체 : Spring Bean)들을 정의하는 클래스를 Configuration Class라고 합니다.

```java
// 1. Launch Spring Context.
// 2. Configure the things that Spring frameworks to manage.
var context = new AnnotaionConfigApplicationContext(configuration.class)
System.out.println(context.getBean(""))
```







_<mark style="background-color:yellow;">IOC Container?</mark>_ \
_<mark style="background-color:yellow;">Spring Container vs Spring Context vs IOC Container vs Application Context?</mark>_

<mark style="color:blue;">스프링 컨테이너는 Spring Beans와 Life cycle를 관리</mark>합니다. 즉 애플리케이션의 객체 생성과 관리를 자동화하는 도구입니다. 미리 정의한 자바클래스(POJOs)들과 환경설정(config)들을 인풋으로 받아 스프링 프레임워크 런타임 시스템을 구성합니다. 객체를 생성하고 필요한 객체에 자동으로 의존성을 주입하기 때문에 개발자가 객체 간의 의존성을 직접 관리할 필요가 없습니다 :)

{% code overflow="wrap" %}
```
🔍 IOC(제어의 역전)는 프로그래밍에서의 제어 흐름에 대한 개념입니다. 일반적으로 객체지향 프로그래밍에서는 객체 간의 관계를 직접 코드로 구현합니다. 이러한 경우 객체가 다른 객체를 생성하거나, 다른 객체의 메서드를 호출하는 등의 제어 흐름이 객체 내부에 결합되어 있습니다. 하지만 제어의 역전은 이러한 객체 간의 결합도를 낮추기 위해, 객체 간의 관계를 외부에서 결정하도록 하는 것을 의미합니다. 즉, 객체가 자신이 사용할 객체를 직접 생성하거나 관리하지 않고, 이를 외부에 위임하는 것입니다. 이를 통해 객체 간의 결합도가 낮아지므로 유지보수와 테스트가 더 쉬워지는 장점이 있습니다.
```
{% endcode %}







_<mark style="background-color:yellow;">Bean Factory vs Application Context?</mark>_

스프링 컨테이너의 유형은 2가지로 나뉠 수 있습니다. Bean Factory는 디폴트 스프링 컨테이너를 말하고 Application Context는 엔터프라이즈급에서 다룰 수 있는 고급 기능을 포함하는 스프링 컨테이너 입니다.

{% code overflow="wrap" %}
```
🔍 현대적인 웹 어플리케이션의 경우, AOP등 고급 기능을 사용하므로 Application Context를 자주 사용합니다. 웹 어플리케이션, 웹 서비스, Restful API, 마이크로 서비스에서 사용할 수 있습니다. Bean factory를 사용하는 경우는 메모리 사용에 극심한 제약이 있는 IoT 앱뿐입니다.
```
{% endcode %}







&#x20;_<mark style="background-color:yellow;">POJOs vs Java Bean vs Spring Bean?</mark>_

Java Bean(EJB) : 3가지 제약을 준수하는 클래스

* public no-args constructor
* getter, setter
* serializable

POJOs : 아무 제약이 없는 일반적으로 흔히 사용하는 기본 자바 객체

Spring Bean : IOC Container가 관리하는 모든 객체







_<mark style="background-color:yellow;">스프링 컨테이너가 관리하는 객체 모두 출력하는 방법?</mark>_

```java
Array.stream(context.getBeanDefinitionNames())
    .forEach(System.out::println)
```







_<mark style="background-color:yellow;">AutoWiring?</mark>_\
_<mark style="background-color:yellow;">매칭 된 스프링민이 여러개일 경우?</mark>_

* @Primary  : 우선적으로 자동 연결
* @Qualifier : 강제적으로 수동 연결







_<mark style="background-color:yellow;">지금까지는 의존성이 필요하다면 개발자가 직접 @Bean을 등록했었습니다.</mark>_\
_<mark style="background-color:yellow;">스프링이 자동으로 객체를 생성해서 의존성을 주입할 수는 없을까요?</mark>_

작성되었던 @Bean을 삭제하고 @Component를 추가하여 스프링이 자동생성할 수 있도록 변경하였습니다.

```java
// in @Configuration class
// @Bean
// public game() {
//    return new PackmanGame()
// }

@Bean
public gameRunner(GamingConsle game) {
    return new GameRunner(game);
}

// in POJOs
@Component
public class PackmanGame() implements GamingConsle {
    // ...
}
```



하지만, NoSearchBeanDefinitionException 발생합니다. 스프링이 정의된 컴포넌트를 찾을 수 없기때문에 발생하는 문제입니다. 따라서 @ComponentScan 을 추가하여 해당 위치를 알려주어 문제를 해결합니다.

```java
@Configuration
@ComponentScan("path:package")
```



수동으로 객체를 생성하지 않고 스프링 프레임워크가 자동으로 생성해줄 수 있습니다. 이를 통해 상당량의 코드를 줄일 수 있게 됩니다. <mark style="color:blue;">스프링은 @Bean을 통해 객체를 관리하고 @AutoWiring을 수행할 뿐아니라 @Component와 @ComponentScan을 통해 필요한 객체를 패키지에서 찾고 객체를 생성하여 전체 애플리케이션을 정상적으로 작동시켜 줍니다.</mark>

