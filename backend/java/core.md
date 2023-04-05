---
description: 자바 코드를 작성할 때 자주 마주치는 용어를 정리하고 이해합니다:)
---

# core

### package

Java 패키지는 Java 클래스를 논리적으로 그룹화하는 방법입니다. 패키지는 클래스와 인터페이스를 조직적으로 정리하여 관리하기 쉽게 합니다. 패키지는 도메인 이름을 역순으로 나열하여 지정하며, 각 패키지는 하나 이상의 클래스나 서브 패키지를 포함할 수 있습니다.



```java
package com.example.packageName;

public class MyClass {
    // 클래스 구현 내용
}
```

Java 패키지는 `package` 키워드를 사용하여 선언됩니다. 예를 들어, `com.example.packageName` 패키지에 있는 `MyClass` 클래스를 선언하려면 다음과 같이 코드를 작성할 수 있습니다.



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

Java 패키지는 다른 패키지의 클래스를 사용할 수 있습니다. 이를 위해서는 `import` 키워드를 사용하여 다른 패키지의 클래스를 가져와야 합니다. 예를 들어, `com.example.anotherPackage` 패키지에 있는 `AnotherClass` 클래스를 사용하려면, 다음과 같이 `import` 구문을 작성합니다.

****

****

### **class**

클래스는 객체의 상태(state)와 행위(behavior)를 정의하며, 이를 이용하여 객체를 생성할 수 있습니다. 즉, 실행할 코드를 작성합니다. 코드 작성자가 원하는 개념을 정리/구현하는 곳이라 말할 수 있습니다.





### **javac.exe**

`javac.exe`는 Java 컴파일러입니다. Java 컴파일러는 Java 소스 코드 파일(.java)을 컴파일하여 바이트 코드 파일(.class)을 생성하는 도구입니다.

```sh
# JVM가 이해 할 수 있는 기계어(.class)로 변환
# 이 과정에서 디버깅 할 수 있음
jongseungMac > javac Hello.java
```

{% hint style="info" %}
_`.class`는 Java 바이트 코드 파일의 확장자입니다. Java 컴파일러(`javac`)는 Java 소스 코드 파일(`.java`)을 컴파일하여 이진 형식으로 된 바이트 코드 파일(`.class`)을 생성합니다. 이러한 바이트 코드 파일은 Java 가상 머신(JVM)에서 실행됩니다._

_`.class` 파일은 Java 클래스 파일, 인터페이스 파일, 혹은 에노테이션 파일 등의 형태가 될 수 있습니다. 이 파일들은 Java 애플리케이션을 구성하는 기본 단위입니다._

_`.class` 파일은 이진 형식으로 되어 있으며, 특정 JVM에서 실행되는 바이트 코드로 구성됩니다. 이러한 구조는 Java 애플리케이션의 이식성(portability)과 보안성(security)을 높이는 데 도움을 줍니다. 또한, `.class` 파일은 컴파일러나 빌드 도구 등 다양한 도구들에서 사용되며, 이를 이용하여 Java 애플리케이션을 개발하고 실행할 수 있습니다._
{% endhint %}

__

__

### java.exe

`java.exe` 는 Java 인터프리터입니다.  Java 프로그램(.class)를 실행하는 도구 입니다.

```sh
# java 프로그램(.class) 실행
jongseungMac > java Hello
```



