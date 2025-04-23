# 변수와 상수

## 변수

변수란 데이터를 저장하기 위한 메모리 공간에 이름을 붙인 것으로, 값이 변할 수 있는 데이터를 저장하는 공간이다. Java에서 변수는 타입과 함께 선언되며, 선언된 타입의 값만 저장할 수 있다.

```java
// 변수 선언과 초기화
int age = 25;
String name = "홍길동";
double height = 175.5;
```


## 상수

상수란 한 번 값이 할당되면 더 이상 값을 변경할 수 없는 변수를 말한다. Java에서는 `final` 키워드를 사용하여 상수를 선언한다. 상수 이름은 대문자와 언더스코어(_)를 사용하는 것이 관례이다.

```java
// 상수 선언
final double PI = 3.14159;
final int MAX_USERS = 10000;
```


## 변수 명명 규칙

- 영문자, 숫자, 언더스코어(_), 달러(\$)만 사용 가능
- 첫 글자는 숫자로 시작할 수 없음
- 예약어는 사용할 수 없음
- 클래스 이름은 대문자로 시작 (Pascal Case)
- 변수와 메소드 이름은 소문자로 시작 (Camel Case)
- 상수는 모두 대문자와 언더스코어 사용 (SNAKE_CASE)


# 기본 자료형

자바의 자료형은 기본 자료형(Primitive Type)과 참조 자료형(Reference Type)으로 나뉜다. 기본 자료형은 실제 값을 저장하는 반면, 참조 자료형은 메모리 주소를 저장한다.

## 정수 자료형

정수 자료형은 소수점이 없는 정수 값을 저장하는 데 사용된다.


| 자료형 | 크기 | 저장할 수 있는 값의 유효 범위 |
| :-- | :-- | :-- |
| byte | 1 바이트 | -128 ~ 127 |
| short | 2 바이트 | -32,768 ~ 32,767 |
| int | 4 바이트 | -2,147,483,648 ~ 2,147,483,647 |
| long | 8 바이트 | -9,223,372,036,854,775,808 ~ 9,223,372,036,854,775,807 |

```java
// 정수 자료형 예시
byte b = 100;
short s = 30000;
int i = 2000000000;
long l = 9000000000000000000L; // long 형은 값 뒤에 L 또는 l을 붙임
```


## 실수 자료형

실수 자료형은 소수점이 있는 숫자를 저장하는 데 사용된다. 부동 소수점 방식으로 표현한다.


| 자료형 | 크기 | 저장할 수 있는 값의 유효 범위 | 정밀도 |
| :-- | :-- | :-- | :-- |
| float | 4 바이트 | 약 ±3.40282347E+38F | 7자리 정밀도 |
| double | 8 바이트 | 약 ±1.7976931348623157E+308 | 15자리 정밀도 |

```java
// 실수 자료형 예시
float f = 3.14f;  // float 형은 값 뒤에 F 또는 f를 붙임
double d = 3.141592653589793;
```


## 문자 자료형

문자 하나를 저장하는 데 사용되며, Unicode 문자를 저장할 수 있다.


| 자료형 | 크기 | 저장할 수 있는 값의 유효 범위 |
| :-- | :-- | :-- |
| char | 2 바이트 | 0 ~ 65,535 (유니코드) |

```java
// 문자 자료형 예시
char c1 = 'A';
char c2 = '가';
char c3 = '\u0041'; // 유니코드 표현 (A)
```


## 논리 자료형

참과 거짓 값을 저장하는 데 사용된다.


| 자료형 | 크기 | 저장할 수 있는 값 |
| :-- | :-- | :-- |
| boolean | 1 바이트 | true, false |

```java
// 논리 자료형 예시
boolean isTrue = true;
boolean isFalse = false;
```


# 참조 자료형

참조 자료형은 기본 자료형이 아닌 모든 자료형을 말하며, 객체의 주소를 저장한다. 클래스, 인터페이스, 배열, 열거형 등이 참조 자료형에 해당한다.

## 문자열(String)

문자열은 Java에서 가장 많이 사용되는 참조 자료형 중 하나이다. 문자열은 쌍따옴표("")로 표현한다.

