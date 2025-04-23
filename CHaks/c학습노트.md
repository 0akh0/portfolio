<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" class="logo" width="120"/>

# C 언어 학습노트

이 C 언어 학습노트는 프로그래밍 입문자 및 C 언어를 복습하고자 하는 분들을 위해 작성되었습니다. 핵심 개념과 사용법, 메모리와의 상호작용을 간결하고 체계적으로 설명하고 있습니다. 각 주제별로 개별 마크다운 파일로 구성되어 있어 필요한 내용만 선택적으로 학습할 수 있습니다.

## 01_C_언어_소개.md

```markdown
# C 언어 소개
C 언어는 1972년 AT&amp;T 벨 연구소의 데니스 리치(Dennis Ritchie)가 개발한 프로그래밍 언어로, 시스템 프로그래밍과 응용 프로그래밍에 모두 사용되는 범용 언어입니다.

## C 언어의 특징
C 언어는 다음과 같은 특징을 가지고 있습니다:
- 중간 수준의 언어(Middle-level language): 하드웨어에 가까운 저수준 프로그래밍과 사용자 친화적인 고수준 프로그래밍의 장점을 모두 갖추고 있습니다.
- 이식성(Portability): 다양한 하드웨어 플랫폼에서 실행 가능합니다.
- 모듈성(Modularity): 함수를 통해 코드를 모듈화할 수 있습니다.
- 구조적 프로그래밍(Structured Programming): 프로그램을 구조화하여 개발할 수 있습니다.
- 효율성(Efficiency): 하드웨어를 직접 제어할 수 있어 실행 속도가 빠릅니다.

## C 언어 활용 분야
C 언어는 주로 다음과 같은 분야에서 활용됩니다:
- 운영체제 및 시스템 소프트웨어 개발
- 임베디드 시스템 프로그래밍
- 게임 개발
- 데이터베이스 관리 시스템
- 컴파일러 및 인터프리터 개발
- IoT(Internet of Things) 디바이스 프로그래밍

## C 언어 개발 환경
C 언어로 프로그래밍을 시작하기 위해 필요한 개발 환경은 다음과 같습니다:
- 텍스트 에디터 또는 통합 개발 환경(IDE): Visual Studio, Code::Blocks, Dev-C++, CLion 등
- C 컴파일러: GCC, Clang, MSVC 등
- 디버거: GDB, Visual Studio Debugger 등

## C 언어 프로그램의 기본 구조
C 언어 프로그램의 기본 구조는 다음과 같습니다:

```

\#include <stdio.h>  // 헤더 파일 포함

int main() {  // 메인 함수 시작
printf("Hello, World!\n");  // 문장
return 0;  // 함수 반환값
}  // 메인 함수 종료

```

- `#include &lt;stdio.h&gt;`: 표준 입출력 헤더 파일을 포함합니다.
- `int main()`: 프로그램의 진입점인 메인 함수를 정의합니다.
- `printf("Hello, World!\n");`: 화면에 "Hello, World!"를 출력합니다.
- `return 0;`: 프로그램이 정상적으로 종료되었음을 운영체제에 알립니다.
```


## 02_기본_문법.md

```markdown
# 기본 문법
C 언어의 기본 문법은 프로그램 작성의 기초가 되는 규칙과 구성 요소를 포함합니다.

## 주석
주석은 프로그램 코드에 설명을 추가하는 데 사용되며, 컴파일러에 의해 무시됩니다.
```

// 이것은 한 줄 주석입니다

/*
이것은
여러 줄
주석입니다
*/

```

## 식별자
식별자는 변수, 함수, 배열 등의 이름을 지정하는 데 사용되는 문자열입니다.
- 영문자(A-Z, a-z), 숫자(0-9), 밑줄(_)로 구성됩니다.
- 첫 글자는 영문자나 밑줄이어야 합니다.
- 대소문자를 구분합니다. (예: count, Count, COUNT는 서로 다른 식별자)
- C 언어의 예약어는 식별자로 사용할 수 없습니다.

## 예약어(키워드)
C 언어에서 특별한 의미를 갖는 단어로, 사용자 정의 식별자로 사용할 수 없습니다.

|   |   |   |   |
|---|---|---|---|
| auto | break | case | char |
| const | continue | default | do |
| double | else | enum | extern |
| float | for | goto | if |
| int | long | register | return |
| short | signed | sizeof | static |
| struct | switch | typedef | union |
| unsigned | void | volatile | while |

## 세미콜론
C 언어에서 문장의 끝은 세미콜론(;)으로 표시합니다.
```

int a = 10;  // 변수 선언과 초기화
printf("Hello\n");  // 함수 호출

```

## 블록
중괄호({})로 묶인 코드 블록은 여러 문장을 하나의 단위로 그룹화합니다.
```

if (condition) {
// 이 블록 내의 모든 문장은
// condition이 참일 때 실행됩니다
statement1;
statement2;
}

```

## 들여쓰기
들여쓰기는 코드의 가독성을 높이기 위해 사용되며, 일반적으로 4개의 공백 또는 탭 문자를 사용합니다.
```

if (condition) {
statement1;
if (another_condition) {
statement2;
}
}

```
```


## 03_자료형.md

```markdown
# 자료형
C 언어에서 자료형은 변수나 상수의 크기와 유형을 지정하는 데 사용됩니다.

## 기본 자료형
C 언어의 기본 자료형은 다음과 같습니다.

### 정수 자료형
정수 자료형은 소수점이 없는 숫자를 저장하는 데 사용됩니다.

