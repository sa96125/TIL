# 연산자

연산자는 <mark style="color:blue;">수학적 또는 논리적 연산을 수행하는 기호 또는 문자</mark>입니다. 연산자는 피연산자라는 하나 이상의 값에 대해 연산을 수행하며, 결과를 반환합니다. 자바에서는 산술 연산자, 비교 연산자, 논리 연산자, 삼항 연산자, 대입 연산자, 형변환 연산자,`instanceof` 연산자 등 다양한 종류의 연산자를 지원합니다.





_<mark style="background-color:yellow;">자바에서 사용하는 연산자는 다른 프로그래밍 언어와 큰 차이가 없으니,</mark>_ \
_<mark style="background-color:yellow;">예시 코드를 보고 빠르게 숙지할 수 있도록 합시다 :)</mark>_

```java
int num1 = 10;
int num2 = 3;

// 산술 연산자
int result1 = num1 + num2;
int result2 = num1 - num2;
int result3 = num1 * num2;
int result4 = num1 / num2;
int result5 = num1 % num2;

// 비교 연산자
boolean isEqual = (num1 == num2);
boolean isGreater = (num1 > num2);
boolean isLessOrEqual = (num1 <= num2);

// 논리 연산자
boolean logicalAnd = (num1 > 0 && num2 > 0);
boolean logicalOr = (num1 > 0 || num2 > 0);
boolean logicalNot = !(num1 > 0);

// 삼항 연산자
int result6 = (num1 > num2) ? num1 : num2;

// 대입 연산자
num1 += num2;
num2 -= num1;

System.out.println(result1); // 13 출력
System.out.println(result2); // 7 출력
System.out.println(result3); // 30 출력
System.out.println(result4); // 3 출력
System.out.println(result5); // 1 출력
System.out.println(isEqual); // false 출력
System.out.println(isGreater); // true 출력
System.out.println(isLessOrEqual); // false 출력
System.out.println(logicalAnd); // true 출력
System.out.println(logicalOr); // true 출력
System.out.println(logicalNot); // false 출력
System.out.println(result6); // 10 출력
System.out.println(num1); // 13 출력
System.out.println(num2); // -10 출력

// instanceof 연산자
class Animal {
  // ...
}

class Cat extends Animal {
  // ...
}

class Dog extends Animal {
  // ...
}

Animal animal1 = new Cat();
Animal animal2 = new Dog();

if (animal1 instanceof Cat) {
  System.out.println("animal1 is an instance of Cat");
} else if (animal1 instanceof Animal) {
  System.out.println("animal1 is an instance of Animal");
}

if (animal2 instanceof Dog) {
  System.out.println("animal2 is an instance of Dog");
} else if (animal2 instanceof Animal) {
  System.out.println("animal2 is an instance of Animal");
}

```





_<mark style="background-color:yellow;">생각해보니 우리가 사칙연산할 때, 연산자  우선 순위에 따라 식의 계산 결과가 달라지잔아요?</mark>_\
_<mark style="background-color:yellow;">이렇게 많은 연산자가 있는 걸보니 컴퓨터가 계산하는 방식이 다를 것 같은데..?</mark>_

우선순위는 연산자의 종류에 따라 나뉘며, 우선순위가 높은 연산자가 먼저 계산됩니다. 만약 같은 우선순위를 가진 연산자가 나타날 경우, 연산자 결합 방향에 따라 계산됩니다. 예를들어, 단항연산자(2), 대입연산자(9)를 제외한 모든 연산의 진행방향은 왼쪽에서 오른쪽입니다.

1. 괄호 ( )
2. 단항 연산자 (+, -, ++, --, !, \~)
3. 산술 연산자 (\*, /, %, +, -)
4. 시프트 연산자 (<<, >>, >>>)
5. 비교 연산자 (<, >, <=, >=, instanceof)
6. 비트 연산자 (&, ^, |)
7. 논리 연산자 (&&, ||, !)
8. 삼항 연산자 (조건식 ? 피연산자1 : 피연산자2)
9. 대입 연산자 (=, +=, -=, \*=, /=, %=, <<=, >>=, >>>=, &=, ^=, |=)





_<mark style="background-color:yellow;">앞서 변수와 상수에 대해 공부할 때, 자료형 선언이 중요하다는 생각이 들었는데,</mark>_\
_<mark style="background-color:yellow;">산술계산을 할  때, 주의해야할 사항은 없을까요?</mark>_

이항 연산자는 두 피연산자의 타입이 일치해야 연산이 가능하므로, 피연산자의 타입이 서로 다르다면 연산 전에 형변환 연산자로 타입을 일치시켜야합니다.&#x20;

1. 두 피연산자의 타입을 같게 일치 시킨다.(보다 큰 타입으로 일치)
2. 피연산자의 타입이 int보다 작은 타입이면 int로 변환된다.
3. 값의 범위가 <mark style="color:blue;">자료형 타입의 최대값을 넘으면 오버플로우가 발생</mark>한다.

```java
byte a = 10;
byte b = 20;

// OK
byte c = (byte)(a+b);

// ERROR
byte c = a+b; // byte형 타입에 int형 타입 데이터를 저장X
```