```java
// 문자열 참조 자료형 예시
String greeting = "안녕하세요";
String name = new String("홍길동");
```


## 배열(Array)

같은 타입의 여러 변수를 하나의 묶음으로 다루는 자료형이다.

```java
// 배열 참조 자료형 예시
int[] numbers = {1, 2, 3, 4, 5};
String[] names = new String[^3];
names[^0] = "Kim";
names[^1] = "Lee";
names[^2] = "Park";
```


## 클래스(Class)

사용자 정의 자료형으로, 속성(필드)과 기능(메소드)을 가질 수 있다.

```java
// 클래스 예시
class Person {
    String name;
    int age;
    
    void introduce() {
        System.out.println("내 이름은 " + name + "이고, 나이는 " + age + "세 입니다.");
    }
}

// 클래스 사용
Person person = new Person();
person.name = "홍길동";
person.age = 30;
person.introduce();
```


## 인터페이스(Interface)

추상 메소드의 집합으로, 구현 클래스에서 반드시 구현해야 하는 메소드들을 정의한다.

```java
// 인터페이스 예시
interface Movable {
    void move(int x, int y);
}

// 인터페이스 구현
class Car implements Movable {
    @Override
    public void move(int x, int y) {
        System.out.println("차가 (" + x + ", " + y + ")로 이동합니다.");
    }
}
```


# 연산자

연산자는 데이터를 처리하여 결과를 산출하는 기호를 말한다. Java에서는 다양한 연산자를 제공한다.

## 산술 연산자

수학적인 계산을 수행하는 연산자이다.


| 연산자 | 설명 | 예시 | 결과 |
| :-- | :-- | :-- | :-- |
| + | 덧셈 | 10 + 5 | 15 |
| - | 뺄셈 | 10 - 5 | 5 |
| * | 곱셈 | 10 * 5 | 50 |
| / | 나눗셈 | 10 / 5 | 2 |
| % | 나머지 | 10 % 3 | 1 |

## 대입 연산자

변수에 값을 할당하는 연산자이다.


| 연산자 | 설명 | 예시 | 동일 표현 |
| :-- | :-- | :-- | :-- |
| = | 변수에 값을 할당 | x = 10 | x = 10 |
| += | 덧셈 후 할당 | x += 5 | x = x + 5 |
| -= | 뺄셈 후 할당 | x -= 5 | x = x - 5 |
| *= | 곱셈 후 할당 | x *= 5 | x = x * 5 |
| /= | 나눗셈 후 할당 | x /= 5 | x = x / 5 |
| %= | 나머지 연산 후 할당 | x %= 5 | x = x % 5 |

## 증감 연산자

변수의 값을 1 증가시키거나 감소시키는 연산자이다.


| 연산자 | 설명 | 예시 |
| :-- | :-- | :-- |
| ++ | 1 증가 | ++x (전위), x++ (후위) |
| -- | 1 감소 | --x (전위), x-- (후위) |

```java
// 증감 연산자 예시
int a = 5;
System.out.println(++a); // 6 (증가 후 사용)
int b = 5;
System.out.println(b++); // 5 (사용 후 증가)
System.out.println(b);   // 6
```


## 비교 연산자

두 값을 비교하여 true 또는 false 결과를 반환하는 연산자이다.


| 연산자 | 설명 | 예시 |
| :-- | :-- | :-- |
| == | 같음 | x == y |
| != | 다름 | x != y |
| > | 큼 | x > y |
| < | 작음 | x < y |
| >= | 크거나 같음 | x >= y |
| <= | 작거나 같음 | x <= y |

## 논리 연산자

논리적인 조건을 결합하는 연산자이다.


| 연산자 | 설명 | 예시 |
| :-- | :-- | :-- |
| \&\& | AND (모두 참이면 참) | x > 0 \&\& y > 0 |
| \|\| | OR (하나라도 참이면 참) | x > 0 \|\| y > 0 |
| ! | NOT (참/거짓 반전) | !(x > 0) |

## 비트 연산자

비트 단위로 연산을 수행하는 연산자이다.


