## 객체 지향 프로그래밍
현실세계를 모델링하기 위해 객체 개념을 사용
* 캡슐화
* 상속
* 다형성
* 추상화

### (1) 캡슐화
- 객체를 캡슐로 싸서 내부 보호, 외부 접근으로부터 안전
- 클래스 → 인스턴스 클래스 (필드, 메소드)
- 객체 = 클래스의 인스턴스
```java
- 필드를 private 선언
- getter , setter 사용
- 접근 제어자의 사용
```

### (2) 상속
- 자식클래스가 부모클래스를 물려 받음 부모클래스의 기능을 확장 하는 개념
- 부모클래스 = 슈퍼클래스
- 자식클래스 = 서브클래스
- 다중 상속 불가.
```java
public class Animal {}
public class Dog extends Animal {}
```

### (3) 다형성
- 메소드가 클래스/객체에 따라 다르게 구현되는 것
- 메소드 오버라이딩 : 재선언
- 메소드 오버로딩 : 중복 선언
```java
public class Animal {
    public void soundAnimal() {
        System.out.println("동물의 울음소리");
    }
}

public class Dog extends Animal {
    
    // 메서드 오버라이딩
    @Override
    public void soundAnimal() {
        System.out.println(getName() + "멍멍");
    }
    
}
```

### (4) 추상화
- 밑그림만 선언해두는 느낌이다. (세부사항은 숨김)
- abstract 와 interface 로 추상화 시키고 
- extends 와 implements 로 구현한다.
```java
abstract class Animal {
    String name;

    // 생성자
    public Animal(String name) {
        this.name = name;
    }

    // 추상 메서드 (구현 없음 → 서브클래스에서 반드시 구현)
    abstract void makeSound();

    // 일반 메서드 (구현이 있음)
    public void sleep() {
        System.out.println(name + " is sleeping.");
    }
}
```
```java
interface Animal {
    // 추상 메서드 (구현 없음)
    void makeSound();

    // 디폴트 메서드 (Java 8 이상, 기본 구현 제공 가능)
    default void sleep() {
        System.out.println("Sleeping...");
    }
}
```

---

## 객체지향 설계 원칙 (SOLID)
* Single Responsibility Principle (단일 책임 원칙): 클래스는 하나의 책임만 가져야 한다.
* Open/Closed Principle (개방-폐쇄 원칙): 기존 코드는 수정하지 않고 확장 가능해야 한다.
* Liskov Substitution Principle (리스코프 치환 원칙): 부모 클래스는 자식 클래스로 대체 가능해야 한다.
* Interface Segregation Principle (인터페이스 분리 원칙): 필요한 메서드만 포함한 인터페이스를 사용.
* Dependency Inversion Principle (의존 역전 원칙): 고수준 모듈은 저수준 모듈에 의존하지 않아야 한다.


---

## Class

**클래스 — class**

- 객체의 설계도, 틀 (데이터, 함수를 포함한 사용자 정의 데이터 타입)
- 속성(필드) 와 메소드로 이루어져있다.

```java
public class Person {
    private String name;
    private int age;

    // 메소드 (행동)
    public void displayInfo() {
        System.out.println("Name: " + name + ", Age: " + age);
    }
}
```

**객체 생성 방법**

 1. 객체에 대한 레퍼런스 변수 선언
   `Circle pizza;`
2. 객체 생성 (new 연산자)
   `pizza = new Circle();`

( 1+2. 선언 + 객체 동시에 하기)
`Circle pizza = new Circle();`


3. 접근 (. 점 연산자 )
   `pizza.name = "피자";`

---
## Variable

**지역 변수**

- 메서드 안에서 선언된 변수
- 반드시 초기화를 해야한다.

**멤버 변수 (필드)**

- 클래스 내부에 선언된 변수
- 객체의 상태를 나타낸다.
- 객체 생성 시 각 테이터 타입에 맞게 자동 초기화 된다.

**참조 변수**