| 자료형 | 크기 | 값의 범위 |
|--------|------|-----------|
| char | 1 바이트 | -128 ~ 127 또는 0 ~ 255 |
| unsigned char | 1 바이트 | 0 ~ 255 |
| signed char | 1 바이트 | -128 ~ 127 |
| int | 보통 4 바이트 | -2,147,483,648 ~ 2,147,483,647 |
| unsigned int | 보통 4 바이트 | 0 ~ 4,294,967,295 |
| short | 2 바이트 | -32,768 ~ 32,767 |
| unsigned short | 2 바이트 | 0 ~ 65,535 |
| long | 4 바이트 (Windows), 8 바이트 (Unix/Linux 64비트) | -2,147,483,648 ~ 2,147,483,647 (4 바이트) |
| unsigned long | 4 바이트 (Windows), 8 바이트 (Unix/Linux 64비트) | 0 ~ 4,294,967,295 (4 바이트) |
| long long | 8 바이트 | -9,223,372,036,854,775,808 ~ 9,223,372,036,854,775,807 |
| unsigned long long | 8 바이트 | 0 ~ 18,446,744,073,709,551,615 |

### 실수 자료형
실수 자료형은 소수점이 있는 숫자를 저장하는 데 사용됩니다.

| 자료형 | 크기 | 유효 자릿수 | 값의 범위 |
|--------|------|--------------|-----------|
| float | 4 바이트 | 약 7자리 | 약 ±3.4 × 10^±38 |
| double | 8 바이트 | 약 15~16자리 | 약 ±1.7 × 10^±308 |
| long double | 보통 12 바이트 또는 16 바이트 | 약 19자리 | 시스템에 따라 다름 |

### 문자 자료형
문자 자료형은 문자를 저장하는 데 사용됩니다.

| 자료형 | 크기 | 값의 범위 |
|--------|------|-----------|
| char | 1 바이트 | 한 문자 (ASCII 코드 값) |

### 불리언 자료형
C99부터 `_Bool` 자료형이 도입되었으며, `&lt;stdbool.h&gt;` 헤더를 포함하면 `bool` 자료형을 사용할 수 있습니다.

| 자료형 | 크기 | 값의 범위 |
|--------|------|-----------|
| _Bool | 1 바이트 | 0(거짓) 또는 1(참) |

## 자료형 변환
자료형 변환은 한 자료형의 값을 다른 자료형으로 변환하는 과정입니다.

### 암시적 형변환
컴파일러가 자동으로 수행하는 자료형 변환입니다.
```

int i = 10;
float f = i;  // int에서 float로 자동 변환

```

### 명시적 형변환
프로그래머가 캐스트 연산자를 사용하여 수행하는 자료형 변환입니다.
```

float f = 3.14;
int i = (int)f;  // float에서 int로 명시적 변환, i = 3

```

## 변수
변수는 데이터를 저장하기 위한 이름이 있는 메모리 공간입니다.

### 변수 선언
```

자료형 변수명;  // 변수 선언
자료형 변수명 = 초기값;  // 변수 선언과 초기화

```
예:
```

int age;  // 변수 선언
age = 25;  // 변수에 값 할당
int height = 180;  // 변수 선언과 초기화

```

### 변수 이름 규칙
- 영문자, 숫자, 밑줄(_)로 구성
- 첫 글자는 영문자나 밑줄
- 대소문자 구분
- 예약어는 사용할 수 없음

## 상수
상수는 프로그램 실행 중에 값이 변경되지 않는 고정된 데이터입니다.

### 리터럴 상수
직접 표현된 값입니다.
```

42  // 정수 리터럴
3.14  // 실수 리터럴
'A'  // 문자 리터럴
"Hello"  // 문자열 리터럴

```

### 심볼릭 상수
`const` 키워드나 `#define`을 사용하여 정의된 상수입니다.
```

const int MAX_VALUE = 100;  // const 키워드 사용
\#define PI 3.14159  // \#define 사용

```

## 자료형 수식어
자료형의 범위나 성질을 수정하는 키워드입니다.

| 수식어 | 설명 |
|--------|------|
| signed | 양수와 음수를 모두 표현 (기본값) |
| unsigned | 양수만 표현 |
| short | 크기를 줄임 |
| long | 크기를 늘림 |
| const | 값을 변경할 수 없음 |
| volatile | 컴파일러 최적화에서 제외 |
```


## 04_연산자.md

```markdown
# 연산자
C 언어에서 연산자는 특정 연산을 수행하는 기호입니다.

## 산술 연산자
숫자 데이터에 대한 기본적인 수학 연산을 수행합니다.

| 연산자 | 설명 | 예시 |
|---------|------|-------|
| + | 덧셈 | a + b |
| - | 뺄셈 | a - b |
| * | 곱셈 | a * b |
| / | 나눗셈 | a / b |
| % | 나머지 | a % b |
| ++ | 증가 | a++ 또는 ++a |
| -- | 감소 | a-- 또는 --a |

### 예시
```

int a = 10, b = 3;
int sum = a + b;       // 13
int difference = a - b;  // 7
int product = a * b;    // 30
int quotient = a / b;   // 3
int remainder = a % b;  // 1

```

## 관계 연산자
두 값의 관계를 비교하며, 결과는 참(1) 또는 거짓(0)입니다.

| 연산자 | 설명 | 예시 |
|---------|------|-------|
| == | 같다 | a == b |
| != | 같지 않다 | a != b |
| &gt; | 크다 | a &gt; b |
| &lt; | 작다 | a &lt; b |
| &gt;= | 크거나 같다 | a &gt;= b |
| &lt;= | 작거나 같다 | a &lt;= b |