| 연산자 | 설명 | 예시 |
| :-- | :-- | :-- |
| \& | 비트 AND | x \& y |
| \| | 비트 OR | x \| y |
| ^ | 비트 XOR | x ^ y |
| ~ | 비트 NOT | ~x |
| << | 왼쪽 시프트 | x << 2 |
| >> | 오른쪽 시프트 | x >> 2 |
| >>> | 부호 없는 오른쪽 시프트 | x >>> 2 |

# 제어문

제어문은 프로그램의 실행 흐름을 제어하는 구문이다. 조건문과 반복문으로 나눌 수 있다.

## 조건문

### if 문

조건이 참일 경우 지정된 블록의 코드를 실행한다.

```java
// 기본 if 문
if (조건) {
    // 조건이 참일 때 실행할 코드
}

// if-else 문
if (조건) {
    // 조건이 참일 때 실행할 코드
} else {
    // 조건이 거짓일 때 실행할 코드
}

// if-else if-else 문
if (조건1) {
    // 조건1이 참일 때 실행할 코드
} else if (조건2) {
    // 조건1이 거짓이고 조건2가 참일 때 실행할 코드
} else {
    // 모든 조건이 거짓일 때 실행할 코드
}
```


### switch 문

식의 값에 따라 여러 경우 중 하나를 선택하여 실행한다.

```java
switch (식) {
    case 값1:
        // 식의 결과가 값1일 때 실행할 코드
        break;
    case 값2:
        // 식의 결과가 값2일 때 실행할 코드
        break;
    default:
        // 일치하는 case가 없을 때 실행할 코드
}
```


## 반복문

### for 문

지정된 횟수만큼 코드 블록을 반복한다.

```java
for (초기화; 조건; 증감) {
    // 반복할 코드
}

// 예시
for (int i = 0; i &lt; 5; i++) {
    System.out.println(i);
}
```


### 향상된 for 문 (for-each)

배열이나 컬렉션의 모든 요소를 순회한다.

```java
for (요소타입 변수명 : 배열 또는 컬렉션) {
    // 반복할 코드
}

// 예시
int[] numbers = {1, 2, 3, 4, 5};
for (int num : numbers) {
    System.out.println(num);
}
```


### while 문

조건이 참인 동안 코드 블록을 반복한다.

```java
while (조건) {
    // 반복할 코드
}

// 예시
int i = 0;
while (i &lt; 5) {
    System.out.println(i);
    i++;
}
```


### do-while 문

코드 블록을 최소 한 번 실행한 후, 조건이 참인 동안 계속 반복한다.

```java
do {
    // 반복할 코드
} while (조건);

// 예시
int i = 0;
do {
    System.out.println(i);
    i++;
} while (i &lt; 5);
```


## 분기문

### break

반복문이나 switch 문을 즉시 종료한다.

```java
for (int i = 0; i &lt; 10; i++) {
    if (i == 5) {
        break; // i가 5일 때 반복문 종료
    }
    System.out.println(i);
}
```


### continue

현재 반복을 건너뛰고 다음 반복으로 진행한다.

```java
for (int i = 0; i &lt; 10; i++) {
    if (i % 2 == 0) {
        continue; // i가 짝수이면 출력하지 않고 다음 반복으로
    }
    System.out.println(i);
}
```


# 배열

배열은 같은 타입의 여러 변수를 하나의 묶음으로 다루는 자료구조이다.

## 배열 선언 및 초기화

```java
// 배열 선언
타입[] 변수명;
타입 변수명[];

// 배열 생성
변수명 = new 타입[크기];

// 배열 선언과 생성을 동시에
타입[] 변수명 = new 타입[크기];

// 배열 초기화와 함께 선언
타입[] 변수명 = {값1, 값2, 값3, ...};
타입[] 변수명 = new 타입[]{값1, 값2, 값3, ...};
```

예시:

```java
// 정수 배열 선언과 초기화
int[] numbers = new int[^5]; // 크기가 5인 정수 배열 생성
numbers[^0] = 10;
numbers[^1] = 20;
numbers[^2] = 30;
numbers[^3] = 40;
numbers[^4] = 50;

// 초기값을 지정한 배열 선언
int[] scores = {95, 85, 90, 80, 75};

// 문자열 배열
String[] names = {"홍길동", "김철수", "이영희"};
```


