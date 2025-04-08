## 배열(Array)이란?

> **저장공간의 나열**

---

### 배열을 사용하는 이유

1.  **여러 개의 변수를 관리할 때 편리함**

-   각각의 값을 위해 변수를 여러 개 선언하면 **이름도 각각** 달라서 관리가 복잡해짐.
-   배열은 한 번의 선언으로 **n개의 저장공간**을 만들 수 있어, 이름도 **하나만** 사용하면 됨.
-   **코드 간결화 + 유지 보수성 향상**

2.  **규칙성이 없는 값에 규칙성을 부여**

-   배열의 **인덱스(index)**를 통해 **위치 기반으로 값을 제어**할 수 있음.
-   데이터를 순차적으로 다룰 수 있어 **반복문과의 궁합이 뛰어남**

---

### 예시 (Java 기준)

```java
int[] numbers = new int[5];  // 정수형 배열 5칸 선언
numbers[0] = 10;
numbers[1] = 20;
// ...
```

## 배열의 선언 (Java 기준)

배열은 여러 개의 값을 **하나의 이름으로 묶어서** 저장할 수 있는 저장공간이다.
Java에서 배열은 항상 **Heap 메모리**에 할당됩니다. 즉, 메모리적으로는 모두 **동적 배열**이다.

---

### 배열 선언 방법

```java
자료형[] 배열명 = {값1, 값2, ... };
// 어떤 값을 넣을지 "알 때" 사용

자료형[] 배열명 = new 자료형[칸수];
// 어떤 값을 넣을지는 모르나, "몇 칸 만들지는 알 때" 사용

자료형[] 배열명 = null;
// 어떤 값도 모르고, 칸수도 정해지지 않았을 때
```

## 배열의 구조

```java
 int[] arData = {3, 5, 1, 2, 8};
```

-   `arData`라는 이름의 **저장공간** 한 개가 만들어지며, 여기에는 한 개의 값만 담을 수 있다.
-   5개의 값을 담기 위해서는 5칸이 필요하며, 이는 **Heap 메모리**에 할당된다.
-   이 5칸 중 **첫 번째 저장공간의 주소값**이 `arData` 저장공간에 들어간다.
-   이후 다음 주소에 접근하려면 `+ n` 연산을 통해 접근할 수 있다.

예를 들어

-   `arData + 2`는 값 `1`이 담긴 주소값이며,
-   `*(arData + 2)`는 해당 주소에 가서 읽어온 값인 `1`이 된다.

하지만 Java에서는 **직접 주소 접근 연산자**를 사용할 수 없기 때문에,
위와 같은 방식 대신 **`[]` 연산자**를 사용한다:

```java
arData[2]; // 결과: 1
```

## length

> 배열을 선언하면 length라는 상수가 선언되고, 해당 배열의 길이가 담긴다.<br>

**ex) 배열명.length**

## 배열의 사용

```java
int[] arData = new int[5]; // 저장공간
arData[0] = 120; // 저장공간
arData[0] + 9; // 값
System.out.println(arData); // 주소값
arData[2] = arData[0] + arData[1]; // 저장공간, 값3
System.out.println(arData[5]); // 오류
```

## 2차원 배열

> **"배열 안에 배열"**, 즉 **1차원 배열들의 모음**

---

### 왜 2차원 배열을 사용할까?

-   1차원 배열 여러 개를 개별로 선언하면 **관리 복잡도 상승**
-   예: `int[] row1`, `int[] row2`, ...
-   하나로 묶어 관리하기 위해 **2차원 배열 사용**

```java
int[][] arr = {
   {1, 2, 3},
   {4, 5, 6},
   {7, 8, 9}
};
```

---

# 클래스는 `반`이다

> 공통 요소를 한 번만 선언해놓고 사용하도록 <br>설계한 `틀(설계도)`

## `객체(Object)`를 만들기 위한 타입이다.

-   타입이다(Type)<br>
    클래스 안에선언된 변수와 메소드를 사용하고 싶다면.
    해당 클래스 타입으로 변수를 선언해야 한다.

-   주어이다.( 언어다, 영어,,. )<br>
    Moneky.eat("banana")<br>
    원숭이가 먹는다 바나나를,

-   클래스 (class)

```java
class 클래스명{
// 필드 = 변수 , 메소드
};
```

## 클래스 필드 사용 <br>

-   객체화(instance) : 객체(instance variable)를 만드는 작업, 추상적인 개념을 구체화 시키는작업<br>

```java
클래스명 객체명 = new 생성자();
```

## .(마침표)

`하위 연산자`, `멤버 변수 접근 연산자`, `닷 연산자`, `점 연산자`
주소값 뒤에서만 사용이 가능하며, 해당 주소를 참조하는 명령어이다.