### 예시
```

int a = 10, b = 5;
int result1 = (a == b);  // 0 (거짓)
int result2 = (a > b);   // 1 (참)
int result3 = (a <= b);  // 0 (거짓)

```

##, 논리 연산자
두 개 이상의 조건을 결합하거나 부정합니다.

| 연산자 | 설명 | 예시 |
|---------|------|-------|
| &amp;&amp; | 논리 AND | a &amp;&amp; b |
| \|\| | 논리 OR | a \|\| b |
| ! | 논리 NOT | !a |

### 예시
```

int a = 1, b = 0;
int result1 = (a \&\& b);  // 0 (거짓)
int result2 = (a || b);  // 1 (참)
int result3 = !a;        // 0 (거짓)

```

## 비트 연산자
비트 단위로 연산을 수행합니다.

| 연산자 | 설명 | 예시 |
|---------|------|-------|
| &amp; | 비트 AND | a &amp; b |
| \| | 비트 OR | a \| b |
| ^ | 비트 XOR | a ^ b |
| ~ | 비트 NOT | ~a |
| &lt;&lt; | 왼쪽 시프트 | a &lt;&lt; n |
| &gt;&gt; | 오른쪽 시프트 | a &gt;&gt; n |

### 예시
```

int a = 12;  // 1100(2)
int b = 10;  // 1010(2)
int result1 = a \& b;   // 8 (1000(2))
int result2 = a | b;   // 14 (1110(2))
int result3 = a ^ b;   // 6 (0110(2))
int result4 = ~a;      // -13 (비트 반전)
int result5 = a << 1;  // 24 (11000(2))
int result6 = a >> 1;  // 6 (0110(2))

```

## 할당 연산자
변수에 값을 할당합니다.

| 연산자 | 설명 | 예시 |
|---------|------|-------|
| = | 기본 할당 | a = b |
| += | 덧셈 후 할당 | a += b (a = a + b) |
| -= | 뺄셈 후 할당 | a -= b (a = a - b) |
| *= | 곱셈 후 할당 | a *= b (a = a * b) |
| /= | 나눗셈 후 할당 | a /= b (a = a / b) |
| %= | 나머지 후 할당 | a %= b (a = a % b) |
| &amp;= | 비트 AND 후 할당 | a &amp;= b (a = a &amp; b) |
| \|= | 비트 OR 후 할당 | a \|= b (a = a \| b) |
| ^= | 비트 XOR 후 할당 | a ^= b (a = a ^ b) |
| &lt;&lt;= | 왼쪽 시프트 후 할당 | a &lt;&lt;= b (a = a &lt;&lt; b) |
| &gt;&gt;= | 오른쪽 시프트 후 할당 | a &gt;&gt;= b (a = a &gt;&gt; b) |

### 예시
```

int a = 10;
a += 5;   // a = 15
a -= 3;   // a = 12
a *= 2;   // a = 24
a /= 4;   // a = 6
a %= 4;   // a = 2

```
```


## 05_제어_구조.md

```markdown
# 제어 구조
제어 구조는 프로그램의 실행 흐름을 제어하는 문장들입니다.

## 조건문
조건에 따라 다른 코드 블록을 실행합니다.

### if 문
조건이 참일 때 코드 블록을 실행합니다.
```

if (condition) {
// condition이 참일 때 실행될 코드
}

```

### if-else 문
조건이 참일 때와 거짓일 때 다른 코드 블록을 실행합니다.
```

if (condition) {
// condition이 참일 때 실행될 코드
} else {
// condition이 거짓일 때 실행될 코드
}

```

### if-else if-else 문
여러 조건에 따라 다른 코드 블록을 실행합니다.
```

if (condition1) {
// condition1이 참일 때 실행될 코드
} else if (condition2) {
// condition1이 거짓이고 condition2가 참일 때 실행될 코드
} else {
// 모든 조건이 거짓일 때 실행될 코드
}

```

### 중첩 if 문
if 문 안에 다른 if 문을 포함할 수 있습니다.
```

if (condition1) {
if (condition2) {
// condition1과 condition2가 모두 참일 때 실행될 코드
}
}

```

### 조건 연산자
간단한 조건문을 한 줄로 표현할 수 있는 3항 연산자입니다.
```

result = (condition) ? value1 : value2;

```
- condition이 참이면 value1이 반환됩니다.
- condition이 거짓이면 value2가 반환됩니다.

### switch 문
여러 가능한 값에 따라 다른 코드 블록을 실행합니다.
```

switch (expression) {
case value1:
// expression이 value1과 같을 때 실행될 코드
break;
case value2:
// expression이 value2와 같을 때 실행될 코드
break;
default:
// expression이 어떤 case 값과도 일치하지 않을 때 실행될 코드
}

```
- `break` 문이 없으면 해당 case 이후의 모든 코드가 실행됩니다. (fall-through)
- `default` 케이스는 선택 사항이며, 일치하는 case가 없을 때 실행됩니다.

## 반복문
특정 코드 블록을 반복하여 실행합니다.

### while 문
조건이 참인 동안 코드 블록을 반복 실행합니다.
```

while (condition) {
// condition이 참인 동안 반복 실행될 코드
}

```

### do-while 문
코드 블록을 최소한 한 번 실행한 후, 조건이 참인 동안 반복 실행합니다.
```

do {
// 최소한 한 번 실행되고, condition이 참인 동안 반복 실행될 코드
} while (condition);

```

