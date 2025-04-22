<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" class="logo" width="120"/>

# C\# 학습 노트

이 학습 노트는 C\# 프로그래밍 언어의 기본 개념부터 고급 기능까지 포괄적으로 다룹니다. 개념별로 구조화된 내용을 통해 C\#을 체계적으로 학습할 수 있습니다.

## C\# 소개

C\#은 마이크로소프트에서 개발한 현대적인 객체 지향 프로그래밍 언어입니다. .NET 프레임워크 기반으로 동작하며 다양한 애플리케이션 개발에 사용됩니다.

### C\#의 특징

- C++에서 파생된 객체 지향 언어[^3]
- 형식 안정성(객체지향언어는 형식의 안정성이 있음)[^4]
- Java의 특징 + C, C++[^4]


### C\#의 장점

- 입문자에게 적합한 언어[^4]
- 메모리 관리가 쉽다(Garbage Collector)[^4]
- 다양한 라이브러리 지원[^4]


### .NET 프레임워크

C\#을 통해 프로그래밍을 합니다. 컴파일까지만 해주면 나머지는 컴퓨터가 기계어로 바꿔준 후 운영체제로 넘기기 때문에 맥과 윈도우 모두 호환이 가능합니다[^4].

## 프로그램 구조

C\# 프로그램은 하나 이상의 파일로 구성됩니다. 각 파일에는 0개 이상의 네임스페이스가 포함됩니다. 네임스페이스에는 클래스, 구조체, 인터페이스, 열거형, 대리자 등의 형식이 포함됩니다[^5].

### 기본 구조

```csharp
using System;

namespace YourNamespace
{
    class YourClass
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello world!");
        }
    }
}
```

최신 C\#에서는 최상위 문을 사용할 수도 있습니다:

```csharp
using System;

Console.WriteLine("Hello world!");
```


## 변수

변수란 변화하기 쉬운 값 또는 변화하는 값을 저장할 때 사용하는 식별자를 뜻합니다. 데이터를 저장하는 공간으로, 데이터 형식과 식별자(이름)로 구성됩니다[^4].

### 변수 선언

```csharp
데이터형식 변수명;
```

예: `int num;`

### 지역 변수

{ }(브레이스) 코드블록 내부에 선언되고 코드블록 외부에서는 사용불가한 변수입니다[^4].

## 상수

상수란 변화하지 않는 고유의 값을 뜻합니다. 변수와 달리 한번 정해지면 변하지 않습니다[^4].

### 상수 선언

```csharp
const 자료형 변수명 = 값;
```

예:

```csharp
const int NUM = 100;
const string LINE = "------------";
```

상수는 주로 대문자로 표기합니다[^4].

## 자료형

### 정수 자료형

정수 자료형은 양의 정수와 음의 정수를 다룰 때 사용합니다. 정수 자료형 변수에 실수를 대입하게 되면 소수점 이하 숫자는 무시되어 처리되므로 주의해야 합니다.


| 자료형 | 의미 | 크기 | 저장할 수 있는 값의 유효 범위 |
| :-- | :-- | :-- | :-- |
| byte | byte | 1 바이트 | 0 ~ 255 |
| sbyte | signed byte | 1 바이트 | -128 ~ 127 |
| short | signed short | 2 바이트 | -32,768 ~ 32,767 |
| ushort | unsigned short | 2 바이트 | 0 ~ 65,535 |
| int | signed int | 4 바이트 | -2,147,483,648 ~ 2,147,483,647 |
| uint | unsigned int | 4 바이트 | 0 ~ 4,294,967,295 |
| long | signed long | 8 바이트 | -9,223,372,036,854,775,808 ~ 9,223,372,036,854,775,807 |
| ulong | unsigned long | 8 바이트 | 0 ~ 18,446,744,073,709,551,615 |

### 실수 자료형

실수 자료형은 소수점을 포함하는 데이터를 처리할 때 사용합니다. 컴퓨터에서는 소수점이 특정 위치에 고정되어 있지 않고 소수점의 위치를 지정하는 부동 수소점(Floating-point)방식으로 표현합니다.


| 자료형 | 의미 | 크기 | 저장할 수 있는 값의 유효 범위 |
| :-- | :-- | :-- | :-- |
| float | 단일 정밀도(자릿수 : 7개까지 처리) | 4 byte | -3.402823e38 ~ 3.402823e38 |
| double | 복수 정밀도(자릿수 : 16개까지 처리) | 8 byte | -1.79769313486232e308 ~ 1.79769313486232@308 |
| decimal | 복수 초정밀도(자릿수 : 28개까지 처리) | 16 byte | +-1.0 x 10e-28~+-7.9 x 10e28 |