## 다차원 배열

2차원 이상의 배열을 다차원 배열이라고 한다.

```java
// 2차원 배열 선언 및 초기화
int[][] matrix = new int[^3][^4]; // 3행 4열 배열

// 2차원 배열 초기화
int[][] matrix = {
    {1, 2, 3, 4},
    {5, 6, 7, 8},
    {9, 10, 11, 12}
};
```


## 배열 다루기

```java
// 배열 길이 구하기
int length = array.length;

// 배열 복사
int[] original = {1, 2, 3, 4, 5};
int[] copy = new int[original.length];
System.arraycopy(original, 0, copy, 0, original.length);

// 또는 Arrays 클래스 사용
int[] copy2 = Arrays.copyOf(original, original.length);

// 배열 정렬
Arrays.sort(array);

// 배열 내용 출력
System.out.println(Arrays.toString(array));
```


# 클래스와 객체

클래스는 객체를 생성하기 위한 템플릿이며, 객체는 클래스의 인스턴스이다.

## 클래스 정의

```java
[접근제한자] class 클래스명 {
    // 필드(멤버 변수)
    [접근제한자] 자료형 필드명;
    
    // 생성자
    [접근제한자] 클래스명([매개변수...]) {
        // 초기화 코드
    }
    
    // 메소드
    [접근제한자] 리턴타입 메소드명([매개변수...]) {
        // 실행 코드
    }
}
```


## 접근 제한자

| 접근제한자 | 같은 클래스 | 같은 패키지 | 자식 클래스 | 전체 |
| :-- | :-- | :-- | :-- | :-- |
| private | O | X | X | X |
| default | O | O | X | X |
| protected | O | O | O | X |
| public | O | O | O | O |

## 객체 생성 및 사용

```java
// 객체 생성
클래스명 변수명 = new 클래스명();

// 필드 접근
변수명.필드명 = 값;
값 = 변수명.필드명;

// 메소드 호출
변수명.메소드명(매개값...);
```

예시:

```java
public class Person {
    // 필드
    String name;
    int age;
    
    // 생성자
    public Person() {
        // 기본 생성자
    }
    
    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
    
    // 메소드
    void introduce() {
        System.out.println("내 이름은 " + name + "이고, 나이는 " + age + "세 입니다.");
    }
}

// 객체 생성 및 사용
Person person1 = new Person();
person1.name = "홍길동";
person1.age = 30;
person1.introduce();

Person person2 = new Person("김철수", 25);
person2.introduce();
```


# 상속

상속은 기존의 클래스를 재사용하여 새로운 클래스를 작성하는 것이다. 상속을 통해 코드의 재사용성을 높이고 클래스 간의 계층 구조를 형성할 수 있다.

## 상속 구현

```java
[접근제한자] class 자식클래스 extends 부모클래스 {
    // 필드와 메소드
}
```


## 메소드 오버라이딩

부모 클래스의 메소드를 자식 클래스에서 재정의하는 것이다.

```java
@Override
[접근제한자] 리턴타입 메소드명([매개변수...]) {
    // 재정의된 코드
}
```


## super 키워드

super는 부모 클래스의 멤버에 접근하는 데 사용된다.

```java
// 부모 생성자 호출
super([매개값...]);

// 부모 메소드 호출
super.메소드명([매개값...]);

// 부모 필드 접근
super.필드명;
```

예시:

```java
// 부모 클래스
class Animal {
    String name;
    
    Animal(String name) {
        this.name = name;
    }
    
    void sound() {
        System.out.println("동물이 소리를 냅니다.");
    }
}

// 자식 클래스
class Dog extends Animal {
    String breed;
    
    Dog(String name, String breed) {
        super(name); // 부모 생성자 호출
        this.breed = breed;
    }
    
    @Override
    void sound() {
        System.out.println(name + "이(가) 멍멍 짖습니다.");
    }
    
    void showInfo() {
        System.out.println("이름: " + name);
        System.out.println("품종: " + breed);
    }
}

// 사용 예
Dog dog = new Dog("멍멍이", "진돗개");
dog.sound(); // 오버라이딩된 메소드 호출
dog.showInfo();
```


