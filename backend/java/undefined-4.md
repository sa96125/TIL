# 배열

자바에서 배열은 <mark style="color:blue;">동일한 유형</mark>의 데이터를 저장하는 데 사용되는 데이터 구조입니다. 배열은 고정 크기이며, 크기는 배열을 생성할 때 결정됩니다. 자바에서 배열을 선언하려면 배열 유형과 배열 이름, 그리고 배열의 크기를 지정해야 합니다. 변수와 달리 배열은 각 저장 공간이 연속적으로 배치되어 있다는 특징을 가집니다.





_<mark style="background-color:yellow;">배열 선언 및 초기화 하는 방법은 다음과 같습니다.</mark>_\
_<mark style="background-color:yellow;">어떤 방법을 사용해야, 효율적으로 배열을 만들 수 있을까요?</mark>_

자바에서 배열을 선언하는 가장 효율적인 방법은 배열의 크기를 미리 알고 있을 때, 배열을 미리 할당하는 것입니다. 이 방법은 불필요한 메모리 할당을 줄이고, 배열의 크기를 늘리거나 줄이는 작업을 피할 수 있어서 성능상 이점이 있습니다.

```java
// 1. 크기가 5인 int형 배열 생성
int[] myArray = new int[5];

// 2. 크기가 5이면서 값을 가지고 있는 int형 배열 생성
int[] myArray = {1, 2, 3, 4, 5};

// 3. 3행 4열의 int형 2차원 배열 생성
int[][] myMultiArray = new int[3][4];

// 4. sourceArray 배열에서 첫 3개의 값을 복제한 destArray 배열 생성
int[] sourceArray = {1, 2, 3, 4, 5}; 
int[] destArray = Arrays.copyOf(sourceArray, 3);

// 5. myArray 배열의 모든 요소를 0으로 초기화
int[] myArray = new int[5]; 
Arrays.fill(myArray, 0); 
```



예를 들어, 다음과 같이 배열을 선언하는 것이 가장 효율적입니다. 만약 배열의 크기를 미리 알 수 없는 경우에는, 필요한 크기에 맞게 동적으로 배열을 할당하는 방법을 사용할 수 있습니다. 예를 들어, 다음과 같이 ArrayList 클래스를 사용하여 가변 크기의 배열을 생성할 수 있습니다.

```java
// 크기를 10으로 미리 지정하여 배열을 할당
int[] myArray = new int[10];

// ArrayList 등의 자료구조를 사용하여 동적으로 배열을 할당 
ArrayList<Integer> myList = new ArrayList<Integer>();
```