※주의 사항: **float(f)형과 decimal(m)형**은 사용 시 **리터럴 접미사**를 붙여야 합니다[^4].

예:

```csharp
float f = 123.345f;
decimal d = 12345678912334567m;
```


### 문자 및 문자열 자료형

문자와 문자열은 텍스트 데이터를 저장하는 데 사용됩니다[^4].

#### 문자(char)

작은 따옴표(' ')를 사용하여 단일 문자를 표현합니다.

예: `char a = 'A';`

#### 문자열(string)

쌍 따옴표(" ")를 사용하여 텍스트를 표현합니다.

예: `string s = "abcd";`

#### 문자열 제어 방법

- `+` : 두 개의 문자열을 합합니다.
- `==` : 두 개의 문자열을 비교합니다.
- `Replace()` : 특정 문자를 변경합니다.
- `ToUpper()` : 모두 대문자로 변경합니다.
- `ToLower()` : 모두 소문자로 변경합니다[^4].


### 불리언(Boolean) 자료형

불리언 자료형은 참(true) 또는 거짓(false) 값을 저장합니다.

예: `bool isValid = true;`

### 기타 자료형

#### 객체 데이터 형태(object)

어떤 데이터 형이든 모두 처리가 가능하다는 장점이 있으며, 클래스에 상속이 적용됩니다[^4].

#### 열거형(enum)

열거형은 코드 가독성을 높이기 위해 사용하는 데이터 형태입니다[^4].

```csharp
enum DAY_OF_WEEK
{
    SUN, // 0
    MON, // 1
    TUE, // 2
    WED, // 3
    THU = 100, // 100
    FRI, // 101
    SAT  // 102
}
```

enum형은 자동으로 첫번째 데이터부터 0부터 번호를 매기며, 특정 값을 지정할 수도 있습니다.

#### nullable 형식

기존 데이터형의 값 + null값 저장이 가능한 형식입니다[^4].

```csharp
데이터자료형? 식별자
```

예: `int? num = 100;`

HasValue 속성으로 값의 존재 여부를 확인할 수 있습니다(값이 있으면 True, 없으면 False).

#### var

자료형이 불분명한 변수의 자료형으로 주로 사용합니다. 선언과 동시에 초기화해야 합니다[^4].

```csharp
var num = 100;
```

- 암시적 형식의 지역 변수(보통 {}안에서 정의된 함수)
- 선언과 동시에 초기화
- 지역변수로만 사용가능
- 'for ~ each'에서 자주사용


## 형변환

C\#에서는 다양한 형변환 방법을 제공합니다[^4].

### 캐스트 연산자를 이용한 형변환

정수에서 실수로, 또는 실수에서 정수로 변환할 때 사용합니다.

```csharp
int a = 10;
float b = (float)a; // 정수에서 실수로 형변환
```


### 메서드를 이용한 형변환

- `ToString()` : 기본 데이터형을 문자열로 변환
- `Parse()` : 문자열을 기본 데이터형으로 변환
- `Convert.~` : 다양한 형변환 메서드를 제공


## 연산자

### 산술 연산자

- `+` : 덧셈
- `-` : 뺄셈
- `*` : 곱셈
- `/` : 나눗셈
- `%` : 나머지


### 비교 연산자

- `==` : 같음
- `!=` : 다름
- `&gt;` : 크다
- `&lt;` : 작다
- `&gt;=` : 크거나 같다
- `&lt;=` : 작거나 같다


### 논리 연산자

- `&amp;&amp;` : AND
- `||` : OR
- `!` : NOT


### 비트 연산자

- `&amp;` : 비트 AND
- `|` : 비트 OR
- `^` : 비트 XOR
- `~` : 비트 NOT
- `&lt;&lt;` : 왼쪽 시프트
- `&gt;&gt;` : 오른쪽 시프트


### 할당 연산자

- `=` : 할당
- `+=` : 더하고 할당
- `-=` : 빼고 할당
- `*=` : 곱하고 할당
- `/=` : 나누고 할당
- `%=` : 나머지를 할당


### 조건 연산자(삼항 연산자)

```csharp
조건식 ? 참일 때 표현식 : 거짓일 때 표현식
```


## 제어문

### 조건문

#### if문

```csharp
if (조건식)
{
    // 조건이 참일 때 실행될 코드
}
else if (다른 조건식)
{
    // 다른 조건이 참일 때 실행될 코드
}
else
{
    // 모든 조건이 거짓일 때 실행될 코드
}
```


#### switch문