### for 문
초기화, 조건, 증감 등의 세 부분으로 나눠 반복 실행을 제어합니다.
```

for (initialization; condition; increment) {
// condition이 참인 동안 반복 실행될 코드
}

```
- initialization: 반복문이 시작하기 전에 한 번 실행됩니다.
- condition: 각 반복 전에 검사되며, 참일 때만 반복문 본체가 실행됩니다.
- increment: 각 반복 후에 실행됩니다.
```


## 06_함수.md

```markdown
# 함수
함수는 특정 작업을 수행하는 독립적인 코드 블록입니다.

## 함수의 구조
C 언어 함수의 기본 구조는 다음과 같습니다.
```

반환_자료형 함수명(매개변수_목록) {
// 함수 본체
return 반환값;  // 반환 자료형이 void가 아닌 경우 필요
}

```

## 함수 선언
함수를 사용하기 전에 컴파일러에게 함수의 존재를 알려주는 것입니다. 함수 원형(prototype)이라고도 합니다.
```

반환_자료형 함수명(매개변수_자료형 매개변수명, ...);

```
예:
```

int add(int a, int b);  // add 함수 선언

```

## 함수 정의
함수의 실제 구현 부분입니다.
```

int add(int a, int b) {
return a + b;  // 두 정수를 더한 결과를 반환
}

```

## 함수 호출
함수를 사용하여 해당 작업을 수행하는 것입니다.
```

int result = add(5, 3);  // add 함수 호출, result는 8

```

## 함수 매개변수 전달 방식

### 값에 의한 전달(Pass by Value)
함수에 매개변수 값의 복사본이 전달됩니다. 함수 내에서 매개변수를 변경해도 원본 값에는 영향을 주지 않습니다.
```

void swap(int a, int b) {
int temp = a;
a = b;
b = temp;
}

int main() {
int x = 5, y = 10;
swap(x, y);  // 함수 호출 후에도 x=5, y=10 (값이 바뀌지 않음)
return 0;
}

```

### 참조에 의한 전달(Pass by Reference)
C 언어에서는 직접적인 참조 전달을 지원하지 않지만, 포인터를 사용하여 비슷한 효과를 낼 수 있습니다.
```

void swap(int *a, int *b) {
int temp = *a;
*a = *b;
*b = temp;
}

int main() {
int x = 5, y = 10;
swap(\&x, \&y);  // 함수 호출 후 x=10, y=5 (값이 바뀜)
return 0;
}

```

## 함수의 매개변수

### 고정 매개변수
함수 정의 시 개수와 자료형이 고정된 매개변수입니다.
```

int add(int a, int b) {
return a + b;
}

```

### 가변 매개변수
함수 호출 시 매개변수의 개수가 가변적인 경우 사용합니다. `&lt;stdarg.h&gt;` 헤더를 포함해야 합니다.
```

\#include <stdio.h>
\#include <stdarg.h>

int sum(int count, ...) {
int result = 0;
va_list args;
va_start(args, count);

    for (int i = 0; i &lt; count; i++) {
        result += va_arg(args, int);
    }
    
    va_end(args);
    return result;
    }

int main() {
printf("Sum: %d\n", sum(3, 10, 20, 30));  // 출력: Sum: 60
printf("Sum: %d\n", sum(5, 1, 2, 3, 4, 5));  // 출력: Sum: 15
return 0;
}

```

## 함수의 반환값

### 값 반환
`return` 문을 사용하여 함수에서 값을 반환합니다.
```

int square(int n) {
return n * n;  // n의 제곱값 반환
}

```

### void 함수
반환값이 없는 함수는 반환 자료형을 `void`로 선언합니다.
```

void printMessage(char *message) {
printf("%s\n", message);
// 반환값 없음
}

```

## 재귀 함수
자기 자신을 호출하는 함수입니다. 재귀 함수는 반드시 종료 조건을 가져야 합니다.
```

int factorial(int n) {
if (n <= 1)  // 종료 조건
return 1;
else
return n * factorial(n - 1);  // 재귀 호출
}

```
```


## 07_배열과_문자열.md

```markdown
# 배열과 문자열
배열은 같은 자료형의 변수들을 연속적인 메모리 공간에 저장하는 자료구조입니다.

## 배열
배열은 동일한 자료형의 연속적인 집합입니다.

### 배열 선언
```

자료형 배열명[배열_크기];

```
예:
```

int numbers[^5];  // 5개의 정수를 저장할 수 있는 배열 선언

```

### 배열 초기화
배열은 다음과 같은 방법으로 초기화할 수 있습니다.
```

int numbers[^5] = {10, 20, 30, 40, 50};  // 모든 요소 초기화
int numbers[] = {10, 20, 30, 40, 50};  // 크기를 자동으로 결정
int numbers[^5] = {10, 20};  // 일부만 초기화 (나머지는 0)
int numbers[^5] = {0};  // 모든 요소를 0으로 초기화

```

### 배열 요소 접근
배열의 각 요소는 인덱스를 사용하여 접근합니다. 인덱스는 0부터 시작합니다.
```

int numbers[^5] = {10, 20, 30, 40, 50};
int first = numbers;  // 첫 번째 요소: 10
int third = numbers[^2];  // 세 번째 요소: 30
numbers[^4] = 60;  // 다섯 번째 요소를 60으로 변경

```

## 다차원 배열
배열의 각 요소가 또 다른 배열인 경우를 다차원 배열이라고 합니다.

### 2차원 배열 선언 및 초기화
```

int matrix[^3][^4];  // 3행 4열의 2차원 배열 선언

// 초기화 방법 1
int matrix[^3][^4] = {
{1, 2, 3, 4},
{5, 6, 7, 8},
{9, 10, 11, 12}
};

// 초기화 방법 2 (행과 열을 구분하지 않고 일렬로)
int matrix[^3][^4] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12};

```

