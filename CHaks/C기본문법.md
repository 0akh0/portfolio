# 기본 문법
C 언어의 기본 문법은 프로그램 작성의 기초가 되는 규칙과 구성 요소를 포함합니다.

## 주석
주석은 프로그램 코드에 설명을 추가하는 데 사용되며, 컴파일러에 의해 무시됩니다.
```C

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
```C

int a = 10;  // 변수 선언과 초기화
printf("Hello\n");  // 함수 호출

```

## 블록
중괄호({})로 묶인 코드 블록은 여러 문장을 하나의 단위로 그룹화합니다.
```C

if (condition) {
// 이 블록 내의 모든 문장은
// condition이 참일 때 실행됩니다
statement1;
statement2;
}

```

## 들여쓰기
들여쓰기는 코드의 가독성을 높이기 위해 사용되며, 일반적으로 4개의 공백 또는 탭 문자를 사용합니다.
```C

if (condition) {
statement1;
if (another_condition) {
statement2;
}
}

```