```csharp
switch (변수)
{
    case 값1:
        // 변수가 값1일 때 실행될 코드
        break;
    case 값2:
        // 변수가 값2일 때 실행될 코드
        break;
    default:
        // 변수가 어떤 case에도 해당하지 않을 때 실행될 코드
        break;
}
```


### 반복문

#### while문

```csharp
while (조건식)
{
    // 조건이 참인 동안 반복 실행될 코드
}
```


#### do-while문

```csharp
do
{
    // 최소 한 번은 실행되고, 조건이 참인 동안 반복 실행될 코드
} while (조건식);
```


#### for문

```csharp
for (초기화; 조건식; 증감식)
{
    // 조건이 참인 동안 반복 실행될 코드
}
```


#### foreach문

```csharp
foreach (var 항목 in 컬렉션)
{
    // 컬렉션의 각 항목에 대해 실행될 코드
}
```


## 배열

배열은 동일한 데이터 유형의 여러 항목을 저장하는 데 사용됩니다.

### 배열 선언 및 초기화

```csharp
// 선언
데이터형[] 배열명 = new 데이터형[크기];

// 선언과 동시에 초기화
데이터형[] 배열명 = new 데이터형[] { 값1, 값2, ... };
데이터형[] 배열명 = { 값1, 값2, ... }; // 간소화된 형태
```

예:

```csharp
int[] numbers = new int[^5]; // 5개의 정수를 저장할 수 있는 배열
int[] scores = { 90, 85, 77, 93, 60 }; // 초기값이 있는 배열
```


### 다차원 배열

#### 2차원 배열

```csharp
데이터형[,] 배열명 = new 데이터형[행 크기, 열 크기];
```

예:

```csharp
int[,] matrix = new int[3, 4]; // 3x4 행렬
int[,] grid = { { 1, 2 }, { 3, 4 }, { 5, 6 } }; // 3x2 행렬 초기화
```


#### 가변 배열(Jagged Array)

```csharp
데이터형[][] 배열명 = new 데이터형[행 크기][];
```

예:

```csharp
int[][] jaggedArray = new int[^3][];
jaggedArray[^0] = new int[] { 1, 2, 3 };
jaggedArray[^1] = new int[] { 4, 5 };
jaggedArray[^2] = new int[] { 6, 7, 8, 9 };
```


## 메서드

메서드는 특정 작업을 수행하는 코드 블록으로, 재사용 가능성을 높이고 코드를 구조화하는 데 도움이 됩니다[^3].

### 메서드 선언

```csharp
접근제한자 반환형 메서드명(매개변수목록)
{
    // 메서드 본문
    return 반환값; // 반환형이 void가 아닌 경우
}
```

예:

```csharp
public int Add(int a, int b)
{
    return a + b;
}
```


### 메서드 오버로딩

메서드 오버로딩을 통해 같은 이름의 메서드를 매개변수의 수나 타입을 다르게 하여 여러 개 정의할 수 있습니다[^3].

```csharp
public int Add(int a, int b)
{
    return a + b;
}

public double Add(double a, double b)
{
    return a + b;
}

public string Add(string a, string b)
{
    return a + b;
}
```


### 매개변수 전달 방식

#### 값에 의한 전달(Pass by Value)

```csharp
void Increment(int x)
{
    x++; // 원본 변수에 영향을 주지 않음
}
```


#### 참조에 의한 전달(Pass by Reference)

```csharp
void Increment(ref int x)
{
    x++; // 원본 변수의 값이 변경됨
}
```


#### 출력 매개변수(out parameter)

```csharp
void GetValues(out int x, out int y)
{
    x = 10; // out 매개변수는 메서드 내에서 반드시 값을 할당해야 함
    y = 20;
}
```


## 클래스와 객체

C\#은 객체 지향 프로그래밍 언어로, 클래스와 객체는 핵심 개념입니다[^3].

### 클래스 정의

```csharp
접근제한자 class 클래스명
{
    // 필드(멤버 변수)
    접근제한자 데이터형 필드명;
    
    // 생성자
    접근제한자 클래스명(매개변수목록)
    {
        // 초기화 코드
    }
    
    // 메서드
    접근제한자 반환형 메서드명(매개변수목록)
    {
        // 메서드 본문
    }
    
    // 속성
    접근제한자 데이터형 속성명
    {
        get { return 필드; }
        set { 필드 = value; }
    }
}
```


### 객체 생성 및 사용

```csharp
클래스명 객체명 = new 클래스명();
객체명.메서드명();
객체명.속성명 = 값;
```


### 생성자

생성자는 객체가 생성될 때 자동으로 호출되는 특별한 메서드로, 객체의 초기화를 담당합니다[^3].

