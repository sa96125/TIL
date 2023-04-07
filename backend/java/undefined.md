# 배경

Java는 Oracle에서 개발 및 유지보수하는 <mark style="color:blue;">**객체지향 프로그래밍 언어**</mark>입니다. 1995년에 발표되어 현재까지도 많은 개발자들이 사용하고 있습니다. Write Once, Run Anywhere라는 특징을 가지고 있어서, 한번 작성한 코드를 다양한 운영체제 및 플랫폼에서 실행할 수 있습니다.

참고로 Java는 C++ 언어를 기반으로 하며, C++의 복잡성을 줄이고 개발자가 보다 쉽게 개발할 수 있도록 디자인되었습니다. Java는 Garbage Collection 기능을 제공하여 개발자가 메모리 관리를 할 필요가 없으며, 다양한 API와 라이브러리를 제공하여 개발을 보다 쉽게 할 수 있습니다. 자바 9버전 이후로는 6개월마다 기능이 업데이트 되고 있습니다. 이전에는 안정성 때문에 다양한 분야에서 사용되는 만큼 변화에 신중했지만, 이제는 최신기능을 적극적으로 수용하며 변화에 적극적이게 되었습니다. 낮은 버전을 사용할 수록 얼마나 안정적으로 운영할 것인지 선택할 수 있고 높은 버전을 사용할 수록 얼마나 새로운 기술을 도입할 것인지 선택자로 가늠할 수 있습니다.







_<mark style="background-color:yellow;">난 사실, 자바하면 오라클이 떠오르긴 하는데.. 누가 만들었을까요?</mark>_\
_<mark style="background-color:yellow;">뭐 만하면 Java 8! Java 8! Java 8이 뭔데, 왜 표준처럼 자리 잡은 걸까요?</mark>_

* 1991년: 제임스 고슬링(James Gosling)과 그의 동료들이 "Oak"이라는 이름의 객체지향 언어를 개발
* 1995년: Sun Microsystems에서 Oak 언어를 Java로 이름을 변경하고 발표
* 1996년: JDK 1.0(자바 개발 도구)이 출시
* 1997년: JDK 1.1이 출시
* 1998년: <mark style="color:blue;">**Java 2**</mark>(J2SE 1.2) 출시, J2SE(스탠다드), J2ME(마이크로), J2EE(엔터프라이즈)
* 2000년: J2SE 1.3이 출시
* 2004년: <mark style="color:blue;">**Java 5**</mark>(J2SE 1.5) 출시, 이 버전에서 제네릭스, 열거형, 애노테이션 등의 새로운 기능이 추가
* 2006년: Sun Microsystems에서 Java SE, Java EE, Java ME 등의 다양한 플랫폼을 발표
* 2009년: Oracle이 Sun Microsystems를 인수하면서 Java의 소유권이 Oracle로 이전
* 2011년: Java 7이 출시
* 2014년: <mark style="color:blue;">**Java 8**</mark>이 출시, 이 버전에서 람다 표현식, 스트림 API 등의 새로운 기능이 추가(핵심 기능)
* 2017년: Java 9가 출시, 이 버전에서 모듈 시스템이 추가







_<mark style="background-color:yellow;">현대 시대에는 무수한 컴퓨터프로그래밍 언어가 세상에 존재합니다.</mark>_ \
_<mark style="background-color:yellow;">그렇다면, 수 많은 언어중 자바를 사용하는 이유는 무엇 일까요?</mark>_

**첫 번째, 다양한 분야에서 사용되고 있다.**

* 서버 프로그래밍\
  Java는 멀티스레드를 지원하고, 안정성과 확장성이 높은 언어로서 서버 프로그래밍에서 많이 사용됩니다. 대표적인 예로는 Spring Framework, Apache Struts 등이 있습니다.
* 모바일 애플리케이션\
  Java는 안드로이드(Andriod) 운영체제에서 사용되는 기본 언어 중 하나입니다. 안드로이드 스튜디오와 Java를 함께 사용하여 안드로이드 애플리케이션을 개발할 수 있습니다.
* 게임\
  Java는 게임 개발 도구로 많이 사용되며, Minecraft 등 대표적인 게임이 Java로 개발되었습니다.
* 웹 애플리케이션\
  Java는 대규모의 사용자에게 안정적으로 서비스를 제공할 수 있는 언어입니다. JSP(JavaServer Pages), Servlet, Struts 등을 사용하여 웹 애플리케이션을 개발할 수 있습니다.