### 2차원 배열 요소 접근
```

int matrix[^3][^4] = {
{1, 2, 3, 4},
{5, 6, 7, 8},
{9, 10, 11, 12}
};
int element = matrix[^1][^2];  // 2행 3열의 요소: 7
matrix[^2][^3] = 20;  // 3행 4열의 요소를 20으로 변경

```

## 문자열
C 언어에서 문자열은 널 문자('\0')로 끝나는 문자 배열입니다.

### 문자열 선언 및 초기화
```

char str1[^6] = {'H', 'e', 'l', 'l', 'o', '\0'};  // 문자 배열로 초기화
char str2[] = "Hello";  // 문자열 리터럴로 초기화 (자동으로 널 문자 추가)
char str3[^10] = "Hello";  // 지정된 크기보다 작은 문자열 (남은 공간은 널 문자로 채워짐)

```

### 문자열 함수
`&lt;string.h&gt;` 헤더에는 문자열 처리를 위한 다양한 함수가 정의되어 있습니다.

#### strlen() - 문자열 길이 구하기
```

\#include <string.h>

int main() {
char str[] = "Hello";
int length = strlen(str);  // 문자열 길이: 5
return 0;
}

```

#### strcpy() - 문자열 복사
```

\#include <string.h>

int main() {
char src[] = "Source";
char dest[^20];

    strcpy(dest, src);  // src의 내용을 dest로 복사
    
    return 0;
    }

```

#### strcat() - 문자열 연결
```

\#include <string.h>

int main() {
char str1[^20] = "Hello";
char str2[] = "World";

    strcat(str1, " ");  // str1에 공백 추가
    strcat(str1, str2);  // str1에 str2 연결 (결과: "Hello World")
    
    return 0;
    }

```

#### strcmp() - 문자열 비교
```

\#include <string.h>

int main() {
char str1[] = "apple";
char str2[] = "banana";

    int result = strcmp(str1, str2);
    // str1 &lt; str2이면 음수, str1 == str2이면 0, str1 &gt; str2이면 양수 반환
    
    if (result &lt; 0) {
        printf("str1이 str2보다 사전적으로 앞에 있습니다.\n");
    } else if (result &gt; 0) {
        printf("str1이 str2보다 사전적으로 뒤에 있습니다.\n");
    } else {
        printf("str1과 str2가 같습니다.\n");
    }
    
    return 0;
    }

```
```


## 08_포인터.md

```markdown
# 포인터
포인터는 메모리 주소를 저장하는 변수입니다.

## 포인터의 기본 개념
포인터는 다른 변수나 데이터의 메모리 주소를 저장합니다. 이를 통해 간접적으로 데이터에 접근하고 조작할 수 있습니다.

### 포인터 선언
```

자료형 *포인터명;

```
예:
```

int *p;  // 정수형 변수를 가리키는 포인터 선언

```

### 주소 연산자(&amp;)와 역참조 연산자(*)
- 주소 연산자(`&amp;`)는 변수의 메모리 주소를 반환합니다.
- 역참조 연산자(`*`)는 포인터가 가리키는 메모리 위치의 값을 반환합니다.
```

int num = 10;
int *p = \#  // num의 주소를 p에 저장

printf("num의 값: %d\n", num);  // 10
printf("num의 주소: %p\n", \&num);  // num의 메모리 주소
printf("p의 값(num의 주소): %p\n", p);  // num의 메모리 주소
printf("p가 가리키는 값: %d\n", *p);  // 10

```

## 포인터와 배열
배열 이름은 배열의 첫 번째 요소의 주소를 나타내는 포인터 상수입니다.

### 배열과 포인터의 관계
```

int arr[^5] = {10, 20, 30, 40, 50};
int *p = arr;  // arr은 첫 번째 요소의 주소

printf("첫 번째 요소: %d\n", arr);  // 10
printf("첫 번째 요소: %d\n", *arr);  // 10
printf("첫 번째 요소: %d\n", *p);  // 10

printf("두 번째 요소: %d\n", arr[^1]);  // 20
printf("두 번째 요소: %d\n", *(arr + 1));  // 20
printf("두 번째 요소: %d\n", *(p + 1));  // 20
printf("두 번째 요소: %d\n", p[^1]);  // 20

```

### 포인터 산술
포인터에 정수를 더하거나 뺄 때, 실제로는 포인터가 가리키는 자료형의 크기에 해당 정수를 곱한 만큼 주소가 이동합니다.
```

int arr[^5] = {10, 20, 30, 40, 50};
int *p = arr;

p++;  // p는 arr + 1과 같음 (두 번째 요소를 가리킴)
printf("%d\n", *p);  // 20

p += 2;  // p는 arr + 3과 같음 (네 번째 요소를 가리킴)
printf("%d\n", *p);  // 40

```

## 포인터와 함수
포인터를 함수의 매개변수로 전달하면 함수 내에서 원본 데이터를 직접 조작할 수 있습니다.

### 값에 의한 전달 vs 참조에 의한 전달
```

// 값에 의한 전달 (변경 불가능)
void increment_value(int num) {
num++;  // 지역 변수만 변경됨
}

// 참조에 의한 전달 (포인터 사용, 변경 가능)
void increment_reference(int *num) {
(*num)++;  // 원본 변수 변경
}

int main() {
int a = 10;

    increment_value(a);
    printf("값에 의한 전달 후: %d\n", a);  // 10 (변경되지 않음)
    
    increment_reference(&amp;a);
    printf("참조에 의한 전달 후: %d\n", a);  // 11 (변경됨)
    
    return 0;
    }

```

