# C# 소개

C#은 마이크로소프트에서 개발한 현대적인 객체 지향 프로그래밍 언어입니다. .NET 프레임워크 기반으로 동작하며 다양한 애플리케이션 개발에 사용됩니다.

## C#의 특징

- C++에서 파생된 객체 지향 언어
- 형식 안정성(객체지향언어는 형식의 안정성이 있음)
- Java의 특징 + C, C++의 장점
- 다양한 플랫폼(.NET Core, .NET 5/6/7 등) 지원

## C#의 장점

- 입문자에게 적합한 언어
- 메모리 관리가 쉽다(Garbage Collector)
- 다양한 라이브러리 지원
- Windows, macOS, Linux 등 다양한 운영체제 지원

## .NET 프레임워크

C#을 통해 프로그래밍을 합니다. 컴파일까지만 해주면 나머지는 컴퓨터가 기계어로 바꿔준 후 운영체제로 넘기기 때문에 맥과 윈도우 모두 호환이 가능합니다.

## 프로그램 기본 구조

```

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

최신 C#에서는 최상위 문을 사용할 수도 있습니다:

```

using System;

Console.WriteLine("Hello world!");