- 객체를 가리키는 변수 , 객체의 메모리 주소 저장
- `MyClass obj = new MyClass();`

---

## Method


**멤버 함수 (메서드)**
- 클래스 내부에 정의된 함수
- 객체의 행동을 나타낸다.

**메서드 method**
- 클래스 내부에 정의 된 함수, 객체의 행위 (Behavior) 정의
- 메서드는 객체 지향의 핵심 요소  = 캡슐화 / 재사용성 / 모듈화 / 추상화

**메서드 선언 방법**
- 클래스 내부에 정의

```java
접근제어자 반환타입 메서드이름 (매개변수){
		//본체
}

public int add(int a, int b) {
    // 메소드 본체
}
```
---
## Constructor
**생성자  — (new)**

- 객체가 생성될 떄 초기화를 위해 실행되는 메서드
- 클래스 이름과 동일해야한다.
- 리턴 타입 지정 불가능하다.
- 객체 생성 시 한번만 호출된다.
- 여러 개 작성 가능하다. —-(생성자 오버로딩)

**기본생성자 = 디폴트생성자**

- 매개변수가 없는 단순 리턴 생성자이다.
- 클래스에 생성자가 하나도 없으면 (컴파일오류)
  JVM이 자동으로 생성 해줌
- 생성자가 하나라도 존재하면 자동 생성 안됨

---
## Parameter , Return Type

**매개변수 parameter**

- 메소드가 호출될 때 전달되는 값을 받기 위해 사용되는 변수
- 메소드가 실행될 때 해당 값이 할당됨

**반환 유형 return type**

- 메소드가 실행이 완료되면 호출자에게 돌려주는 값의 데이터 타입
- 기본 데이터 타입 - int, double, char, boolean 등
- 참조 데이터 타입 - 객체, 배열, 클래스 등
- void - 값 반환 하지 않음

**return**

- 값의 반환
- 메서드 종료 (void형 메서드에서)

**기본 타입  primitive type**

- 정수, 실수, 문자, 논리 값을 저장하는 데이터 타입
- 실제 값(value) 저장

**참조 타입  reference type**

- 배열, 클래스, 인터페이스 타입
- 메모리의 주소값 저장
- 스택(stack)영역에 주소값을 저장하고 내부의 실제 값은 힙(heap) 영역에 저장


---

## Garbage & Collection

**가비지**

- 할당 받은 객체, 배열 메모리 중 더이상 사용하지 않게된 메모리
- 참조하는 레퍼런스가 하나도 없는 객체 / 배열을 가비지로 판단함

**가비지 컬렉션 (by 가비지 컬렉션 스레드)**

- 가비지가 많아지면 가용 메모리 양이 줄어듬, 일정 크기 이하로 줄어들면 JVM 이 자동으로 가비지 회수해서 가용메모리를 늘려줌
- System.gc(); //가비지 컬렉션 요청 (권장되지 않음, 내부 매커니즘에 맡기는 게 좋음)

---

## Package

**패키지 package  — (import)**

- import 사용  `import 패키지.*;`
- 서로 관련 있는 클래스를 하나의 디렉터리에 모아 놓은 것
- 자바 소스 파일 첫 줄에 와야 한다.
- 클래스 파일은 패키지에 소속 되어야 한다.
- 대분류와 소분류 패키지를 구분할 때는 .(dot)을 사용
- 소문자 권장, 키워드나 java로 시작 불가능



----

## this() 레퍼런스
- 객체 자기 자신에 대한 레퍼런스, 컴파일러에 의해 자동 관리 
- 다른 생성자 호출가능 this()
1. 생성자에서만 사용됨!
2. 반드시 같은 클래스의 다른 생성자!!를 호출할 때 사용
3. 반드시 생성자의 첫문장!!으로 사용되어야함

**this — (this. or this())**

- 객체 자기 자신에 대한 레퍼런스, 컴파일러에 의해 자동 관리 (첫줄에 와야함)
- **this.  :**  동일 클래스 내의 멤버변수, 메서드 참조 가능
- **this() :** 생성자 내부에서 자신의 다른 생성자 호출가능