### 배열을 함수의 매개변수로 전달
```

// 배열을 포인터로 전달
void print_array(int *arr, int size) {
for (int i = 0; i < size; i++) {
printf("%d ", arr[i]);
}
printf("\n");
}

// 배열 표기법으로 전달 (내부적으로는 포인터로 변환됨)
void modify_array(int arr[], int size) {
for (int i = 0; i < size; i++) {
arr[i] *= 2;  // 각 요소를 2배로
}
}

int main() {
int numbers[^5] = {1, 2, 3, 4, 5};

    print_array(numbers, 5);  // 1 2 3 4 5
    modify_array(numbers, 5);
    print_array(numbers, 5);  // 2 4 6 8 10
    
    return 0;
    }

```

## 다중 포인터
포인터를 가리키는 포인터입니다.

### 이중 포인터
```

int num = 10;
int *p = \#   // num을 가리키는 포인터
int **pp = \&p;   // p를 가리키는 포인터 (이중 포인터)

printf("num의 값: %d\n", num);  // 10
printf("*p의 값: %d\n", *p);    // 10
printf("**pp의 값: %d\n", **pp); // 10

**pp = 20;  // num의 값을 20으로 변경
printf("num의 값: %d\n", num);  // 20

```
```


## 09_구조체와_공용체.md

```markdown
# 구조체와 공용체
구조체(Structure)와 공용체(Union)는 사용자 정의 자료형으로, 여러 자료형의 데이터를 하나의 단위로 그룹화하는 데 사용됩니다.

## 구조체
구조체는 서로 다른 자료형의 데이터를 하나의 단위로 묶는 사용자 정의 자료형입니다.

### 구조체 선언
```

struct 구조체명 {
자료형1 멤버1;
자료형2 멤버2;
// ...
};

```
예:
```

struct Person {
char name;
int age;
float height;
};

```

### 구조체 변수 선언
```

struct Person person1;  // Person 구조체 타입의 변수 선언

```

### 구조체 초기화
```

// 선언과 동시에 초기화
struct Person person1 = {"John Doe", 25, 175.5};

// 개별 멤버 초기화
struct Person person2;
strcpy(person2.name, "Jane Smith");
person2.age = 30;
person2.height = 162.3;

// C99부터 지원되는 지정 초기화
struct Person person3 = {
.name = "Tom",
.age = 40,
.height = 180.0
};

```

### 구조체 멤버 접근
```

// 점(.) 연산자를 이용한 멤버 접근
printf("이름: %s\n", person1.name);
printf("나이: %d\n", person1.age);
printf("키: %.1f\n", person1.height);

// 멤버 값 변경
person1.age = 26;

```

### 구조체 포인터
```

struct Person *ptr = \&person1;  // Person 구조체 변수의 주소를 포인터에 저장

// 화살표(->) 연산자를 이용한 멤버 접근
printf("이름: %s\n", ptr->name);
printf("나이: %d\n", ptr->age);
printf("키: %.1f\n", ptr->height);

// 또는 역참조 후 점 연산자 사용
printf("이름: %s\n", (*ptr).name);
printf("나이: %d\n", (*ptr).age);
printf("키: %.1f\n", (*ptr).height);

```

### 구조체 배열
```

struct Person people[^3] = {
{"John", 25, 175.5},
{"Jane", 30, 162.3},
{"Tom", 40, 180.0}
};

// 배열 요소에 접근
printf("두 번째 사람 이름: %s\n", people[^1].name);

```

## 공용체
공용체는 여러 멤버가 같은 메모리 공간을 공유하는 사용자 정의 자료형입니다.

### 공용체 선언
```

union 공용체명 {
자료형1 멤버1;
자료형2 멤버2;
// ...
};

```
예:
```

union Data {
int i;
float f;
char str[^20];
};

```

### 공용체 사용
```

union Data data;

data.i = 10;
printf("data.i: %d\n", data.i);  // 10

data.f = 3.14;  // 이전 값(data.i)은 손실됨
printf("data.f: %.2f\n", data.f);  // 3.14

strcpy(data.str, "Hello");  // 이전 값(data.f)은 손실됨
printf("data.str: %s\n", data.str);  // Hello

```

## 열거형
열거형은 명명된 정수 상수 집합을 정의하는 사용자 정의 자료형입니다.

### 열거형 선언
```

enum 열거형명 {
상수1,
상수2,
// ...
};

```
예:
```

enum Day {
SUNDAY,     // 0
MONDAY,     // 1
TUESDAY,    // 2
WEDNESDAY,  // 3
THURSDAY,   // 4
FRIDAY,     // 5
SATURDAY    // 6
};

```

### 열거형 사용
```

enum Day today = WEDNESDAY;
printf("Today is day %d\n", today);  // Today is day 3

if (today == WEDNESDAY) {
printf("It's Wednesday!\n");
}

// 열거형 변수는 정수형으로 취급됩니다
today = 5;  // FRIDAY
printf("Now it's day %d\n", today);  // Now it's day 5

```
```


## 10_메모리_관리와_파일_입출력.md

```markdown
# 메모리 관리와 파일 입출력
메모리 관리와 파일 입출력은 C 프로그래밍에서 중요한 두 가지 주제입니다.

## 메모리 구조
C 프로그램의 메모리는 일반적으로 다음과 같은 세그먼트로 구분됩니다.

### 코드 세그먼트(Code Segment)
- 프로그램의 실행 코드가 저장되는 영역
- 읽기 전용

### 데이터 세그먼트(Data Segment)
- 전역 변수와 정적 변수가 저장되는 영역
- 초기화된 데이터 세그먼트(initialized data segment)와 초기화되지 않은 데이터 세그먼트(BSS: Block Started by Symbol)로 구분