* 인공지능(AI)\
  Java는 인공지능 분야에서도 사용됩니다. Weka, Deeplearning4j 등 Java 기반의 인공지능 프레임워크가 있으며, Java는 R, Python 등의 다른 인기있는 언어와 함께 사용되기도 합니다.



**두 번째, 20년 동안 사랑 받는 프로그래밍 언어이다.**

2022년 TIOBE 프로그래밍 언어 지수에 따른, 상위 10개 프로그래밍 언어 중 Java는 2위에 랭크되어 있는 것을 확인 할 수 있습니다. TIOBE INDEX 순위는 인기 있는 언어들의 검색 빈도, 개발자 수, 코드량, 커뮤니티 활동 등을 종합적으로 평가하여 산출된 지수입니다. 프로그래밍 언어의 사용과 인기는 항상 변화하고 있습니다. 근 20년 동안 상위에 렝크 되어 왔으며, 배우기 쉽고 풍부한 학습자료를 가지고 있습니다.



**세 번째, 모던 프로그래밍 언어이다.**

Java는 주로 객체 지향 언어(Object-Oriented Programming, OOP)로 알려져 있지만, Java 8부터 함수형 프로그래밍(Functional Programming, FP)을 지원하도록 업그레이드 되었습니다. 따라서 Java는 OOP와 FP 모두를 지원하는 다중 패러다임 언어(Multi-Paradigm Programming Language)로 분류됩니다.

Java 8부터는 람다 표현식(Lambda Expressions)과 스트림(Streams) API를 도입하여 함수형 프로그래밍의 기본적인 개념인 일급 함수(First-Class Function), 고차 함수(Higher-Order Function), 순수 함수(Pure Function) 등을 지원합니다. 이러한 함수형 프로그래밍의 기능은 Java 9, 10, 11 등의 버전에서도 추가적으로 지원되고 있습니다.

하지만, Java는 여전히 객체 지향 언어의 특징인 캡슐화(Encapsulation), 상속(Inheritance), 다형성(Polymorphism) 등을 중요하게 다루고 있습니다. 따라서, <mark style="color:blue;">**Java는 OOP를 기본으로 하는 언어이지만, FP를 지원하는 다중 패러다임 언어**</mark>이기도 합니다.



**마지막으로, 대규모 시스템에서 안정적이다.**&#x20;

* 가비지 컬렉션\
  Java는 가비지 컬렉션 기능을 제공하여 <mark style="color:blue;">**메모리 관리를 자동으로 처리**</mark>합니다. 따라서 개발자가 직접 메모리를 할당하고 해제할 필요가 없으며, 메모리 누수(Memory Leak) 문제를 방지할 수 있습니다.
* 멀티스레드 지원\
  Java는 멀티스레드를 지원하여 <mark style="color:blue;">**여러 작업을 동시에 처리**</mark>할 수 있습니다. 이를 통해 대규모 트래픽 처리나 병렬 처리 등을 효과적으로 수행할 수 있습니다.
* 예외 처리(Exception Handling) 기능\
  Java는 예외 처리 기능을 지원하여 예외 상황을 미리 예측하고 처리할 수 있습니다. 이를 통해 안정성이 높은 프로그램을 개발할 수 있습니다.
* 플랫폼 독립성(Platform Independence)\
  Java는 <mark style="color:blue;">**플랫폼 독립적**</mark>인 특성을 갖습니다. 즉, Java로 작성된 프로그램은 운영체제나 하드웨어 종속성이 없으며, 어떤 플랫폼에서도 실행될 수 있습니다. 이를 통해 대규모의 사용자들이 사용하는 다양한 환경에서 안정적으로 동작할 수 있습니다. 자바 언어가 플랫폼에 독립적인 이유는 자바 프로그램이 실행되는 가상 컴퓨터(또는 소프트웨어), 자바 가상 머신 JVM 위에서 동작하기 때문입니다. 일반적으로 각기 다른 운영체제에서 동작하게 만들려면 코드를 각 운영체제에서 사용할 수 있도록 수정해야하지만, 자바로 작성된 코드는 각 운영체제에서 사용가능한 JVM을 설치하면 되므로 소스코드를 직접적으로 수정할 필요가 없습니다.
* 개방형(Open) 표준\
  Java는 개방형 표준(Open Standard)인 Java Community Process(JCP)를 통해 새로운 기술 및 개발 방법을 지속적으로 개선하고, 다양한 개발자와 기업이 참여할 수 있습니다. 이를 통해 높은 수준의 안정성과 개발 생산성을 유지할 수 있습니다.