# 인터페이스

인터페이스는 클래스가 구현해야 하는 메소드들을 정의한 추상적인 타입이다. 다중 상속과 유사한 효과를 낼 수 있다.

## 인터페이스 정의

```java
[접근제한자] interface 인터페이스명 {
    // 상수 필드
    타입 상수명 = 값;
    
    // 추상 메소드
    리턴타입 메소드명([매개변수...]);
    
    // 디폴트 메소드 (Java 8 이상)
    default 리턴타입 메소드명([매개변수...]) {
        // 실행 코드
    }
    
    // 정적 메소드 (Java 8 이상)
    static 리턴타입 메소드명([매개변수...]) {
        // 실행 코드
    }
}
```


## 인터페이스 구현

```java
[접근제한자] class 클래스명 implements 인터페이스명1, 인터페이스명2, ... {
    // 인터페이스의 추상 메소드 구현
    @Override
    public 리턴타입 메소드명([매개변수...]) {
        // 실행 코드
    }
}
```

예시:

```java
// 인터페이스 정의
interface Flyable {
    void fly();
}

interface Swimmable {
    void swim();
}

// 인터페이스 구현
class Duck implements Flyable, Swimmable {
    @Override
    public void fly() {
        System.out.println("오리가 날아갑니다.");
    }
    
    @Override
    public void swim() {
        System.out.println("오리가 수영합니다.");
    }
}

// 사용 예
Duck duck = new Duck();
duck.fly();
duck.swim();

// 인터페이스 타입으로 참조 가능
Flyable flyableDuck = new Duck();
flyableDuck.fly(); // 인터페이스에 정의된 메소드만 호출 가능
```


# 예외 처리

예외 처리는 프로그램 실행 중 발생할 수 있는 오류를 처리하는 방법이다. Java에서는 try-catch-finally 블록을 사용하여 예외를 처리한다.

## try-catch-finally

```java
try {
    // 예외가 발생할 수 있는 코드
} catch (예외타입1 변수명) {
    // 예외타입1 예외가 발생했을 때 실행할 코드
} catch (예외타입2 변수명) {
    // 예외타입2 예외가 발생했을 때 실행할 코드
} finally {
    // 예외 발생 여부와 상관없이 항상 실행할 코드
}
```


## 예외 던지기

```java
[접근제한자] 리턴타입 메소드명([매개변수...]) throws 예외타입1, 예외타입2, ... {
    // 메소드 내용
    if (예외조건) {
        throw new 예외타입("예외 메시지");
    }
}
```


## 사용자 정의 예외

```java
// 사용자 정의 예외 클래스
public class 예외클래스명 extends Exception {
    public 예외클래스명() {
        super();
    }
    
    public 예외클래스명(String message) {
        super(message);
    }
}
```

예시:

```java
// 사용자 정의 예외
class InsufficientFundsException extends Exception {
    public InsufficientFundsException(String message) {
        super(message);
    }
}

// 예외 발생 및 처리
class BankAccount {
    private double balance;
    
    public BankAccount(double initialBalance) {
        this.balance = initialBalance;
    }
    
    public void withdraw(double amount) throws InsufficientFundsException {
        if (amount &gt; balance) {
            throw new InsufficientFundsException("잔액이 부족합니다: " + balance);
        }
        balance -= amount;
        System.out.println("출금 완료: " + amount);
    }
}

// 사용 예
try {
    BankAccount account = new BankAccount(1000);
    account.withdraw(1500); // 예외 발생
} catch (InsufficientFundsException e) {
    System.out.println("예외 발생: " + e.getMessage());
} finally {
    System.out.println("거래 완료");
}
```


# 컬렉션

컬렉션은 객체를 효율적으로 저장, 관리하기 위한 자료구조를 제공하는 프레임워크이다.

## List

순서가 있는 데이터의 집합으로, 중복을 허용한다.


