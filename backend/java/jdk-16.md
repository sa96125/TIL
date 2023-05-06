# JDK 16

record

record는 데이터를 저장하는 불변(immutable) 클래스를 쉽게 작성할 수 있도록 도와주는 기능입니다. record를 사용하면 필드와 접근자 메서드(getter)가 자동으로 생성되므로, 이전 버전의 자바에서 사용되었던 일반적인 클래스보다 코드가 훨씬 간결해집니다. record는 불변(immutable)하며, 생성자 매개변수를 통해 초기화됩니다. 이를 통해 코드의 안정성과 가독성이 향상되며, 개발자는 데이터 클래스를 작성하는 데 집중할 수 있습니다.



다음은 record를 사용한 간단한 예시 코드입니다.

```java
public record Person(String name, int age) {
    // record의 내용은 생성자 매개변수와 세미콜론으로 끝납니다.
    // 이 클래스는 불변(immutable)하며, 필드와 접근자 메서드(getter)를 가집니다.
    
    // 추가적인 메서드나 생성자를 작성할 수 있습니다.
    public String hello() {
        return "Hello, my name is " + name + " and I am " + age + " years old.";
    }
}

// 이제 Person 클래스를 사용할 수 있습니다.
Person p1 = new Person("Alice", 25);
Person p2 = new Person("Bob", 30);

System.out.println(p1.name()); // 출력: Alice
System.out.println(p1.age()); // 출력: 25

System.out.println(p1.hello()); // 출력: Hello, my name is Alice and I am 25 years old.

```

