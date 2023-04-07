# 조건문과 반복문

자바에서 조건문은 <mark style="color:blue;">**프로그램의 흐름을 제어**</mark>하는 데 사용됩니다. 조건문은 주어진 조건에 따라 코드 블록을 실행하거나 실행하지 않을 수 있습니다. 반복문은 특정 조건이 참(true)인 경우에 한해서 <mark style="color:blue;">**코드 블록을 반복적으로 실행**</mark>할 수 있게 해줍니다. 자바에서는 크게 for문, while문, do-while문 세 가지 종류의 반복문이 제공됩니다.







_<mark style="background-color:yellow;">마찬가지로, 자바에서 사용하는 조건문은 다른 프로그래밍 언어와 큰 차이가 없으니,</mark>_ \
_<mark style="background-color:yellow;">예시 코드를 보고 빠르게 숙지할 수 있도록 합시다 :)</mark>_

```java
// 1. if 문
if (조건식) {
    // 조건식이 참일 때 실행할 코드
}

// 2. if-else 문
if (조건식) {
    // 조건식이 참일 때 실행할 코드
} else {
    // 조건식이 거짓일 때 실행할 코드
}

// 3. if-else if-else 문
if (조건식1) {
    // 조건식1이 참일 때 실행할 코드
} else if (조건식2) {
    // 조건식2가 참일 때 실행할 코드
} else {
    // 모든 조건식이 거짓일 때 실행할 코드
}

// 4. switch 문
switch (변수) {
    case 값1:
        // 값1에 해당하는 코드
        break;
    case 값2:
        // 값2에 해당하는 코드
        break;
    // ...
    default:
        // 모든 경우에 해당하지 않을 때 실행할 코드
        break;
}
```







_<mark style="background-color:yellow;">상황에 따라 if문을 사용하기도 switch문을 사용하기도 합니다.</mark>_\
_<mark style="background-color:yellow;">둘의 차이점을 뭘까요? 성능적인 차이도 있을까요?</mark>_

if문은 조건식이 참(true)인 경우 해당 블록을 실행합니다. 따라서, <mark style="color:blue;">**if문은 조건이 달라질 때마다 순서대로 조건식을 평가**</mark>하므로, 조건문이 복잡하거나 조건의 개수가 많은 경우에는 성능이 저하될 수 있습니다.



반면, switch문은 일반적으로 if문보다 더 빠르게 실행됩니다. <mark style="color:blue;">**switch문은 조건식의 결과를 기반**</mark>으로 각각의 case문을 실행하므로, if문보다 더 빠른 속도를 보장합니다. 하지만, switch문은 조건식이 정수형 또는 문자열 형태이어야 하며, 각 case문은 상수(constant) 또는 리터럴(literal) 값으로만 설정해야 합니다. 또한, case문에서 <mark style="color:blue;">**break문을 사용하여 다음 case문으로 이동하는 것을 방지**</mark>해야 합니다.



따라서, if문과 switch문 중 어떤 것을 사용할지는 조건의 복잡도와 데이터 타입, 실행 속도 등 다양한 요소를 고려하여 결정해야 합니다. 일반적으로, 조건의 개수가 많거나 조건이 복잡한 경우에는 if문을 사용하는 것이 더 나을 수 있습니다. 하지만, 조건의 개수가 제한적이고 간단한 경우에는 switch문을 사용하는 것이 더 효율적일 수 있습니다.







_<mark style="background-color:yellow;">특별할 것 없는 자바의 반복문?</mark>_\
_<mark style="background-color:yellow;">반복문에도 이름을 지을 수 있다는 사실! 알고 있나요?</mark>_

반복문을 사용하면 코드의 중복을 최소화하고, 반복적으로 비슷한 작업을 수행할 수 있습니다. 하지만, 반복문을 사용할 때에는 무한 루프(infinite loop)에 빠지지 않도록 주의해야 합니다. 또한, 반복문의 종료 조건을 정확히 파악하고, 반복문의 성능에 영향을 미치는 요소들도 고려해야 합니다.

```java
// 1. for문
for (초기식; 조건식; 증감식) {
    // 반복적으로 실행할 코드 블록
}

// 2. while문
while (조건식) {
    // 조건식이 참일 경우 반복적으로 실행할 코드 블록
}

// 3. do-while문
do {
    // 최초 한 번 실행하고, 조건식이 참일 경우 반복적으로 실행할 코드 블록
} while (조건식);

// 4. 중첩 반복문, 이름을 가진 반복문
Loop1 : for (초기식; 조건식; 증감식) {
    for (초기식; 조건식; 증감식) {
        if (조건식) {
            break Loop1;
        }
    }
}
```



while문의 내부 로직에서 특정 조건에서 루프를 종료하고 싶다면 break 키워드를 선언하고, 반복문의 끝으로 이동하여 다음 반복으로 넘어가고 싶다면 continue 키워드를 사용합니다.

```java
// 중첩 반복문, 이름을 가진 반복문
Loop1 : for (초기식; 조건식; 증감식) {
    for (초기식; 조건식; 증감식) {
        if (조건식) {
            break Loop1;
        }
    }
}
```