| 구현 클래스 | 특징 |
| :-- | :-- |
| ArrayList | 배열 기반, 검색이 빠름 |
| LinkedList | 연결 리스트 기반, 추가/삭제가 빠름 |
| Vector | 스레드 안전, 동기화됨 |
| Stack | Vector를 상속받음, LIFO 구조 |

```java
// ArrayList 사용 예
List&lt;String&gt; nameList = new ArrayList&lt;&gt;();
nameList.add("홍길동");
nameList.add("김철수");
nameList.add("이영희");

for (String name : nameList) {
    System.out.println(name);
}
```


## Set

순서가 없는 데이터의 집합으로, 중복을 허용하지 않는다.


| 구현 클래스 | 특징 |
| :-- | :-- |
| HashSet | 해시 테이블에 저장, 가장 빠름 |
| LinkedHashSet | 삽입 순서 유지 |
| TreeSet | 정렬된 순서로 저장, 검색이 느림 |

```java
// HashSet 사용 예
Set&lt;Integer&gt; numberSet = new HashSet&lt;&gt;();
numberSet.add(10);
numberSet.add(20);
numberSet.add(10); // 중복 값은 저장되지 않음

for (Integer number : numberSet) {
    System.out.println(number);
}
```


## Map

키와 값의 쌍으로 이루어진 데이터의 집합으로, 키는 중복을 허용하지 않는다.


| 구현 클래스 | 특징 |
| :-- | :-- |
| HashMap | 해시 테이블에 저장, 가장 빠름 |
| LinkedHashMap | 삽입 순서 유지 |
| TreeMap | 정렬된 키 순서로 저장 |
| Hashtable | 스레드 안전, 동기화됨 |

```java
// HashMap 사용 예
Map&lt;String, Integer&gt; scoreMap = new HashMap&lt;&gt;();
scoreMap.put("홍길동", 90);
scoreMap.put("김철수", 80);
scoreMap.put("이영희", 95);

for (Map.Entry&lt;String, Integer&gt; entry : scoreMap.entrySet()) {
    System.out.println(entry.getKey() + ": " + entry.getValue());
}
```


# 제네릭

제네릭은 클래스, 인터페이스, 메소드를 정의할 때 타입 파라미터를 사용하는 기법이다. 컴파일 시점에 타입 안정성을 보장한다.

## 제네릭 클래스

```java
public class 클래스명&lt;T&gt; {
    private T t;
    
    public void set(T t) {
        this.t = t;
    }
    
    public T get() {
        return t;
    }
}
```


## 제네릭 메소드

```java
public &lt;T&gt; T 메소드명(T t) {
    return t;
}
```


## 제한된 타입 파라미터

```java
public class 클래스명&lt;T extends 상위타입&gt; {
    // 클래스 내용
}
```

예시:

```java
// 제네릭 클래스
class Box&lt;T&gt; {
    private T item;
    
    public void set(T item) {
        this.item = item;
    }
    
    public T get() {
        return item;
    }
}

// 제한된 타입 파라미터
class NumberBox&lt;T extends Number&gt; {
    private T item;
    
    public void set(T item) {
        this.item = item;
    }
    
    public T get() {
        return item;
    }
    
    public double getDoubleValue() {
        return item.doubleValue();
    }
}

// 사용 예
Box&lt;String&gt; stringBox = new Box&lt;&gt;();
stringBox.set("Hello");
String str = stringBox.get();

NumberBox&lt;Integer&gt; intBox = new NumberBox&lt;&gt;();
intBox.set(10);
double value = intBox.getDoubleValue();
```


# 람다식

람다식은 함수를 간결하게 표현하는 방식으로, Java 8부터 도입되었다. 주로 함수형 인터페이스와 함께 사용된다.

## 람다식 문법

```java
(매개변수...) -&gt; { 실행문; }
```


## 함수형 인터페이스

하나의 추상 메소드만 가지는 인터페이스로, @FunctionalInterface 어노테이션으로 표시할 수 있다.


