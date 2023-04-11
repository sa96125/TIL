# 상속

상속이란 기존의 <mark style="color:blue;">클래스를 재사용하여 새로운 클래스를 작성</mark>하는 것입니다. OOP에서 클래스들 간에 존재하는 개념으로, 부모 클래스가 가지고 있는 특성(필드)과 행위(메서드)를 자식 클래스가 물려받아 사용할 수 있는 것을 말합니다. 이를 통해 코드의 재사용성과 유지보수성을 높일 수 있습니다.





_<mark style="background-color:yellow;">예시 코드를 살펴보겠습니다.</mark>_

```java
// 부모 클래스
class Animal {
    private String name;
    private int age;
    
    public Animal(String name, int age) {
        this.name = name;
        this.age = age;
    }
    
    public void move() {
        System.out.println("움직입니다.");
    }
    
    public void makeSound() {
        System.out.println("소리를 냅니다.");
    }
}

// 자식 클래스
class Dog extends Animal {
    private String breed;
    
    public Dog(String name, int age, String breed) {
        super(name, age);
        this.breed = breed;
    }
    
    @Override
    public void makeSound() {
        System.out.println("멍멍!");
    }
}

// 사용 예시
public class Main {
    public static void main(String[] args) {
        Animal animal = new Animal("동물", 5);
        animal.move();
        animal.makeSound();
        
        Dog dog = new Dog("강아지", 2, "진돗개");
        dog.move();
        dog.makeSound();
    }
}

```



위 코드에서는 `Animal`이라는 부모 클래스와 `Dog`라는 자식 클래스가 존재합니다. `Dog` 클래스는 `Animal` 클래스를 상속받아서 `name`과 `age` 필드, `move()` 메서드, `makeSound()` 메서드를 사용할 수 있습니다. 또한, `Dog` 클래스에서 `makeSound()` 메서드를 오버라이딩하여 "멍멍!"이라는 다른 동작을 수행하도록 구현하였습니다.



`main()` 메서드에서는 `Animal` 객체와 `Dog` 객체를 생성하여 `move()` 메서드와 `makeSound()` 메서드를 호출하여 결과를 출력합니다. 이를 통해 부모 클래스의 특성을 물려받은 자식 클래스를 생성하고 사용하는 예시를 볼 수 있습니다.



특이한 점은, 생성자와 초기화 블럭은 상속되지 않습니다. 생성자는 객체를 초기화할 때 호출되기 때문에, 상속받은 자식 클래스에서는 자신만의 초기화 작업을 수행해야합니다. 부모 클래스의 생성자를 그대로 상속받는 것은, 자식 클래스의 초기화 작업에 영향을 끼칠 수 있기 때문입니다.







_<mark style="background-color:yellow;">클래스안에 멤버변수에 사용자 타입(클래스)로 선언할때도 있던데,</mark>_\
_<mark style="background-color:yellow;">상속하는 거랑 무슨 차이가 있는 걸까요?</mark>_

하나의 거대한 클래스를 작성하는 것보다 단위별로 여러 개의 클래스를 작성한 다음 이 단위 클래스들을 포함관계로 재사용하면 보다 간결하고 이해하기 쉽게 클래스를 작성할 수 있습니다. 또한, 코드가 작게 나뉘어 작성되어 있기 때문에 코드를 관리하는데도 수월합니다.



포함관계로 Engine과 Door를 미리 작성한 경우의 예시 코드입니다.

```java
class Car {
    Engine e = new Engine();
    Door[] d = new Door[4];
    // ...
}
```



클래스를 작성하는데 있어 상속관계를 맺을 것인지 포함관계를 맺어줄 것인지 결하는하는 것은 때때로 혼돈스러울 수 있습니다. 왜냐하면 기능적으로 별반 큰 차이가 없기 때문입니다.

```java
// 포함 관계
class Circle {
    Point c = new Point();
    int r;
}

// 상속 관계
class Circle extends Point {
    int r;
}
```



이를 명확하게 구분하는 방법은 is(상속) / has(포함)를 대입하여 의미론적으로 생각해보는  것입니다.

* Circle is Point (x)
* Circle has Point (o)



따라서 이 경우에는 has(포함관계)가 명확해 보입니다. 이처럼 프로그램에 사용되는 모든 클래스를 분석하여 가능한 많은 관계를 맺어 주도록 노력해서 코드의 재사용성을 높여야합니다.

{% code overflow="wrap" %}
```
🔍 위의 코드에서 부모클래스 Circle 또한 컴파일 과정에서 자동으로 상속을 받습니다. 자바에서는 모든 클래스의 최상위에 object 클래스가 위치하는데 모든 인스턴스가 가져야할 기본적인 메소드가 정의되어 있어 toString()과 같은 공용 메소드를 호출할 수 있는 것입니다.
```
{% endcode %}







_<mark style="background-color:yellow;">그럼, 이 상속이란 개념은 모든 객체지향에서 적용 되겠네요.</mark>_\
_<mark style="background-color:yellow;">C++에서 상속과 자바의 상속은 똑같다고 생각하면 될까요?</mark>_

