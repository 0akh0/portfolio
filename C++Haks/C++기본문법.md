# 주석

코드에 설명을 추가할 때 사용합니다.

```cpp
// 한 줄 주석
/* 여러 줄
   주석 */
```




# 입출력

C++에서 표준 입출력은 `<iostream>` 헤더를 사용합니다.

```cpp
#include <iostream>
using namespace std;

int main() {
    cout << "Hello, World!" << endl;
    int age;
    cout << "나이를 입력하세요: ";
    cin >> age;
    cout << "당신의 나이는 " << age << "살입니다." << endl;
    return 0;
}
```

- `cout` : 출력(콘솔에 표시)
- `cin` : 입력(키보드로부터 값 받기)
- `endl` : 줄바꿈



# 변수 선언과 초기화

```cpp
int a = 10;         // 선언과 동시에 초기화
double b(3.14);     // 괄호 초기화
char c{'A'};        // 중괄호 초기화(C++11 이상)
```




# 상수 선언

```cpp
const int MAX = 100;
#define PI 3.14
```




# 자료형 변환

## 암시적(자동) 변환

컴파일러가 자동으로 타입을 변환합니다.

```cpp
int i = 10;
double d = i;   // int -> double로 자동 변환
```


## 명시적(강제) 변환

프로그래머가 직접 타입을 변환합니다.

```cpp
double d = 3.14;
int i = (int)d; // 소수점 이하 버려짐
```