```java
클래스명 객체명 = new 클래스명();
객체명.필드명;
객체명.메소드명();
```

## 생성자

클래스 이름 뒤에 소괄호가 있는 형태, 메소드와 기능이 똑같지만 메소드라고 부르지 않는다.<br>
생성자는 리턴이라는 기능이 존재하지 않기 때문이다.<br>

```java
class 클래스명 {
    클래스명() {
        // 생성자 내용 (필드 초기화 등)
    }
}
```

-   해당 클래스 필드 메모리에 할당 후 부여된 주소값을 가져온다.

-   `초기화`

## 기본 생성자

**매개변수가 없는 생성자이며**, 클래스 선언 시 컴파일러가 자동으로 작성해준다.<br>
만약 직접 생성자를 선언하게 되면. 더이상 컴파일러가 작성해주지 않는다.

```java
class Person {
    String name;
    int age;

    // 기본 생성자
    Person() {
        this.name = "이름없음";
        this.age = 0;
    }
}
```

-   **this**

필드에 접근한 객체가 누군지 알아야 해당 필드에 접근할 수 있다.<br>
이 때 접근한 객체가 가지고 있는 필드 주소값. this라는 변수에 자동으로 담긴다.

---

> 다형성(Polymorphism), 오버로딩(Overloading)
> 매개변수의 개수 혹은 타입이 다르면 동일한 이름의 메소드로 선언할 수 있다.

```java
class Calculator {
    int add(int a, int b) {
        return a + b;
    }

    double add(double a, double b) {
        return a + b;
    }

    int add(int a, int b, int c) {
        return a + b + c;
    }
}
```

-   메소드 이름은 같고, **매개변수의 타입/개수/순서가** 달라야함

-   반환타입만 다르다고 오버로딩이 되지 않음

---

<br>

# `배열과 클래스의 차이점`<br>

> 배열은 같은 자료형만 담을 수 있으며 각 방을 번호(index)로 기억해야 한다.<br>
> 순서가 있어야하는 것 또는 처음부터 끝까지 가져오는 작업이라면 배열에 담는 것이 좋다.<br>
> 클래스는 서로 다른 자료형도 담을 수 있으며, 각 값은 전부 이름을 붙여서 필드로 구성한다.<br>
> 원하는 값을 가져오고 싶다면, 클래스로 가져우는 것이 훨씬 낫다.

# 상속 (Inheritance)

> **기존 클래스의 필드(변수/메소드)를 새로운 클래스에서 재사용**할 수 있도록 하는 개념

-   상속 문법

```java
   class A {
      A 필드
   }

   class B extends A{
      A, B 필드
   }
```

### A : 부모 클래스, 상위 클래스, 슈퍼 클래스, 기반 클래스

### B : 자식 클래스, 하위 클래스, 서브 클래스, 파생 클래스

# super()

> 부모 클래스의 생성자를 호출하는 키워드<br>
> 자식 생성자 내에서 부모의 필드를 메모리에 할당하기 위해 사용

-   `개념정리`

```
자식 클래스 타입 객체는 부모 클래스 필드에도 접근할 수 있다.

하지만 자식 생성자만 호출되면 자식 필드만 메모리에 올라간다.

부모 필드까지 접근 가능한 이유는자식 생성자 내부에서 부모 생성자(super())가 자동 호출되기 때문이다.
```

-   **`핵심`**

| 키워드    | 설명                                      |
| --------- | ----------------------------------------- |
| `super()` | 부모 클래스 기본 생성자 호출 키워드       |
| 자동 호출 | 작성하지 않아도 컴파일러가 자동 추가      |
| 위치 제한 | 생성자 내부의 첫 줄에만 작성 가능         |
| 목적      | 부모 필드 및 초기화 위해 부모 생성자 실행 |

```java
class A {
    A() {
        System.out.println("부모 생성자 호출");
    }
}

class B extends A {
    B() {
        super(); // 생략 가능 (자동 호출됨)
        System.out.println("자식 생성자 호출");
    }
}
```

## 다형성 (Polymorphism)

1. **오버로딩 (Overloading)**

    - 같은 이름의 메소드라도 **매개변수의 개수 또는 타입**이 다르면 여러 개 정의할 수 있다.

2. **오버라이딩 (Overriding)**
    - 부모 클래스에서 선언한 메소드를 자식 클래스에서 **재정의**할 때 사용한다.
    - 같은 이름의 메소드로 선언하면, 자식 객체로 접근했을 때 **자식 쪽 메소드가 우선**된다.
    - 부모 클래스 메소드를 그대로 사용하고 싶다면, **`super` 키워드**를 통해 접근할 수 있다.

