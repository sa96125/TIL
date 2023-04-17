# Terms

_<mark style="background-color:yellow;">Tightly coupling vs Loosely coupling?</mark>_

타이트한 결합과 느슨한 결합은 소프트웨어 컴포넌트간의 상호 의존성 정도를 나타내는 용어입니다. 타이트한 결합은 두 개 이상의 컴포넌트가 서로 강하게 의존하는 상황을 말합니다. 즉, 한 컴포넌트에서 변경이 일어날 경우 다른 컴포넌트에도 큰 영향을 미칠 수 있습니다. 다시 말해, 타이트하게 결합된 컴포넌트는 서로 강하게 묶여있어 분리하기가 어려울 수 있습니다. 타이트한 결합 시스템은 유연성이 낮아서 유지보수가 어려울 수 있으며, 한 컴포넌트를 수정하면 다른 컴포넌트도 수정해야 하는 경우가 많습니다.

반면, 느슨한 결합은 두 개 이상의 컴포넌트가 서로 독립적인 상황을 말합니다. <mark style="color:blue;">한 컴포넌트에서 변경이 일어나도 다른 컴포넌트에 영향을 미치지 않습니다. 느슨하게 결합된 컴포넌트는 독립적이며, 쉽게 수정하거나 교체할 수 있습니다.</mark> 느슨한 결합 시스템은 유연성이 높아서 유지보수와 수정이 쉬울 수 있습니다.

```
(높은 결합)
An engine is tightly coupled to a Car.

(낮은 결합)
A wheel is loosely coupled to a Car.
```

결론적으로, 타이트하게 결합된 시스템은 개발이 용이하고 효율적일 수 있지만, 장기적으로 유지보수와 수정이 어려울 수 있습니다. 반면, 느슨하게 결합된 시스템은 개발이 복잡할 수 있지만, 유지보수와 수정이 쉽고 유연하게 대처할 수 있습니다.



자바에서는  인터페이스를 사용하여 느슨한 결합으로 코드를 유지할 수 있습니다. 다음 예시코드는 높은 결합도를 가진 자바 클래스입니다. 게임을 변경할 때 여러 곳의 코드를 변경해야하므로 유지보수가 어렵습니다.&#x20;

```java
public class Nintendo {
       public static void main(String[] args) {
              var game = new MarioGame();
              // var game = new PackManGame(); -> ERROR : 생성자 only for MarioGame 
              // var game = new SuperContraGame(); -> ERROR : 생성자 only for MarioGame 

              var gameRunner = new GameRunner(game);
              gameRunner.run();
       }
}

public class GameRunner {
       private MarioGame game;
       // private PackManGame game;
       // private SuperContraGame game;
              
       public GameRunner(MarioGame game) {
              this.game = game
       }
       
       public void run() { ... }
}

public class MarioGame { ... }

public class PacManGame { ... }

public class SuperContraGame { ... }
```



하지만 인터페이스를 사용하여 코드를 느슨한 결합으로 코드 변경에 크게 영향을 받지 않을 뿐더러    클래스를 독립적으로 유지보수할 수 있습니다.

```java
public class Nintendo {
       public static void main(String[] args) {
              var game = new MarioGame();
              // var game = new PackManGame(); -> OK 
              // var game = new SuperContraGame(); -> OK 

              var gameRunner = new GameRunner(game);
              gameRunner.run();
       }
}

public class GameRunner { 
       private GameConsole game;
       // private PackManGame game;
       // private SuperContraGame game;
              
       public GameRunner(GameConsole game) {
              this.game = game
       }
       
       public void run() { ... }
}

public interface GameConsole {
       public up () { ... }
       public down () { ... }
       public left () { ... }
       public right () { ... }
}

public class MarioGame implements GameConsole { ... }

public class PacManGame implements GameConsole { ... }

public class SuperContra implements GameConsole { ... }
```





_<mark style="background-color:yellow;">package?</mark>_

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