```csharp
public class Person
{
    public string Name;
    public int Age;
    
    // 기본 생성자
    public Person()
    {
        Name = "Unknown";
        Age = 0;
    }
    
    // 매개변수가 있는 생성자
    public Person(string name, int age)
    {
        Name = name;
        Age = age;
    }
}
```


### 소멸자

소멸자는 객체가 소멸될 때 자동으로 호출되는 메서드입니다[^3].

```csharp
~클래스명()
{
    // 정리 코드
}
```


## 상속

상속은 기존 클래스의 특성을 새 클래스에 물려주는 기능입니다[^3].

### 상속 구현

```csharp
접근제한자 class 자식클래스 : 부모클래스
{
    // 자식 클래스의 추가 멤버
}
```


### 메서드 오버라이딩

부모 클래스의 메서드를 자식 클래스에서 재정의할 수 있습니다[^3].

```csharp
public class Parent
{
    public virtual void Display()
    {
        Console.WriteLine("Parent's Display");
    }
}

public class Child : Parent
{
    public override void Display()
    {
        Console.WriteLine("Child's Display");
    }
}
```


### 추상 클래스

추상 클래스는 인스턴스화할 수 없으며, 상속을 위한 기본 클래스로 사용됩니다[^3].

```csharp
public abstract class Shape
{
    public abstract double CalculateArea();
    
    public void Display()
    {
        Console.WriteLine("This is a shape.");
    }
}

public class Circle : Shape
{
    public double Radius { get; set; }
    
    public override double CalculateArea()
    {
        return Math.PI * Radius * Radius;
    }
}
```


### 봉인 클래스(sealed class)

봉인 클래스는 더 이상 상속될 수 없는 클래스입니다[^3].

```csharp
public sealed class FinalClass
{
    // 멤버
}
```


## 인터페이스

인터페이스는 클래스가 구현해야 하는 메서드, 속성, 이벤트 등의 시그니처를 정의합니다[^3].

### 인터페이스 정의

```csharp
public interface IShape
{
    double CalculateArea();
    void Draw();
}
```


### 인터페이스 구현

```csharp
public class Circle : IShape
{
    public double Radius { get; set; }
    
    public double CalculateArea()
    {
        return Math.PI * Radius * Radius;
    }
    
    public void Draw()
    {
        Console.WriteLine("Drawing a circle");
    }
}
```


## 예외 처리

예외 처리는 프로그램 실행 중 발생할 수 있는 오류를 다루는 메커니즘입니다.

### try-catch-finally

```csharp
try
{
    // 예외가 발생할 수 있는 코드
}
catch (예외타입1 e)
{
    // 예외타입1에 대한 처리
}
catch (예외타입2 e)
{
    // 예외타입2에 대한 처리
}
finally
{
    // 예외 발생 여부와 관계없이 항상 실행되는 코드
}
```


### 예외 발생시키기

```csharp
if (조건)
{
    throw new 예외타입("예외 메시지");
}
```


## 제네릭

제네릭은 형식에 독립적인 클래스, 메서드, 인터페이스 등을 구현할 수 있게 해줍니다[^3].

### 제네릭 클래스

```csharp
public class List&lt;T&gt;
{
    private T[] items;
    
    public void Add(T item)
    {
        // 구현
    }
    
    public T GetItem(int index)
    {
        return items[index];
    }
}
```


### 제네릭 메서드

```csharp
public T Max&lt;T&gt;(T a, T b) where T : IComparable&lt;T&gt;
{
    return a.CompareTo(b) &gt; 0 ? a : b;
}
```


## 델리게이트와 이벤트

### 델리게이트

델리게이트는 메서드를 참조하는 형식으로, 메서드를 매개변수로 전달하거나 변수에 저장할 수 있게 해줍니다[^3].

```csharp
// 델리게이트 정의
public delegate int Calculator(int a, int b);

// 델리게이트 사용
public static int Add(int a, int b) { return a + b; }
public static int Subtract(int a, int b) { return a - b; }

Calculator calc = Add;
int result = calc(5, 3); // 8

calc = Subtract;
result = calc(5, 3); // 2
```


### 이벤트

이벤트는 특정 상황이 발생했을 때 알림을 제공하는 메커니즘입니다[^3].

```csharp
public class Button
{
    // 이벤트 델리게이트 정의
    public delegate void ClickEventHandler(object sender, EventArgs e);
    
    // 이벤트 선언
    public event ClickEventHandler Click;
    
    // 이벤트 발생 메서드
    public void OnClick()
    {
        if (Click != null)
        {
            Click(this, EventArgs.Empty);
        }
    }
}

// 이벤트 사용
Button button = new Button();
button.Click += (sender, e) =&gt; Console.WriteLine("Button clicked!");
button.OnClick(); // "Button clicked!" 출력
```