**super — (super. or super())**

- 한단계 위 부모클래스의 객체를 지정할 때 사용하는 키워드 (첫줄에 와야함)
- **super.  :**  부모클래스 멤버 참조 가능
- **super() :** 생성자 내부에서만 사용, 부모클래스 생성자 호출

**this() , super()**

1. 생성자에서만 사용됨!
2. 반드시 같은 클래스의 다른 생성자!!를 호출할 때 사용
3. 반드시 생성자의 첫 문장!!으로 사용되어야함


## **객체 치환**
`ob1 = ob2`
- 객체 복사가 아님 X, 객체 참조를 다른 객체에 할당하는 것

1. b1 은 이제 ob2가 참조하는 객체를 참조하게 된다.
2. 기존의 ob1 의 객체는 아무도 가리키지 않음 접근 불가 상태 가비지가 되어 자동으로 수거돼 재사용됨.




## Access Modifiers

### 접근 지정자 

`private`
클래스 내에서만 접근 가능.
외부 클래스에서는 접근 불가.

`protected`
동일 패키지 내의 모든 클래스에서 접근 가능.
다른 패키지의 자식 클래스에서 접근 가능.

`public`
모든 클래스에서 접근 가능.
다른 패키지와 관계없이 어디서든 접근할 수 있음.

`default (생략)`
동일 패키지 내에서만 접근 가능.
다른 패키지에서는 접근 불가.


### 멤버(필드/메소드)에 대한 접근 지정자 순서

`private < default < protected < public`

* private: 해당 클래스 내에서만 접근 가능.
* default (생략): 동일 패키지 내에서만 접근 가능.
* protected: 동일 패키지 내 또는 다른 패키지의 자식 클래스에서 접근 가능.
* public: 모든 클래스에서 접근 가능.

### 클래스에 대한 접근 지정자

`public`
다른 패키지에서도 접근 가능.
클래스가 public으로 선언되면, 다른 패키지에서 자유롭게 사용할 수 있음.

`default (생략)`
동일 패키지 내에서만 접근 가능.
다른 패키지에서는 접근 불가.

---

## static 멤버 (클래스 멤버)
static 키워드를 사용하여 정의된 멤버는 클래스 레벨에서 공유되는 변수나 메소드
* **독립적인 공간 할당**: 클래스 로딩 시 메모리 공간이 할당되며, 객체의 생성과 관계없이 존재.
* **클래스당 하나만 생성됨**: 하나의 클래스에 대해서 단 하나의 static 멤버만 존재.
* **객체 생성 전에도 존재**: 프로그램 시작 시 클래스가 로딩되면 static 멤버는 이미 존재.
* **객체 소멸과 관계없음**: 객체가 소멸해도 static 멤버는 계속 존재하며, 프로그램 종료 시 소멸.
* **모든 객체들에 의해 공유됨**: 모든 객체는 같은 static 멤버를 참조하므로, 클래스 이름을 통해서 접근하거나, 객체를 통해서 접근할 수 있음.

### Static 주의 사항
* static 멤버는 static 메소드에서만 접근 가능:
 static 메소드에서는 static 변수와 static 메소드에만 접근할 수 있습니다.

* static 멤버는 인스턴스 멤버에서 접근 가능:
인스턴스 멤버는 static 멤버에 자유롭게 접근할 수 있습니다.

* static 메소드에서는 this 사용 불가:
static 메소드는 클래스 차원에서 실행되기 때문에, 인스턴스를 나타내는 this를 사용할 수 없습니다.
---

## **final 키워드**

1.  final 클래스 : 상속 X
2.  final 메소드 : 오버라이딩 X
3.  final 필드 : 상수화

- static 키워드와의 혼동:
static 필드는 클래스 수준에서 초기화되며, 모든 객체가 공유합니다. 
- 반면, 인스턴스 필드는 각 객체마다 별도로 초기화됩니다.