_<mark style="background-color:yellow;">javac.exe?</mark>_

`javac.exe`는 Java 컴파일러입니다. Java 컴파일러는 Java 소스 코드 파일(.java)을 컴파일하여 바이트 코드 파일(.class)을 생성하는 도구입니다. `.class` 파일은 Java 클래스 파일, 인터페이스 파일, 혹은 에노테이션 파일 등의 형태가 될 수 있습니다. 이 파일들은 Java 애플리케이션을 구성하는 기본 단위입니다.

```sh
# JVM가 이해 할 수 있는 기계어(.class)로 변환
# 이 과정에서 디버깅 할 수 있음
jongseungMac > javac Hello.java
```



`.class`는 Java 바이트 코드 파일의 확장자입니다. Java 컴파일러(`javac`)는 Java 소스 코드 파일(`.java`)을 컴파일하여 이진 형식으로 된 바이트 코드 파일(`.class`)을 생성합니다. 이러한 바이트 코드 파일은 Java 가상 머신(JVM)에서 실행됩니다.



`.class` 파일은 이진 형식으로 되어 있으며, 특정 JVM에서 실행되는 바이트 코드로 구성됩니다. 이러한 구조는 Java 애플리케이션의 이식성(portability)과 보안성(security)을 높이는 데 도움을 줍니다. 또한, `.class` 파일은 컴파일러나 빌드 도구 등 다양한 도구들에서 사용되며, 이를 이용하여 Java 애플리케이션을 개발하고 실행할 수 있습니다.





_<mark style="background-color:yellow;">java.exe?</mark>_

`java.exe` 는 Java 인터프리터입니다.  Java 프로그램(.class)를 실행하는 도구 입니다.

```sh
# java 프로그램(.class) 실행
jongseungMac > java Hello  
```





_<mark style="background-color:yellow;">Build와 Compile?</mark>_

<mark style="color:blue;">컴파일(Compile)은 소스 코드를 기계어로 변환하는 과정</mark>입니다. 즉, 소스 코드를 작성한 개발자가 이해할 수 있는 고수준의 언어를 컴퓨터가 이해할 수 있는 저수준의 언어로 변환하는 작업입니다. 이 과정은 주로 컴파일러(Compiler)라는 프로그램을 사용합니다. 컴파일된 코드는 실행 파일, 라이브러리 파일 등의 형태로 저장됩니다.

반면, <mark style="color:blue;">빌드(Build)는 소스 코드와 관련된 모든 작업을 수행하여 실행 가능한 프로그램을 만드는 과정</mark>입니다. 즉, 컴파일 뿐만 아니라, 코드 분석, 문제 해결, 라이브러리 링킹, 테스트, 패키징 등의 작업을 포함합니다. 빌드는 주로 빌드 도구(Build tool)라는 프로그램을 사용합니다.

컴파일은 소스 코드를 기계어로 변환하는 단계이고, 빌드는 이러한 변환 과정을 포함한 프로그램을 만드는 과정입니다. 즉, 빌드는 컴파일 단계를 포함합니다. 빌드는 소프트웨어를 개발하고 배포할 때 매우 중요한 과정이며, 빌드 도구를 사용하여 자동화할 수 있습니다. 이를 통해 개발자는 효율적인 빌드 프로세스를 구축하고, 소프트웨어의 품질을 개선할 수 있습니다.





_<mark style="background-color:yellow;">인자(argument)와 매개변수(parameter)의 차이?</mark>_

매개변수는 함수나 메서드를 정의할 때 사용되는 변수이고, 인자는 함수나 메서드를 호출할 때 전달되는 값입니다. 인자의 타입은 매개변수의 타입과 일치하거나 자동 형변환이 가능한 것이여야합니다.





_<mark style="background-color:yellow;">기본형 매개변수와 참조형 매개변수의 차이?</mark>_