`ex)`

```java
   class Parent {
       void sayHello() {
           System.out.println("Hello from Parent");
       }
   }

   class Child extends Parent {

       @Override
       void sayHello() {
           super.sayHello(); // 부모 메소드 호출
           System.out.println("Hello from Child");
       }
   }
```

# Casting

-   `업캐스팅(upcasting)`

자식 값을 부모 타입으로 형변환

```java
부모 객체 = new 자식생성자();
```

-   `다운캐스팅(downcasting)`

up casting 된 객체를 다시 자식 타입으로형변환

```java
(자식 클래스)up casting된 객체
(double)
```

**부모 값을 자식 타입으로 형변환 시 오류 발생.**

> Casting을 잘 사용하는 방법

모든 자식들을 하나의 타입으로 묶을 때 up casting을 진행한다.<br>
전달받은 자식 객체가 어떤 타입인지 검사한 뒤 해당 타입으로 down casting을 진행한다.<br>
즉, 묶어서 하나의 타입으로 받고, 다시 원래 타입으로 복구하자!

## 접근 권한 제어자 (Access Modifiers)

자바에서는 클래스, 변수, 메소드 등에 접근 가능한 범위를 지정하기 위해 **접근 제어자**를 사용함

| 접근 제어자 | 같은 클래스 | 같은 패키지 | 자식 클래스 (다른 패키지) | 다른 패키지 |
| ----------- | ----------- | ----------- | ------------------------- | ----------- |
| `public`    | O           | O           | O                         | O           |
| `protected` | O           | O           | O                         | X           |
| (default)   | O           | O           | X                         | X           |
| `private`   | O           | X           | X                         | X           |

---

> **`public`**

-   어디서든 접근 가능 (모든 클래스, 모든 패키지에서 사용 가능)

> **`protected`**

-   같은 패키지 내에서는 자유롭게 접근 가능
-   다른 패키지라 하더라도 **상속받은 자식 클래스는 접근 가능**

> **(default)**

-   접근 제어자를 명시하지 않은 상태
-   같은 패키지 안에서만 접근 가능 (다른 패키지에서는 접근 불가)

> **`private`**

-   **선언된 클래스 내부에서만** 접근 가능
-   다른 클래스에서는 절대 접근할 수 없음

# 추상 클래스

    필드 안에 구현이 안된 메소드가 선언되어 있는 클래스를 추상 클래스라고 한다.
    이 때 구현되지 않은 메소드를 추상 메소드라고 부른다.
    즉, 추상 클래스에 추상 메소드를 선언할수있다.
    이는 반드시 구혆야 하기 때문에 "강제성을: 부여할수있게 된다.

-   `추상 클래스 선언`

```java
	abstract class 클래스명 {
		abstract 리턴타입 메소드명(매개변수,...);
		// 일반 메소드도 선언 가능하다.
	}
```

-   `인터페이스(틀)`<br>
    추상 클래스를 고도화시킨 문법, 상수와 추상 메소드만 존재한다.
    구현은 지정한 클래스에서 진행하고, 인터페이스를 다른 클래스에 지정할 때에는
    implements 키워드를 사용한다.

```java
// 인터페이스
interface Clickable {
    void onClick();
    void onDoubleClick();
}

// 인터페이스 구현 클래스
class Button implements Clickable {
    @Override
    public void onClick() {
        System.out.println("버튼이 클릭되었습니다.");
    }

    @Override
    public void onDoubleClick() {
        System.out.println("버튼이 더블클릭되었습니다.");
    }
}
```

-   `추상클래스와 인터페이스 간의 관계`<br>
    인터페이스를 클래스에 바로 지정하면 모든 메소드에 강제성이 부여되기 때문에
    전부 다 구현해야 한다.<br> 하지만 일반적인 상황에서는 필요한 메소드를 골라서 재졍의한다.
    따라서 인터페이스를 직접 지정하지않고 다른 클래스에 지정한 후 구현해 놓는다면
    강제성이 소멸되고 이로 인해 골라서 재정의할수 있게 된다.<br>
    이 때 중간에서 강제성을 없애주는 클래스를 추상 클래스로 선언하기로 하며,
    추상 클래스 이름 뒤에는 Adpater를 붙여서 목적을 알려준다.

-   `내부 클래스 (inner class)`<br>
    어떤 영역 안에 클래스가 선언되면 내부 클래스라고 한다.

-   `익명 클래스 (Anonymous Inner Class)`<br>
    이름이 없는 클래스이며, 구현되지 않은 필드를 구현하기 위해서 일회성으로 생성되는 클래스이다.
