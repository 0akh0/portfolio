<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" class="logo" width="120"/>

# C/C++ 프로그래밍 학습 노트

이 학습 노트는 C/C++ 프로그래밍 언어의 기본 개념부터 고급 기능까지 체계적으로 정리한 문서입니다. 개인 학습과 참고용으로 작성되었으며, 지속적으로 업데이트될 예정입니다.

## 목차

- [개발 환경 설정](#%EA%B0%9C%EB%B0%9C-%ED%99%98%EA%B2%BD-%EC%84%A4%EC%A0%95)
- [C/C++ 기초](#cc-%EA%B8%B0%EC%B4%88)
- [객체지향 프로그래밍](#%EA%B0%9D%EC%B2%B4%EC%A7%80%ED%96%A5-%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D)
- [메모리 관리](#%EB%A9%94%EB%AA%A8%EB%A6%AC-%EA%B4%80%EB%A6%AC)
- [템플릿](#%ED%85%9C%ED%94%8C%EB%A6%BF)
- [STL(Standard Template Library)](#stlstandard-template-library)
- [파일 입출력](#%ED%8C%8C%EC%9D%BC-%EC%9E%85%EC%B6%9C%EB%A0%A5)
- [고급 주제](#%EA%B3%A0%EA%B8%89-%EC%A3%BC%EC%A0%9C)
- [실습 예제](#%EC%8B%A4%EC%8A%B5-%EC%98%88%EC%A0%9C)
- [참고 자료](#%EC%B0%B8%EA%B3%A0-%EC%9E%90%EB%A3%8C)


## 개발 환경 설정

### Visual Studio 설정하기

1. Visual Studio 2022 실행
2. "새 프로젝트 만들기(N)" 클릭
3. C++, Windows 설정 후 "빈 프로젝트" 선택
4. 프로젝트 이름과 저장 경로 설정 (예: CppLearning)
5. 솔루션 탐색기에서 "소스 파일" 우클릭 → "추가" → "새 항목(W)..." 선택
6. 파일 이름 main.cpp 설정 후 생성[^2]

### 기본 템플릿 코드

```cpp
#include &lt;bits/stdc++.h&gt;
using namespace std;

typedef long long ll;
typedef vector&lt;int&gt; vi;

int main() {
    ios::sync_with_stdio(0);
    cin.tie(0);
    
    cout &lt;&lt; "Hello World!" &lt;&lt; '\n';
    
    return 0;
}
```

> [!TIP]
> g++ 컴파일러로 소스 코드를 컴파일하려면: `g++ -std=c++11 -O2 -Wall test.cpp -o test`[^10]

## C/C++ 기초

### Hello World 출력하기

```cpp
#include &lt;iostream&gt;

int main() {
    std::cout &lt;&lt; "Hello World!" &lt;&lt; std::endl;
    return 0;
}
```

위 코드를 실행하면 콘솔 창에 "Hello World!"가 출력됩니다.[^2]

### 기본 문법 및 데이터 타입

#### 데이터 타입

```cpp
// 정수형
int a = 10;              // 4바이트 정수
long long b = 1000000000; // 8바이트 정수

// 실수형
float c = 3.14f;          // 4바이트 실수
double d = 3.141592;      // 8바이트 실수

// 문자형
char e = 'A';             // 1바이트 문자

// 문자열
std::string str = "Hello"; // 문자열

// 불리언
bool flag = true;         // 참/거짓
```


#### 입출력 최적화

효율적인 입출력을 위한 설정:

```cpp
ios::sync_with_stdio(0); // C와 C++ 스트림 동기화 해제
cin.tie(0);              // cin과 cout의 묶음 해제

// endl 대신 '\n' 사용하기
cout &lt;&lt; "Hello World!" &lt;&lt; '\n';  // 더 효율적인 방법
```


## 객체지향 프로그래밍

### 클래스와 객체

```cpp
class Person {
private:
    std::string name;
    int age;
    
public:
    // 생성자
    Person(std::string n, int a) : name(n), age(a) {}
    
    // 메서드
    void introduce() {
        std::cout &lt;&lt; "안녕하세요! 제 이름은 " &lt;&lt; name &lt;&lt; "이고, " 
                  &lt;&lt; age &lt;&lt; "살입니다." &lt;&lt; std::endl;
    }
    
    // getter/setter
    std::string getName() { return name; }
    void setName(std::string n) { name = n; }
    
    int getAge() { return age; }
    void setAge(int a) { age = a; }
};
```


#### 객체 생성 및 사용

```cpp
// 스택에 객체 생성
Person person1("홍길동", 25);
person1.introduce();

// 힙에 객체 생성 (동적 할당)
Person* person2 = new Person("김철수", 30);
person2-&gt;introduce();

// 메모리 해제
delete person2;
```


### 상속

```cpp
class Student : public Person {
private:
    std::string school;
    int grade;
    
public:
    Student(std::string n, int a, std::string s, int g) 
        : Person(n, a), school(s), grade(g) {}
    
    void study() {
        std::cout &lt;&lt; getName() &lt;&lt; "이(가) " &lt;&lt; school &lt;&lt; "에서 공부중입니다." &lt;&lt; std::endl;
    }
    
    // 오버라이딩
    void introduce() {
        Person::introduce();  // 부모 클래스 메서드 호출
        std::cout &lt;&lt; school &lt;&lt; " " &lt;&lt; grade &lt;&lt; "학년입니다." &lt;&lt; std::endl;
    }
};
```


## 메모리 관리

### 메모리 구조

메모리 공간은 크게 네 부분으로 나뉩니다:

- **스택(Stack)**: 지역변수, 매개변수 등이 할당. 함수 영역을 벗어나면 자동 소멸
- **힙(Heap)**: 동적으로 할당하는 메모리 공간. 프로그래머에 의해 할당/해제
- **데이터(Data)**: 전역변수, 정적변수, 초기화한 배열 등이 할당
- **코드(Code)**: 프로그램의 명령어나 기계어 명령이 존재[^7]


### 동적 메모리 할당/해제

```cpp
// 단일 객체 할당/해제
int* p = new int;        // 할당
*p = 10;                 // 사용
delete p;                // 해제
p = nullptr;             // 널 포인터로 초기화

// 배열 할당/해제
int* arr = new int[^10];  // 10개 정수 배열 할당
arr[^0] = 5;              // 사용
delete[] arr;            // 배열 해제
arr = nullptr;           // 널 포인터로 초기화
```

> [!CAUTION]
> 메모리 해제 후 포인터는 NULL로 꼭 초기화해 에러를 방지해야 합니다. `new`=>`delete`, `new[]`=>`delete[]`로 쌍을 맞춰 사용해야 합니다.[^7]

### 참조(Reference)

C++에서 지원하는 변수 타입인 참조(Reference)는 다른 객체나 값의 별칭으로 사용됩니다.

```cpp
// 기본 참조 사용법
int a = 10;
int&amp; ref = a;     // a의 참조(별칭)
ref = 20;         // a의 값도 20으로 변경됨

// 함수에서 참조 사용
void swap(int&amp; a, int&amp; b) {
    int temp = a;
    a = b;
    b = temp;
}

int x = 5, y = 10;
swap(x, y);       // x와 y의 값이 교환됨
```


## 템플릿

템플릿은 타입에 의존하지 않는 코드를 작성할 수 있게 해주는 강력한 기능입니다.

### 함수 템플릿

```cpp
// 기본 함수 템플릿
template &lt;typename T&gt;
T sum(T a, T b) {
    return a + b;
}

// 사용 예
int result1 = sum&lt;int&gt;(10, 20);              // 30
double result2 = sum&lt;double&gt;(3.14, 2.71);    // 5.85
std::string s = sum&lt;std::string&gt;("Hello, ", "World!"); // "Hello, World!"
```


### 다중 타입 템플릿

```cpp
template &lt;class T1, class T2&gt;
void printAll(T1 a, T2 b) {
    std::cout &lt;&lt; "T1: " &lt;&lt; a &lt;&lt; std::endl;
    std::cout &lt;&lt; "T2: " &lt;&lt; b &lt;&lt; std::endl;
}

// 사용 예
printAll&lt;std::string, int&gt;("Age", 25);  // 명시적 타입 지정
printAll("Name", "John");               // 타입 추론
```


### 클래스 템플릿

```cpp
template &lt;typename T&gt;
class Box {
private:
    T content;
    
public:
    Box(T item) : content(item) {}
    T getContent() { return content; }
    void setContent(T item) { content = item; }
};

// 사용 예
Box&lt;int&gt; intBox(123);
Box&lt;std::string&gt; stringBox("Hello Template");
```


## STL(Standard Template Library)

### 주요 컨테이너

```cpp
// 벡터 (동적 배열)
vector&lt;int&gt; v = {1, 2, 3, 4, 5};
v.push_back(6);  // 요소 추가
v.pop_back();    // 마지막 요소 제거

// 리스트 (이중 연결 리스트)
list&lt;int&gt; l = {1, 2, 3};
l.push_front(0); // 앞에 요소 추가
l.push_back(4);  // 뒤에 요소 추가

// 맵 (키-값 쌍)
map&lt;string, int&gt; m;
m["apple"] = 5;
m["banana"] = 3;
```


### 알고리즘

```cpp
// 정렬
vector&lt;int&gt; v = {5, 2, 8, 1, 3};
sort(v.begin(), v.end());  // 오름차순 정렬: 1, 2, 3, 5, 8

// 이진 탐색
bool found = binary_search(v.begin(), v.end(), 3);  // true 반환

// 최소/최대 요소 찾기
auto min_it = min_element(v.begin(), v.end());  // 1을 가리키는 반복자
auto max_it = max_element(v.begin(), v.end());  // 8을 가리키는 반복자
```


## 파일 입출력

```cpp
#include &lt;fstream&gt;

// 파일 쓰기
ofstream outFile("example.txt");
if (outFile.is_open()) {
    outFile &lt;&lt; "Hello, File I/O!" &lt;&lt; endl;
    outFile &lt;&lt; "Second line." &lt;&lt; endl;
    outFile.close();
}

// 파일 읽기
ifstream inFile("example.txt");
if (inFile.is_open()) {
    string line;
    while (getline(inFile, line)) {
        cout &lt;&lt; line &lt;&lt; endl;
    }
    inFile.close();
}
```


## 고급 주제

### 함수 포인터와 멤버 포인터

```cpp
// 함수 포인터
int add(int a, int b) { return a + b; }
int subtract(int a, int b) { return a - b; }

int (*operation)(int, int);  // 함수 포인터 선언
operation = add;             // add 함수 가리키기
int result = operation(5, 3); // result = 8

// 멤버 함수 포인터
class Calculator {
public:
    int add(int a, int b) { return a + b; }
    int subtract(int a, int b) { return a - b; }
};

int (Calculator::*memFuncPtr)(int, int);  // 멤버 함수 포인터 선언
memFuncPtr = &amp;Calculator::add;            // add 멤버 함수 가리키기

Calculator calc;
int result = (calc.*memFuncPtr)(5, 3);    // result = 8
```


### 스마트 포인터

```cpp
#include &lt;memory&gt;

// unique_ptr: 소유권 독점
std::unique_ptr&lt;int&gt; up(new int(5));
// up2 = up;  // 컴파일 에러! 복사 불가
std::unique_ptr&lt;int&gt; up2 = std::move(up);  // 소유권 이전

// shared_ptr: 공유 소유권, 참조 카운팅
std::shared_ptr&lt;int&gt; sp1(new int(10));
std::shared_ptr&lt;int&gt; sp2 = sp1;  // 참조 카운트 증가
std::cout &lt;&lt; *sp1 &lt;&lt; ", " &lt;&lt; *sp2 &lt;&lt; std::endl;  // 10, 10
std::cout &lt;&lt; "참조 카운트: " &lt;&lt; sp1.use_count() &lt;&lt; std::endl;  // 2 출력

// weak_ptr: 순환 참조 방지
std::weak_ptr&lt;int&gt; wp = sp1;
```


## 실습 예제

### 예제 1: 학생 성적 관리 프로그램

```cpp
#include &lt;iostream&gt;
#include &lt;vector&gt;
#include &lt;string&gt;
#include &lt;algorithm&gt;
using namespace std;

class Student {
private:
    string name;
    int korScore;
    int engScore;
    int mathScore;
    
public:
    Student(string n, int k, int e, int m) 
        : name(n), korScore(k), engScore(e), mathScore(m) {}
    
    string getName() const { return name; }
    
    int getTotalScore() const {
        return korScore + engScore + mathScore;
    }
    
    float getAverage() const {
        return getTotalScore() / 3.0f;
    }
    
    void printInfo() const {
        cout &lt;&lt; "이름: " &lt;&lt; name &lt;&lt; "\n"
             &lt;&lt; "국어: " &lt;&lt; korScore &lt;&lt; ", "
             &lt;&lt; "영어: " &lt;&lt; engScore &lt;&lt; ", "
             &lt;&lt; "수학: " &lt;&lt; mathScore &lt;&lt; "\n"
             &lt;&lt; "총점: " &lt;&lt; getTotalScore() &lt;&lt; ", "
             &lt;&lt; "평균: " &lt;&lt; getAverage() &lt;&lt; endl;
    }
};

int main() {
    vector&lt;Student&gt; students;
    
    // 학생 추가
    students.push_back(Student("홍길동", 90, 85, 95));
    students.push_back(Student("김철수", 75, 80, 85));
    students.push_back(Student("이영희", 95, 90, 92));
    
    // 총점 기준 내림차순 정렬
    sort(students.begin(), students.end(), 
        [](const Student&amp; a, const Student&amp; b) {
            return a.getTotalScore() &gt; b.getTotalScore();
        });
    
    // 정보 출력
    cout &lt;&lt; "===== 학생 성적 목록 (총점 내림차순) =====" &lt;&lt; endl;
    for (const auto&amp; student : students) {
        student.printInfo();
        cout &lt;&lt; "-------------------------------" &lt;&lt; endl;
    }
    
    return 0;
}
```


## 참고 자료

### 도서 정보

- **명품 C++ Programming** - 황기태/생능출판사[^3]


### C++ 주요 Chapter

1. C++ 시작
2. C++ 프로그래밍의 기본
3. 클래스와 객체
4. 객체 포인터와 객체 배열, 객체의 동적 생성
5. 함수와 참조, 복사 생성자
6. 함수 중복과 static 멤버
7. 프렌드와 연산자 중복
8. 상속
9. 가상 함수와 추상 클래스
10. 템플릿과 표준 템플릿 라이브러리(STL)[^3]

### 추가 학습 주제

- 멀티스레드 프로그래밍
- 네트워크 프로그래밍
- 그래픽 프로그래밍
- 데이터베이스 연동
- 디자인 패턴 적용

> [!NOTE]
> 이 학습 노트는 지속적으로 업데이트 될 예정입니다. 새로운 내용이나 오류를 발견하시면 이슈를 등록해주세요.

---

작성일: 2025-04-22

<div style="text-align: center">⁂</div>

[^1]: https://novlog.tistory.com/entry/GitHub-3-README-파일-작성-방법-마크다운-MarkDown

[^2]: https://he11oworld.tistory.com/entry/CC-기초-강의-CC-개발-시작하기-Hello-World-출력하기

[^3]: https://github.com/Lee-JaeWon/Cpp_study/blob/main/README.md

[^4]: https://fienestar.github.io/tip/2020/05/23/마크다운-작성법/

[^5]: https://tbr74.tistory.com/entry/깃허브-스타일-마크다운-적용하기

[^6]: https://mingyum119.tistory.com/77

[^7]: https://paikwiki.github.io/2021/03/cpp-module-01

[^8]: https://yeonco.tistory.com/46

[^9]: https://claris.tistory.com/51

[^10]: https://singularis7.tistory.com/5

[^11]: https://kimyir.tistory.com/96

[^12]: https://gist.github.com/ihoneymon/652be052a0727ad59601

[^13]: https://docs.github.com/ko/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax

[^14]: https://ansohxxn.github.io/blog/markdown/

[^15]: https://github.com/ah01/h2md

[^16]: https://computer-science-student.tistory.com/366

[^17]: https://github.com/CppKorea/CppCoreGuidelines

[^18]: https://sehoon1207.github.io/markdown/markdown-_0_basic/

[^19]: https://product.kyobobook.co.kr/detail/S000001804733

[^20]: https://velog.io/@harimad/Markdown-Badges

[^21]: https://andongmin.com/docs/cpp

[^22]: https://bollt.tistory.com/16

[^23]: https://www.aladin.co.kr/shop/wproduct.aspx?ItemId=170132187

[^24]: https://mimir-study-note.tistory.com/4

[^25]: https://m.yes24.com/goods/detail/78660186

[^26]: https://mimir-study-note.tistory.com/11

[^27]: https://github.com/YoungHaKim7/cpp_training2024/blob/main/README.md

[^28]: https://github.com/dremdeveloper/codingtest_cpp

[^29]: https://github.com/simnalamburt/snucse/blob/main/PL/note.md

[^30]: https://github.com/jacking75/NewbieGameServerProgrammerLearningMaterials/blob/main/README.md

[^31]: https://search.kyobobook.co.kr/search?gbCode=TOT\&target=total

[^32]: https://github.com/pr0gr4m/Newbie-Guideline/blob/main/README.md

[^33]: https://docs.github.com/ko/get-started/writing-on-github/working-with-advanced-formatting/creating-diagrams

[^34]: https://www.mongodb.com/ko-kr/docs/languages/cpp/cpp-driver/current/whats-new/

[^35]: https://datamoney.tistory.com/244

[^36]: https://echung93.tistory.com/entry/Github-글-접고-펼치기-details태그

[^37]: https://gist.github.com/bakyeono/9948714

[^38]: https://dev-youngjun.tistory.com/51