다릅니다. c++에서는 여러 부모클래스로부터 상속받는 것이 가능한 다중상속이 허용되지만 <mark style="color:blue;">자바에서는 둘 이상의 클래스로부터 상속 받을 수 없습니다</mark>. 이  때문에, 복합적인 기능을 가진 클래스를 쉽게 작성할 수 없겠지만, 클래스 간의 관계가 보다 명확해지고 코드를 더욱 신뢰할 수 있게 만들어 준다는 점에서 다중상속보다 유리점이 있습니다.







_<mark style="background-color:yellow;">질문1. 코드를 재사용하기 위해서 상속을 했습니다.</mark>_\
_<mark style="background-color:yellow;">근데 특정 메서드의 내용을 변경하고 싶다면 어떻게 할까요요?</mark>_

오버라이딩(Overriding)이란, 부모 클래스로부터 상속받은 메서드의 내용을 변경하는 것을 말합니다. 기본 성립조건은 이름, 매개변수, 반환타입이 같아야합니다. 접근제어자 또는 예외처리를 변경하는 것도 당연히 포함됩니다.



만약 접근제어자, 예외처리통해 오버라이딩을 할경우 주의 해야할 점은 다음과 같습니다.

* 접근 제어자는 부모클래스의 메서드보다 좁은 범위로 변경할 수 없다.
* 조상 클래스의 메서드보다 많은 수의 예외를 선언할 수 없다.
* 인스턴스 메서드를 클래스 메서드로 또는 그 반대로 변경할 수 없다.

```java
// 접근 제어자 오버라이딩 예제
class Parent {
    protected void parentMethod() {
         // ...   
    }
}

class Child extends Parent {
    // Error
    private void parentMethod() {
         // ...   
    }
    
    // OK
    public void parendMethod() {
         // ...   
    }
}


// 예외처리 오버라이딩 예제
class Parent {
    void parentMethod() throws IOException, SQLException {
         // ...   
    }
}

class Child extends Parent {
    // Error
    private void parentMethod() throws Exception {
         // ...   
    }
    
    // OK
    public void parendMethod() throws IOException {
         // ...   
    }
}

```







_<mark style="background-color:yellow;">질문2. 코드를 재사용하기 위해서 상속을 했습니다,</mark>_\
_<mark style="background-color:yellow;">부모와 자식이 동일한 멤버 변수 이름을 사용할때, 이를 구분할 수 있을까요?</mark>_

super 키워드는자식 클래스에서 부모 클래스로부터 상속받은 멤버를 참조하는데 사용되는 참조변수입니다. 멤버 이름이 중복 정의 되어 서로 구별해야하는 경우에만 super를 사용하는 것이 좋습니다. 이 점을 제외하고는 super와 this는 근본적으로 같습니다.

* super.멤버변수 : 중복 정의 된 부모클래스의 멤버변수, 그 외의 경우는 this와 같다.
* this.멤버변수 : 중복 정의 된 자식클래스의 멤버변수, 그 외의 경우는 super와 같다.



this와 this()가 다른 것처럼(클래스의 다른 생성자를 호출할 때 사용), 마찬가지로 super() 또한 생성자입니다. 자식 클래스의 인스턴스 생성은 부모와 자식이 융합된 인스턴스의 생성을 의미합니다. 부모의 멤버를 그대로 사용하기 때문에 당연히 부모 클래스의 생성자를 호출해야 자식에서 멤버변수에 접근할 수 있기때문에 <mark style="color:blue;">상속받는 클래스의 생성자의 첫줄에는 super()가 삽입</mark>되어야 합니다.

{% code overflow="wrap" %}
```
🔍 object클래스를 제외한 모든 클래스의 생성자 첫 줄에는 생성자 this() 또는 super()를 호출해야합니다. 그렇지 않으면 컴파일러가 자동적으로 super();를 생성자 첫 줄에 삽입합니다.

🔍 인스턴스를 생성할 때, 클래스를 선택하는 것 만큼 생성자를 선택하는 것도 중요합니다. 올바른 생성자를 선택하지 않으면 인스턴스가 예상대로 초기화되지 않을 수 있습니다. 예를 들어, 인스턴스의 필드 중 일부가 초기화되지 않았다면, 인스턴스의 메소드를 호출할 때 NullPointerException과 같은 예외가 발생할 수 있습니다. 또한 클래스에 여러 개의 생성자가 있는 경우, 인스턴스 생성에 사용되는 생성자를 선택하는 것은 해당 클래스의 요구 사항과 일치하는 생성자를 선택해야합니다. 이를테면, 인스턴스를 생성할 때 인수를 전달해야 하는 경우, 해당 인수를 받아들일 수 있는 생성자를 선택해야 합니다. 생성자는 클래스의 일부이므로 클래스 설계를 고려하여 생성자를 선택해야합니다. 따라서 생성자를 선택할 때 클래스의 책임 및 역할, 다른 메소드와의 관계 등을 고려해야합니다.
```
{% endcode %}

