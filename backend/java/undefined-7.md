# 다형성

다형성(Polymorphism)은 객체 지향 프로그래밍에서의 중요한 개념 중 하나로, 같은 타입 또는 인터페이스를 구현하는 여러 객체가 동일한 메시지에 대해 서로 다르게 반응하는 것을 의미합니다.

즉, 다형성은 <mark style="color:blue;">동일한 코드를 여러 객체에 적용하여 다양한 동작</mark>을 하도록 할 수 있게 해주는 기능입니다. 이를 통해 코드의 재사용성과 유지보수성을 높일 수 있으며, 객체 지향 프로그래밍에서 상속과 인터페이스를 이용하여 구현됩니다.





_<mark style="background-color:yellow;">바로, 예시 코드를 살펴보겠습니다.</mark>_

```java
// Shape 클래스
public abstract class Shape {
    public abstract void draw();
}

// Circle 클래스
public class Circle extends Shape {
    @Override
    public void draw() {
        System.out.println("Drawing a Circle");
    }
}

// Rectangle 클래스
public class Rectangle extends Shape {
    @Override
    public void draw() {
        System.out.println("Drawing a Rectangle");
    }
}

// Drawing 클래스
public class Drawing {
    private List<Shape> shapes = new ArrayList<Shape>();

    public void addShape(Shape shape) {
        shapes.add(shape);
    }

    public void drawShapes() {
        for (Shape shape : shapes) {
            shape.draw();
        }
    }
}

// Main 클래스
public class Main {
    public static void main(String[] args) {
        Drawing drawing = new Drawing();
        drawing.addShape(new Circle());
        drawing.addShape(new Rectangle());
        drawing.drawShapes();
    }
}
```



위 코드에서 Shape 클래스는 추상 클래스로, draw() 메서드를 추상 메서드로 선언합니다. Circle과 Rectangle 클래스는 Shape 클래스를 상속받아 draw() 메서드를 오버라이딩하여 도형을 그리는 기능을 구현합니다. Drawing 클래스는 Shape 타입의 리스트를 멤버 변수로 갖고 있으며, addShape() 메서드를 통해 도형을 추가하고 drawShapes() 메서드를 통해 모든 도형을 그립니다.



이때, Drawing 클래스는 Shape 타입의 리스트를 멤버 변수로 갖고 있으므로, Circle과 Rectangle 객체를 Shape 타입으로 추가할 수 있습니다. drawing.drawShapes() 메서드를 호출하면, 동적 바인딩(Dynamic Binding)을 통해 Circle과 Rectangle 객체의 draw() 메서드가 각각 호출되어 도형을 그리는 결과를 출력합니다. 이처럼 <mark style="color:blue;">Shape 타입으로 도형 객체를 다루면, 각 객체의 실제 타입을 알 필요 없이 동일한 인터페이스를 사용하여 다형성을 구현</mark>할 수 있습니다.







_<mark style="background-color:yellow;">혹시 기본형 타입처럼 형 변환이 가능한가요?</mark>_

부모타입의 참조변수로 자식타입의 인스턴스를 참조할 수 있습니다. 당연히 참조변수의 타입 변환도 가능합니다. 형 변환을 통해 인스턴스에서 사용할 수 있는 멤버의 개수를 조절 할 수 있습니다. 참조변수의 <mark style="color:blue;">타입에 따라 사용할 수 있는 멤버의 개수가 달라질 수 있기 때문</mark>에 문제가 발생할 수 있습니다.&#x20;

* 업 캐스팅 : 자식 타입에서 부모 타입으로 형변환(생략가능)
* 다운 캐스팅 : 부모 타입에서 자식 타입으로 형변환(생략불가)



참조변수의 타입이 다를 경우, 주의해야할 사항은 다음과 같습니다.

1. 만약 인스턴스 변수의 이름이 같다면, 타입에 따라 다른 결과를 얻는다.
2. 만약 인스턴스 메서드가 오버라이딩 되어 있다면, 같은 결과를 얻는다.
3. 만약 중복된 멤버가 없다면, 타입에 관계없이 부모의 멤버를 사용한다.

```java
// 중복된 멤버가 있을 경우
class BindingTest {
    public static void main(String[] args) {
        Parent p = new Child();
        Child c = new Child();
        
        System.out.println(p.x); // 100
        System.out.println(c.x); // 200

        System.out.println(p.method); // child one    
        System.out.println(c.method); // child one
    }
}

class Parent {
    int x = 100;
    
    void method() {
        // ...
    }
}

class Child extends Parent {
    int x = 200;
    
    void method() {
        // ...
    }
}

// 중복된 멤버가 없을 경우
class BindingTest {
    public static void main(String[] args) {
        Parent p = new Child();
        Child c = new Child();
        
        System.out.println(p.x); // 100
        System.out.println(c.x); // 100

        System.out.println(p.method); // parent's one    
        System.out.println(c.method); // parent's one
    }
}

class Parent {
    int x = 100;
    
    void method() {
        // ...
    }
}

class Child extends Parent { // ... }
```







_<mark style="background-color:yellow;">참조 변수의 타입에 따라 접근할 수 있는 멤버가 다른 것을 숙지했어요.</mark>_\
_<mark style="background-color:yellow;">반대로 생각해보면 부모가 같다면 공통 멤버를 함께 관리 할 수 있다는 의미겠네요?</mark>_

네 맞아요. 다형성의 <mark style="color:blue;">핵심은 코드의 재사용성과 유연성을 높이는 것</mark>입니다. 객체 지향 프로그래밍에서는 객체를 중심으로 프로그래밍을 하기 때문에, 객체 간의 관계를 쉽게 설계하고 유지보수할 수 있어야 합니다. 다형성은 상속과 인터페이스를 통해 객체 간의 관계를 유연하게 만들어주어, 코드의 재사용성과 유지보수성을 높여줍니다.



매개변수에 다형성을 적용한 예시코드입니다.

```java
// 자식 클래스 타입에서 멤버 변수에 접근
void buy(Computer c) {
    money = money - c.price;
    // ...
}

void buy(Audio a) {
    money = money - a.price;
    // ...
}


// 부모 클래스 타입에서 멤버 변수에 접근
void buy(Product p) {
    money = money - p.price;
    // ...
}
```



제품의 종류가 늘어날 때 마다 새로운 buy메서드를 추가 해야하는 로직에 다형성을 적용하면 하나의 메서드로 간단히 처리할 수 있습니다. 다른 제품 클래스를 추가할 때 Product의 클래스를 상속받기만 하면 buy메서드의 매개변수로 받아질 수 있습니다.