자바에서 메서드를 호출할 때 인자는 매개변수에 복사해서 넘겨주게됩니다. 매개변수의 타입이 기본형(primitive type)일 때는 값이 복사되겠지만, 참조형(reference type)이면 인스턴스의 주소가 복사됩니다.&#x20;

<pre data-overflow="wrap"><code><strong>🔍 기본형일 경우 읽기만 가능하고 참조형일 경우 읽기와 쓰기가 가능합니다. 즉, 참조형일 경우 원본데이터에 영향이 미칠 수 있기 때문에 주의해야합니다.
</strong></code></pre>





_<mark style="background-color:yellow;">overloading?</mark>_

한 클래스 내에 같은 이름의 메서드를 여러 개 정의하는 것을 의미합니다. 오버로딩을 통해, 근본적으로 같은 기능을 하는 메서드들을 구분하여 기억할 필요가 없게 되어 메서드의 이름을 절약할 수 있습니다.



이름이 같다고 무조건 오버로딩이 아니라 다음과  같은 조건이 성립해야합니다.

1. 메서드 이름이 같아야한다.
2. 매개변수의 개수 또는 타입이 달라야한다.
3. 반환 타입은 오버로딩을 구현하는데 아무런 영향을 주지 못한다.





_<mark style="background-color:yellow;">가변인자?</mark>_

JDK1.5부터 메서드의 매개변수 개수를 동적으로 지정해 줄 수 있게 되었는데 이를 가변인자라고 합니다.

```java
public static int sum(int... numbers) {
    int result = 0;
    for (int num : numbers) {
        result += num;
    }
    return result;
}

int result1 = sum(1, 2, 3, 4, 5);
int result2 = sum(10, 20, 30);
int result3 = sum();
```



가변인자를 선언할 시, 주의사항은 다음과 같습니다.

1. 가변 인자외에 매개변수가 더 있을 경우, 가변인자를 매개변수의 제일 마지막에 선언한다.
2. 가변 인자를 사용한 메서드는 가능하면 오버로딩하지 않는 것이 좋다.





_<mark style="background-color:yellow;">재귀호출과 반복문의 차이?</mark>_\
_<mark style="background-color:yellow;">굳이 재귀호출을 사용하는 이유가 뭘까요?</mark>_

메서드의 내부에서 자기자신을 다시 호출하는 것을 '재귀 호출'이라하고, 재귀호출을 하는 메서드를 '재귀 메서드'라고 합니다. 호출된 메서드의 call by value를 통해, 원래의 값이 아닌 복사된 값으로 작업하기 때문에 호출한 메서드와 관계없이 독립적인 작업 수행이 가능합니다. 그런데, 오로지 재귀호출뿐이라면, 무한히 자기 자신을 호출하기 때문에 무한 반복에 빠지기 때문에 종료가능한 조건문이 필수입니다.



재귀호출은 반복문과 유사한 점이 많고 대부분의 재귀호출은 반복문으로 작성하는 것이 가능합니다.

<pre class="language-java"><code class="lang-java"><strong>// 재귀호출로 구현한 팩토리얼
</strong><strong>public static int factorial(int n) {
</strong>    if (n == 0) {
        return 1;
    } else {
        return n * factorial(n - 1);
    }
}

// 반복문으로 구현한 팩토리얼
public static int factorial(int n) {
    int result = 1;
    for (int i = 1; i &#x3C;= n; i++) {
        result *= i;
    }
    return result;
}
</code></pre>



재귀호출의 경우, 매개변수 복사와 종료 후 복귀할 주소저장 등이 추가로 필요하기때문에 반복문보다 수행시간이 더 오래 걸립니다. 그럼에도 불구하고 재귀함수를 사용하는 이유는 <mark style="color:blue;">논리적 간결함</mark>이 있기때문입니다. 복잡한 조건문과 반복문대신 단순한 구조로 구현할 수 있습니다. 다소 비효율적이더라도 알아보기 쉽게 작성하는 것이 논리적 오류가 발생할 확률도 줄어들고 수정하기도 수월합니다.