### 힙(Heap)
- 동적으로 할당된 메모리가 저장되는 영역
- 프로그래머가 명시적으로 관리해야 함

### 스택(Stack)
- 함수 호출 시 지역 변수와 함수 매개변수가 저장되는 영역
- 함수 호출 및 반환 과정에서 자동으로 관리됨

## 메모리 할당 및 해제
C 언어에서는 `&lt;stdlib.h&gt;` 헤더에 정의된 함수를 사용하여 메모리를 동적으로 할당하고 해제할 수 있습니다.

### malloc()
지정된 크기의 메모리 블록을 할당합니다.
```

\#include <stdlib.h>

int *p = (int *)malloc(5 * sizeof(int));  // 5개의 정수를 저장할 공간 할당

if (p == NULL) {
// 메모리 할당 실패 처리
} else {
// 메모리 사용
for (int i = 0; i < 5; i++) {
p[i] = i + 1;
}
}

```

### calloc()
지정된 개수만큼의 메모리 블록을 할당하고 0으로 초기화합니다.
```

int *p = (int *)calloc(5, sizeof(int));  // 5개의 정수를 저장할 공간 할당 및 0으로 초기화

if (p == NULL) {
// 메모리 할당 실패 처리
} else {
// 메모리 사용
for (int i = 0; i < 5; i++) {
printf("%d ", p[i]);  // 0 0 0 0 0
}
}

```

### realloc()
이미 할당된 메모리 블록의 크기를 변경합니다.
```

int *p = (int *)malloc(5 * sizeof(int));  // 처음 5개의 정수를 저장할 공간 할당

if (p != NULL) {
for (int i = 0; i < 5; i++) {
p[i] = i + 1;
}

    // 10개로 확장
    int *new_p = (int *)realloc(p, 10 * sizeof(int));
    
    if (new_p != NULL) {
        p = new_p;  // 새 주소로 업데이트
        
        // 추가된 공간 초기화
        for (int i = 5; i &lt; 10; i++) {
            p[i] = i + 1;
        }
    }
    }

```

### free()
동적으로 할당된 메모리를 해제합니다.
```

int *p = (int *)malloc(5 * sizeof(int));

if (p != NULL) {
// 메모리 사용

    free(p);  // 메모리 해제
    p = NULL;  // 해제 후 포인터를 NULL로 설정 (댕글링 포인터 방지)
    }

```

## 파일 입출력
C 언어에서는 `&lt;stdio.h&gt;` 헤더에 정의된 함수를 사용하여 파일 입출력을 수행할 수 있습니다.

### 파일 열기
```

\#include <stdio.h>

FILE *fp;  // 파일 포인터

// 읽기 모드로 파일 열기
fp = fopen("input.txt", "r");

// 쓰기 모드로 파일 열기 (기존 내용 덮어쓰기)
fp = fopen("output.txt", "w");

// 추가 모드로 파일 열기 (기존 내용 끝에 추가)
fp = fopen("log.txt", "a");

if (fp == NULL) {
printf("파일을 열 수 없습니다.\n");
return 1;
}

```

### 파일 열기 모드

| 모드 | 설명 |
|------|------|
| "r" | 읽기 모드. 파일이 존재해야 함 |
| "w" | 쓰기 모드. 파일이 존재하면 내용 삭제, 없으면 새로 생성 |
| "a" | 추가 모드. 파일이 존재하면 끝에 추가, 없으면 새로 생성 |
| "r+" | 읽기/쓰기 모드. 파일이 존재해야 함 |
| "w+" | 읽기/쓰기 모드. 파일이 존재하면 내용 삭제, 없으면 새로 생성 |
| "a+" | 읽기/추가 모드. 파일이 존재하면 끝에 추가, 없으면 새로 생성 |
| "rb", "wb", "ab" 등 | 이진 모드. 텍스트 모드 대신 바이너리 데이터 처리 |

### 파일 닫기
```

fclose(fp);  // 파일 닫기

```

### 문자 단위 입출력
```

// 문자 읽기
int c;
while ((c = fgetc(fp)) != EOF) {
printf("%c", (char)c);
}

// 문자 쓰기
fputc('A', fp);

```

### 문자열 단위 입출력
```

// 문자열 읽기
char str[^100];
while (fgets(str, sizeof(str), fp) != NULL) {
printf("%s", str);
}

// 문자열 쓰기
fputs("Hello, World!\n", fp);

```

### 형식화된 입출력
```

// 형식화된 읽기
int num;
char name;
fscanf(fp, "%d %s", \&num, name);

// 형식화된 쓰기
fprintf(fp, "이름: %s, 나이: %d\n", "홍길동", 25);

```
```


## 11_전처리기와_고급_주제.md

```markdown
# 전처리기와 고급 주제
C 언어의 전처리기와 고급 주제에 대해 알아봅니다.

## 전처리기
전처리기(preprocessor)는 컴파일 전에 소스 코드를 처리하는 프로그램입니다. 전처리기 지시문은 `#`으로 시작합니다.

### #include
헤더 파일을 소스 코드에 포함합니다.
```

\#include <stdio.h>  // 표준 헤더 파일
\#include "myheader.h"  // 사용자 정의 헤더 파일

```

### #define
매크로를 정의합니다.
```

\#define PI 3.14159  // 단순 매크로 상수
\#define SQUARE(x) ((x) * (x))  // 매크로 함수

printf("원주율: %f\n", PI);
printf("5의 제곱: %d\n", SQUARE(5));  // 25

```

### 조건부 컴파일
특정 조건에 따라 코드를 컴파일할지 여부를 결정합니다.