## LINQ (Language Integrated Query)

LINQ는 C\#에서 데이터 쿼리 기능을 제공하는 기능입니다[^3].

### 쿼리 구문

```csharp
var query = from item in collection
            where item.Property &gt; value
            orderby item.AnotherProperty
            select item;
```


### 메서드 구문

```csharp
var query = collection
    .Where(item =&gt; item.Property &gt; value)
    .OrderBy(item =&gt; item.AnotherProperty)
    .Select(item =&gt; item);
```


## 비동기 프로그래밍

C\#은 async와 await 키워드를 사용하여 비동기 프로그래밍을 지원합니다[^1][^3].

### async/await

```csharp
public async Task&lt;int&gt; DownloadDataAsync()
{
    // 비동기 작업
    var result = await DownloadAsync();
    return result;
}
```


### Task 기반 비동기 패턴

```csharp
public Task&lt;int&gt; GetValueAsync()
{
    return Task.Run(() =&gt; {
        // 시간이 오래 걸리는 작업
        return 42;
    });
}
```


## 파일 입출력

### 파일 읽기

```csharp
using System.IO;

string text = File.ReadAllText("file.txt");
string[] lines = File.ReadAllLines("file.txt");

using (StreamReader reader = new StreamReader("file.txt"))
{
    string line;
    while ((line = reader.ReadLine()) != null)
    {
        Console.WriteLine(line);
    }
}
```


### 파일 쓰기

```csharp
using System.IO;

File.WriteAllText("file.txt", "Hello, World!");
File.WriteAllLines("file.txt", new[] { "Line 1", "Line 2" });

using (StreamWriter writer = new StreamWriter("file.txt"))
{
    writer.WriteLine("Hello, World!");
}
```


## 마크다운 파일 다루기

C\#에서 마크다운 파일을 다루는 방법도 있습니다.

### 마크다운 파일에서 텍스트 추출하기

```csharp
using GroupDocs.Parser;

// Markdown 파일의 전체 텍스트 추출
using (Parser parser = new Parser("/path/document.md"))
{
    using (TextReader reader = parser.GetText())
    {
        Console.WriteLine(reader.ReadToEnd());
    }
}
```

이 코드는 GroupDocs.Parser 라이브러리를 사용하여 마크다운 파일에서 텍스트를 추출하는 예제입니다[^7].

## 참고 자료

- Microsoft Learn: https://learn.microsoft.com/ko-kr/dotnet/csharp/
- C\# 초보 강좌: https://www.inflearn.com/course/c-sharp-basic
- C\# 프로그래밍: https://www.inflearn.com/course/c-programming
- GitHub의 C\# 학습 자료: https://github.com/ahmedelmaadawy/CSharp-Notes

<div style="text-align: center">⁂</div>

[^1]: https://github.com/HyundongHwang/DotNetTour

[^2]: https://learn.microsoft.com/ko-kr/contribute/content/markdown-reference

[^3]: https://github.com/ahmedelmaadawy/CSharp-Notes

[^4]: https://gugugame.tistory.com/entry/C-정리-노트-1

[^5]: https://learn.microsoft.com/ko-kr/dotnet/csharp/fundamentals/program-structure/

[^6]: https://dotnet.microsoft.com/ko-kr/learntocode

[^7]: https://blog.groupdocs.com/ko/parser/extract-text-from-markdown-files-using-csharp/

[^8]: https://github.com/jacking75/NewbieGameServerProgrammerLearningMaterials

[^9]: https://gist.github.com/rkttu/02a0905075f06c46f65fb5523b8af2f3

[^10]: https://github.com/Shim0209/CS_Study

[^11]: https://github.com/hyeyoom/Study-Note

[^12]: https://github.com/alimirakim/The-C-Sharp-Players-Guide-4e-Study

[^13]: https://blog.naver.com/kishanbi/222031864146

[^14]: https://blog.naver.com/brickbot/220462646332

[^15]: https://github.com/pr0gr4m/Newbie-Guideline

[^16]: https://www.dotnetnote.com/docs/csharp/syntax/

[^17]: https://github.com/joehunterdev/c-sharp-masterclass

[^18]: https://c-hash-study-note.tistory.com/entry/C-초보자-가이드-기초부터-이해하기

[^19]: https://velog.io/@sean_kk/C-%ED%95%99%EC%8A%B5%ED%95%98%EA%B8%B0-1-%EA%B3%B5%EC%8B%9D%EB%AC%B8%EC%84%9C

[^20]: https://github.com/teddylee777/machine-learning



