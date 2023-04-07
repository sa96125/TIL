# 연산자

자바에서는 산술 연산자, 비교 연산자, 논리 연산자, 삼항 연산자, 대입 연산자,  형변환 연산자,`instanceof` 연산자 등 다양한 종류의 연산자를 지원합니다. `instanceof` 연산자는 객체가 특정 클래스 또는 인터페이스의 인스턴스인지 여부를 판별하는 데 사용됩니다.



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

// 형변환 연산자
num2 = (int)'3.14'

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
