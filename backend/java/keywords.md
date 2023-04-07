# keywords

<details>

<summary>package?</summary>

Java 패키지는 Java 클래스를 논리적으로 그룹화하는 방법입니다. 패키지는 클래스와 인터페이스를 조직적으로 정리하여 관리하기 쉽게 합니다. 패키지는 도메인 이름을 역순으로 나열하여 지정하며, 각 패키지는 하나 이상의 클래스나 서브 패키지를 포함할 수 있습니다.



Java 패키지는 `package` 키워드를 사용하여 선언됩니다. 예를 들어, `com.example.packageName` 패키지에 있는 `MyClass` 클래스를 선언하려면 다음과 같이 코드를 작성할 수 있습니다.



```java
package com.example.packageName;

public class MyClass {
    // 클래스 구현 내용
}
```



Java 패키지는 다른 패키지의 클래스를 사용할 수 있습니다. 이를 위해서는 `import` 키워드를 사용하여 다른 패키지의 클래스를 가져와야 합니다. 예를 들어, `com.example.anotherPackage` 패키지에 있는 `AnotherClass` 클래스를 사용하려면, 다음과 같이 `import` 구문을 작성합니다.



```java
package com.example.packageName;

import com.example.anotherPackage.AnotherClass;

public class MyClass {
    public void myMethod() {
        // AnotherClass의 인스턴스 생성 및 사용
        AnotherClass ac = new AnotherClass();
        ac.doSomething();
    }
}
```

</details>

<details>

<summary>class?</summary>

자바 프로그램의 기본 단위입니다. 클래스는 객체의 상태(state)와 행위(behavior)를 정의하며, 이를 이용하여 객체를 생성할 수 있습니다. 즉, 실행할 코드를 작성합니다. 코드 작성자가 원하는 개념을 정리/구현하는 곳이라 말할 수 있습니다. 최소 하나 이상으로 구성될 수 있습니다.

</details>

<details>

<summary>javac.exe?</summary>

`javac.exe`는 Java 컴파일러입니다. Java 컴파일러는 Java 소스 코드 파일(.java)을 컴파일하여 바이트 코드 파일(.class)을 생성하는 도구입니다.

```sh
# JVM가 이해 할 수 있는 기계어(.class)로 변환
# 이 과정에서 디버깅 할 수 있음
jongseungMac > javac Hello.java
```

`.class`는 Java 바이트 코드 파일의 확장자입니다. Java 컴파일러(`javac`)는 Java 소스 코드 파일(`.java`)을 컴파일하여 이진 형식으로 된 바이트 코드 파일(`.class`)을 생성합니다. 이러한 바이트 코드 파일은 Java 가상 머신(JVM)에서 실행됩니다.

`.class` 파일은 Java 클래스 파일, 인터페이스 파일, 혹은 에노테이션 파일 등의 형태가 될 수 있습니다. 이 파일들은 Java 애플리케이션을 구성하는 기본 단위입니다.

`.class` 파일은 이진 형식으로 되어 있으며, 특정 JVM에서 실행되는 바이트 코드로 구성됩니다. 이러한 구조는 Java 애플리케이션의 이식성(portability)과 보안성(security)을 높이는 데 도움을 줍니다. 또한, `.class` 파일은 컴파일러나 빌드 도구 등 다양한 도구들에서 사용되며, 이를 이용하여 Java 애플리케이션을 개발하고 실행할 수 있습니다.

</details>

<details>

<summary></summary>

&#x20;일ㅂ

```sh
 
```

</details>

**java.exe?**

`java.exe` 는 Java 인터프리터입니다.  Java 프로그램(.class)를 실행하는 도구 입니다.

```sh
# java 프로그램(.class) 실행
jongseungMac > java Hello  
```





**Build와 Compile?**

<mark style="color:blue;">**컴파일(Compile)은 소스 코드를 기계어로 변환하는 과정**</mark>입니다. 즉, 소스 코드를 작성한 개발자가 이해할 수 있는 고수준의 언어를 컴퓨터가 이해할 수 있는 저수준의 언어로 변환하는 작업입니다. 이 과정은 주로 컴파일러(Compiler)라는 프로그램을 사용합니다. 컴파일된 코드는 실행 파일, 라이브러리 파일 등의 형태로 저장됩니다.

반면, <mark style="color:blue;">**빌드(Build)는 소스 코드와 관련된 모든 작업을 수행하여 실행 가능한 프로그램을 만드는 과정**</mark>입니다. 즉, 컴파일 뿐만 아니라, 코드 분석, 문제 해결, 라이브러리 링킹, 테스트, 패키징 등의 작업을 포함합니다. 빌드는 주로 빌드 도구(Build tool)라는 프로그램을 사용합니다.

컴파일은 소스 코드를 기계어로 변환하는 단계이고, 빌드는 이러한 변환 과정을 포함한 프로그램을 만드는 과정입니다. 즉, 빌드는 컴파일 단계를 포함합니다. 빌드는 소프트웨어를 개발하고 배포할 때 매우 중요한 과정이며, 빌드 도구를 사용하여 자동화할 수 있습니다. 이를 통해 개발자는 효율적인 빌드 프로세스를 구축하고, 소프트웨어의 품질을 개선할 수 있습니다.