| 인터페이스 | 메소드 | 설명 |
| :-- | :-- | :-- |
| Runnable | void run() | 매개변수와 반환값이 없음 |
| Supplier<T> | T get() | 매개변수는 없고 반환값이 있음 |
| Consumer<T> | void accept(T t) | 매개변수는 있고 반환값이 없음 |
| Function<T, R> | R apply(T t) | 매개변수와 반환값이 있음 |
| Predicate<T> | boolean test(T t) | 조건식을 표현하는데 사용 |

예시:

```java
// 함수형 인터페이스
@FunctionalInterface
interface Calculator {
    int calculate(int x, int y);
}

// 람다식 사용
public class LambdaExample {
    public static void main(String[] args) {
        // 익명 클래스
        Calculator addition = new Calculator() {
            @Override
            public int calculate(int x, int y) {
                return x + y;
            }
        };
        
        // 람다식
        Calculator subtraction = (x, y) -&gt; x - y;
        
        // 사용
        System.out.println("덧셈: " + addition.calculate(10, 5));
        System.out.println("뺄셈: " + subtraction.calculate(10, 5));
        
        // 자바 표준 함수형 인터페이스 사용
        Consumer&lt;String&gt; print = (message) -&gt; System.out.println(message);
        print.accept("Hello Lambda!");
        
        Predicate&lt;Integer&gt; isPositive = (n) -&gt; n &gt; 0;
        System.out.println(isPositive.test(10));
        
        Function&lt;Integer, Integer&gt; square = (n) -&gt; n * n;
        System.out.println(square.apply(5));
    }
}
```


# 스트림

스트림은 컬렉션, 배열 등의 데이터를 처리하기 위한 일련의 연산을 제공하는 API로, Java 8부터 도입되었다. 함수형 프로그래밍 방식을 지원한다.

## 스트림 생성

```java
// 컬렉션에서 스트림 생성
List&lt;String&gt; list = Arrays.asList("a", "b", "c");
Stream&lt;String&gt; stream = list.stream();

// 배열에서 스트림 생성
String[] array = {"a", "b", "c"};
Stream&lt;String&gt; stream = Arrays.stream(array);

// Stream.of() 메소드 사용
Stream&lt;String&gt; stream = Stream.of("a", "b", "c");
```


## 중간 연산

중간 연산은 다른 스트림을 반환하며, 여러 연산을 연결할 수 있다.


| 연산 | 설명 |
| :-- | :-- |
| filter() | 조건에 맞는 요소 필터링 |
| map() | 요소를 변환 |
| sorted() | 요소 정렬 |
| distinct() | 중복 제거 |
| limit() | 요소 개수 제한 |
| skip() | 요소 건너뛰기 |

## 최종 연산

최종 연산은 스트림의 요소를 소모하며, 스트림이 닫히게 된다.


| 연산 | 설명 |
| :-- | :-- |
| forEach() | 각 요소에 대해 작업 수행 |
| count() | 요소 개수 반환 |
| collect() | 요소를 수집하여 다른 형태로 변환 |
| reduce() | 요소를 하나로 줄임 |
| anyMatch() | 조건을 만족하는 요소가 하나라도 있는지 확인 |
| allMatch() | 모든 요소가 조건을 만족하는지 확인 |
| noneMatch() | 모든 요소가 조건을 만족하지 않는지 확인 |

예시:

```java
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

public class StreamExample {
    public static void main(String[] args) {
        List&lt;String&gt; names = Arrays.asList("홍길동", "김철수", "이영희", "박지성", "손흥민");
        
        // 이름이 "김"으로 시작하는 사람 필터링
        List&lt;String&gt; filteredNames = names.stream()
            .filter(name -&gt; name.startsWith("김"))
            .collect(Collectors.toList());
        System.out.println(filteredNames);
        
        // 이름의 길이를 추출
        List&lt;Integer&gt; nameLengths = names.stream()
            .map(String::length)
            .collect(Collectors.toList());
        System.out.println(nameLengths);
        
        // 이름이 3글자인 사람 수 계산
        long count = names.stream()
            .filter(name -&gt; name.length() == 3)
            .count();
        System.out.println("3글자 이름 수: " + count);
        
        // 이름을 알파벳 순으로 정렬
        List&lt;String&gt; sortedNames = names.stream()
            .sorted()
            .collect(Collectors.toList());
        System.out.println(sortedNames);
    }
}
```