#### #ifdef, #ifndef, #endif
```

\#define DEBUG

\#ifdef DEBUG  // DEBUG가 정의되어 있으면
printf("디버그 모드\n");
\#endif

\#ifndef RELEASE  // RELEASE가 정의되어 있지 않으면
printf("릴리스 모드가 아닙니다.\n");
\#endif

```

#### #if, #elif, #else, #endif
```

\#define VERSION 2

\#if VERSION == 1
printf("버전 1\n");
\#elif VERSION == 2
printf("버전 2\n");
\#else
printf("알 수 없는 버전\n");
\#endif

```

## 비트 조작
C 언어는 비트 단위 연산을 위한 다양한 연산자를 제공합니다.

### 비트 AND(&amp;)
두 비트가 모두 1일 때만 결과가 1입니다.
```

int a = 12;  // 1100
int b = 10;  // 1010
int result = a \& b;  // 1000 (8)

```

### 비트 OR(|)
두 비트 중 하나라도 1이면 결과가 1입니다.
```

int a = 12;  // 1100
int b = 10;  // 1010
int result = a | b;  // 1110 (14)

```

### 비트 XOR(^)
두 비트가 서로 다를 때만 결과가 1입니다.
```

int a = 12;  // 1100
int b = 10;  // 1010
int result = a ^ b;  // 0110 (6)

```

### 비트 NOT(~)
비트를 반전시킵니다.
```

int a = 12;  // 1100
int result = ~a;  // ...11110011 (-13)

```

### 비트 시프트
비트를 왼쪽 또는 오른쪽으로 이동시킵니다.
```

int a = 12;  // 1100
int left_shift = a << 1;  // 11000 (24)
int right_shift = a >> 1;  // 0110 (6)

```

## 함수 포인터
함수의 주소를 저장하고, 이를 통해 함수를 호출할 수 있는 포인터입니다.

### 함수 포인터 선언
```

반환_자료형 (*포인터명)(매개변수_자료형, ...);

```

### 함수 포인터 사용
```

int add(int a, int b) {
return a + b;
}

int subtract(int a, int b) {
return a - b;
}

int main() {
int (*operation)(int, int);  // 함수 포인터 선언

    operation = add;  // 함수 포인터에 add 함수 주소 할당
    printf("결과: %d\n", operation(5, 3));  // 8
    
    operation = subtract;  // 함수 포인터에 subtract 함수 주소 할당
    printf("결과: %d\n", operation(5, 3));  // 2
    
    return 0;
    }

```

## 가변 인수 함수
매개변수의 개수가 가변적인 함수를 만들기 위해 `&lt;stdarg.h&gt;` 헤더를 사용합니다.

```

\#include <stdio.h>
\#include <stdarg.h>

// 가변 인수를 받는 함수
double average(int count, ...) {
va_list args;
double sum = 0;

    va_start(args, count);  // 가변 인수 처리 시작
    
    for (int i = 0; i &lt; count; i++) {
        sum += va_arg(args, int);  // 다음 인수를 int로 가져옴
    }
    
    va_end(args);  // 가변 인수 처리 종료
    
    return count &gt; 0 ? sum / count : 0;
    }

int main() {
printf("평균: %.2f\n", average(5, 10, 20, 30, 40, 50));  // 30.00
printf("평균: %.2f\n", average(3, 10, 20, 30));  // 20.00

    return 0;
    }

```
```


## 결론

이 C 언어 학습노트는 C 언어의 기초부터 고급 주제까지 다양한 내용을 체계적으로 정리했습니다. 각 파일은 특정 주제에 초점을 맞춰 세분화되어 있어 필요한 내용만 선택적으로 학습할 수 있습니다. 학습자는 기본 문법과 자료형부터 시작하여 차츰 포인터, 구조체, 메모리 관리 등의 고급 주제로 진행할 수 있습니다.

이 학습노트는 C 언어의 탄탄한 기초를 다지는 데 도움이 될 것이며, 더 나아가 C++, Java, Python 등 다른 프로그래밍 언어를 배우는 데에도 좋은 출발점이 될 것입니다. 프로그래밍의 기본 원리를 이해하고 메모리 관리와 같은 저수준 개념을 익히는 것은 어떤 언어를 사용하든 좋은 프로그래머가 되는 데 필수적입니다.

<div style="text-align: center">⁂</div>

[^1]: https://wikidocs.net/book/17681

[^2]: https://mryeo.tistory.com/72

[^3]: https://jehunseo.tistory.com/138

[^4]: https://makershackers.tistory.com/332

[^5]: https://seongkyun.github.io/others/2019/01/19/markdown/

[^6]: https://khw11044.github.io/blog/blog-etc/2020-12-21-markdown-tutorial/

[^7]: https://hongong.hanbit.co.kr/c언어/

[^8]: https://learn.microsoft.com/ko-kr/cpp/build/reference/md-mt-ld-use-run-time-library?view=msvc-170

[^9]: https://wikidocs.net/281757

[^10]: https://prinie.tistory.com/category/Programming/C - 학습노트

[^11]: https://blog.naver.com/chplog/222968846332

[^12]: https://gcamp.tistory.com/category/7_c_cpp

[^13]: https://wikidocs.net/230397

[^14]: https://www.inflearn.com/course/개발공부-c언어

[^15]: https://woo-dev.tistory.com/96

[^16]: https://webcorgi.tistory.com/19

[^17]: https://blog.naver.com/ggujune96/223516338629

[^18]: https://computer-science-student.tistory.com/366

[^19]: https://phalanx-club.tistory.com/164

[^20]: https://blog.naver.com/jooeun0502/221956294941

