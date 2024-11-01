# 📑 java-lotto-precourse 로또
> 간단한 로또 발매기를 구현한다.

<br>
<br>

## 구현할 기능 목록

- [x] 입력
    - [x] 로또 구입 금액을 입력받는다. 
    - [x] 당첨번호를 입력받는다.
    - [x] 보너스 번호를 입력받는다.
    - [x] 사용자가 잘못된 값을 입력할 경우 그 부분부터 입력을 다시 받는다.
    
<br>

- [x] 로또 
    - [x] 구입 금액에 해당하는 만큼 로또를 발행한다. 로또 1장의 가격은 1,000원이다.
    - [x] 중복되지 않는 6개의 로또 번호를 생성한다.
    - [x] 로또 번호가 당첨 기준에 부합하는 만큼 당첨 금액을 저장한다.
        - 1등: 6개 번호 일치 / 2,000,000,000원
        - 2등: 5개 번호 + 보너스 번호 일치 / 30,000,000원
        - 3등: 5개 번호 일치 / 1,500,000원
        - 4등: 4개 번호 일치 / 50,000원
        - 5등: 3개 번호 일치 / 5,000원
    - [x] 수익율을 계산한다.

<br>

- [x] 출력
    - [x] 입력 전 안내문구를 출력한다.
    - [x] 발행한 로또 수량 및 번호를 출력한다. 로또 번호는 오름차순으로 정렬하여 보여준다.
    - [x] 당첨 내역을 출력한다.
    - [x] 수익률을 출력한다. 수익률은 소수점 둘째 자리에서 반올림 한다.
    - [x] 예외 발생 시 에러 문구를 출력한다.


<br>

- [x] 예외 처리
    - [x] 사용자가 잘못된 값을 입력할 경우 예외 처리 한다.
    - [x] 로또 구입 금액이 1000원으로 나누어 떨어지지 않는 경우 예외 처리한다.


<br>
<br>

## 실행 결과 예시
``` 
구입금액을 입력해 주세요.
8000

8개를 구매했습니다.
[8, 21, 23, 41, 42, 43] 
[3, 5, 11, 16, 32, 38] 
[7, 11, 16, 35, 36, 44] 
[1, 8, 11, 31, 41, 42] 
[13, 14, 16, 38, 42, 45] 
[7, 11, 30, 40, 42, 43] 
[2, 13, 22, 32, 38, 45] 
[1, 3, 5, 14, 22, 45]

당첨 번호를 입력해 주세요.
1,2,3,4,5,6

보너스 번호를 입력해 주세요.
7

당첨 통계
---
3개 일치 (5,000원) - 1개
4개 일치 (50,000원) - 0개
5개 일치 (1,500,000원) - 0개
5개 일치, 보너스 볼 일치 (30,000,000원) - 0개
6개 일치 (2,000,000,000원) - 0개
총 수익률은 62.5%입니다.
```

<br>
<br>

## 프로그래밍 요구 사항 1
- JDK 21 버전에서 실행 가능해야 한다.
- 프로그램 실행의 시작점은 Application의 main()이다.
- build.gradle 파일은 변경할 수 없으며, 제공된 라이브러리 이외의 외부 라이브러리는 사용하지 않는다.
- 프로그램 종료 시 System.exit()를 호출하지 않는다.
- 프로그래밍 요구 사항에서 달리 명시하지 않는 한 파일, 패키지 등의 이름을 바꾸거나 이동하지 않는다.
- 자바 코드 컨벤션을 지키면서 프로그래밍한다.
    - 기본적으로 Java Style Guide를 원칙으로 한다.

<br>

## 프로그래밍 요구 사항 2
- indent(인덴트, 들여쓰기) depth를 3이 넘지 않도록 구현한다. 2까지만 허용한다.
    - 예를 들어 while문 안에 if문이 있으면 들여쓰기는 2이다.
    - 힌트: indent(인덴트, 들여쓰기) depth를 줄이는 좋은 방법은 함수(또는 메서드)를 분리하면 된다.
- 3항 연산자를 쓰지 않는다.
- 함수(또는 메서드)가 한 가지 일만 하도록 최대한 작게 만들어라.
- JUnit 5와 AssertJ를 이용하여 정리한 기능 목록이 정상적으로 작동하는지 테스트 코드로 확인한다.
    - 테스트 도구 사용법이 익숙하지 않다면 아래 문서를 참고하여 학습한 후 테스트를 구현한다.
        - JUnit 5 User Guide
        - AssertJ User Guide
        - AssertJ Exception Assertions
        - Guide to JUnit 5 Parameterized Tests

<br>

## 프로그래밍 요구 사항 3
- 함수(또는 메서드)의 길이가 15라인을 넘어가지 않도록 구현한다.
    - 함수(또는 메서드)가 한 가지 일만 잘 하도록 구현한다.
- else 예약어를 쓰지 않는다.
    - else를 쓰지 말라고 하니 switch/case로 구현하는 경우가 있는데 switch/case도 허용하지 않는다.
    - 힌트: if 조건절에서 값을 return하는 방식으로 구현하면 else를 사용하지 않아도 된다.
- Java Enum을 적용하여 프로그램을 구현한다.
- 구현한 기능에 대한 단위 테스트를 작성한다. 단, UI(System.out, System.in, Scanner) 로직은 제외한다.
    - 단위 테스트 작성이 익숙하지 않다면 LottoTest를 참고하여 학습한 후 테스트를 작성한다.

<br>
<br>

## 2주차 공통 피드백 참고

1. 값을 하드코딩하지 않고 상수를 사용한다.

2. 클래스는 상수, 멤버 변수, 생성자, 메서드 순으로 작성한다. 

3. 변수 이름에 자료형은 사용하지 않는다.

4. 한 메서드가 한 가지 기능만 담당하게 한다.
    - 예를 들어, 안내 문구 출력, 사용자 입력 처리, 유효값 검증 등의 작업을 한 함수에 모두 포함하는 대신, 이를 각기 다른 함수로 분리해 본다.

5. 메서드가 한 가지 기능을 하는지 확인하는 기준을 세운다.
    - 여러 메서드에서 중복되는 코드가 있다면 이를 별도 메서드로 분리하는 것을 고려한다. 메서드의 길이가 길어지면 여러 기능을 포함하고 있을 가능성이 커지므로, 15라인이 넘지 않도록 구현하면 의식적으로 메서드를 분리하는 연습을 할 수 있다.

6. 테스트를 작성하는 이유에 대해 본인의 경험을 토대로 정리해본다.

7. 처음부터 큰 단위의 테스트를 만들지 않는다.