# 쓰레드

쓰레드는 프로세스 내에서 실행되는 흐름의 단위로, 멀티쓰레드 프로그래밍을 통해 동시에 여러 작업을 수행할 수 있다.

## 쓰레드 생성

### Thread 클래스 상속

```java
class MyThread extends Thread {
    @Override
    public void run() {
        // 쓰레드가 실행할 코드
    }
}

// 사용
MyThread thread = new MyThread();
thread.start();
```


### Runnable 인터페이스 구현

```java
class MyRunnable implements Runnable {
    @Override
    public void run() {
        // 쓰레드가 실행할 코드
    }
}

// 사용
Thread thread = new Thread(new MyRunnable());
thread.start();

// 람다식 사용
Thread thread = new Thread(() -&gt; {
    // 쓰레드가 실행할 코드
});
thread.start();
```


## 쓰레드 생명주기

| 상태 | 설명 |
| :-- | :-- |
| NEW | 쓰레드가 생성되었지만 아직 시작되지 않음 |
| RUNNABLE | 쓰레드가 실행 중이거나 실행 가능한 상태 |
| BLOCKED | 쓰레드가 모니터 락을 기다리며 차단된 상태 |
| WAITING | 쓰레드가 다른 쓰레드의 특정 작업 완료를 무기한 기다림 |
| TIMED_WAITING | 쓰레드가 다른 쓰레드의 특정 작업 완료를 일정 시간 동안 기다림 |
| TERMINATED | 쓰레드가 실행을 완료한 상태 |

## 쓰레드 동기화

### synchronized 키워드

```java
// 메소드 동기화
public synchronized void method() {
    // 동기화된 코드
}

// 블록 동기화
public void method() {
    synchronized(객체) {
        // 동기화된 코드
    }
}
```


### wait(), notify(), notifyAll()

쓰레드 간 통신을 위한 메소드로, Object 클래스에 정의되어 있다.

```java
// wait() - 쓰레드를 일시 정지 상태로 만듦
synchronized(객체) {
    객체.wait();
}

// notify() - 대기 중인 쓰레드 중 하나를 깨움
synchronized(객체) {
    객체.notify();
}

// notifyAll() - 대기 중인 모든 쓰레드를 깨움
synchronized(객체) {
    객체.notifyAll();
}
```

예시:

```java
class SharedResource {
    private int value = 0;
    private boolean available = false;
    
    public synchronized int get() {
        while (!available) {
            try {
                wait();
            } catch (InterruptedException e) {
                Thread.currentThread().interrupt();
            }
        }
        available = false;
        notify();
        return value;
    }
    
    public synchronized void put(int value) {
        while (available) {
            try {
                wait();
            } catch (InterruptedException e) {
                Thread.currentThread().interrupt();
            }
        }
        this.value = value;
        available = true;
        notify();
    }
}

class Producer implements Runnable {
    private SharedResource resource;
    
    public Producer(SharedResource resource) {
        this.resource = resource;
    }
    
    @Override
    public void run() {
        for (int i = 0; i &lt; 10; i++) {
            resource.put(i);
            System.out.println("생산: " + i);
            try {
                Thread.sleep(100);
            } catch (InterruptedException e) {
                Thread.currentThread().interrupt();
            }
        }
    }
}

class Consumer implements Runnable {
    private SharedResource resource;
    
    public Consumer(SharedResource resource) {
        this.resource = resource;
    }
    
    @Override
    public void run() {
        for (int i = 0; i &lt; 10; i++) {
            int value = resource.get();
            System.out.println("소비: " + value);
            try {
                Thread.sleep(100);
            } catch (InterruptedException e) {
                Thread.currentThread().interrupt();
            }
        }
    }
}

// 사용
SharedResource resource = new SharedResource();
Thread producerThread = new Thread(new Producer(resource));
Thread consumerThread = new Thread(new Consumer(resource));
producerThread.start();
consumerThread.start();
```