기억해야할 것은, 재귀호출은 비효율적이므로 <mark style="color:blue;">재귀호출에 드는 비용보다 재귀호출의 간결함이 주는 이득이 충분히 큰 경우에만 사용</mark>해야합니다.





_<mark style="background-color:yellow;">StackOverflowError?</mark>_

콜 스택이 계속해서 쌓여 메모리의 한계를 넘게되어 프로그램이 비정상적으로 종료되는 것을 의미합니다.





_<mark style="background-color:yellow;">Overloading과의 Overriding의 차이점은 뭘까요?</mark>_

* 오버로딩 : 기존에 없는 새로운 메서드를 정의하는 것(new)
* 오버라이딩 : 상속받은 메서드의 내용을 변경하는 것(mod)





_<mark style="background-color:yellow;">Modifier?</mark>_

제어자는 클래스, 변수 또는 메서드의 선언부에 함께 사용되어 부가적인 의미를 부여합니다.&#x20;

1.  접근 제어자(access modifier)\
    접근 제어자를 사용하는 이유는 클래스 내부에 선언된 데이터를 보호하기 위해서입니다. 때로는 데이터가 유효한 값을 유지하도록, 비밀번호와 같은 중요한 정보를 외부에서 함부러 변경하지 못하도록 하기 위해서는 접근을 제한할 필요성이 있습니다. 또한 굳이 공개될 필요 없는 정보를 숨길 수 있습니다.

    \
    \- public : 어떤 클래스에서든 접근 가능\
    \- protected : 같은 패키지 내에서와 해당 클래스를 상속받은 하위 클래스에서 접근 가능\
    \- default(package-private) : 같은 패키지 내에서만 접근 가능\
    \- private : 해당 클래스 내에서만 접근 가능(상속이 될 가능성이 있으면 protected로 선언)\

2.  그 외의 제어자(modifier)

    \
    \- static(공통의) : 클래스 레벨의 멤버로 만들어지며, 클래스의 인스턴스 없이도 접근 가능\
    \- final(마지막의) : 상속, 오버라이딩, 변수 변경 불가(생성자를 통해 초기화 가능)\
    \- abstract(미완성의) : 미구현 메소드가 있음을 의미\
    \- synchronized : 멀티스레딩 환경에서 동시 접근을 막기 위해 사용\
    \- transient : 직렬화(serialization)할 때 해당 필드는 제외됨을 나타냄\
    \- volatile : 멀티스레딩 환경에서 해당 필드가 스레드에 의해 공유됨을 나타내며, 메모리의 가시성을 보장하기 위해 사용







_<mark style="background-color:yellow;">제어자로 메서드에 접근 제한을 둘수 있다고 했는데,</mark>_\
_<mark style="background-color:yellow;">생성자 또한 접근 제한을 할 수 있는 건가요?</mark>_

할 수 있습니다. 생성자에 접근 제어자를 사용함으로서 인스턴스의 생성을 제한할 수 있습니다.



대표적인 예로 싱글톤 패턴을 구현하는 예제를 살펴보겠습니다.

```java
public final Singleton {
    private static Singlton s = new Singleton();
    
    private Singleton() {
        // ...
    }
    
    public static Singleton getInstance() {
        return s;
    }
}
```

1. 생성자를 private로 선언하였기 때문에 인스턴스 생성이 불가능
2. 클래스가 메모리에 올라갈 때, 단 하나의 인스턴스를 생성(인스턴스 제한)
3. 인스턴스가 생성 불가능하기때문에 클래스 공통 메서드로접근 (public static)







_<mark style="background-color:yellow;">class Vector?</mark>_&#x20;

동적으로 객체를 저장할 수 있는 클래스입니다. 10개 이상의 인스턴스가 저장되면 자동적으로 크기가 증가합니다. 이처럼, 배열의 크기를 알아서 관리해주기때문에 저장할 인스턴스 개수에 신경쓰지 않아도 됩니다.

