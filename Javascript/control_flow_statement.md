# Chapter 4. 변수 ~ Chapter 8.제어문

강의 일시: 2021년 3월 10일
해당 주제: javascript

1. 할당 

    1) 초기화 

    ```jsx
    console.log(score); // undefined

    var score; // 1. 변수 선언 
    scroe = 80; // 2. 값의 할당 

    console.log(score); // 80
    ```

    - 초기화란 변수가 선언된 이후 최초로 값을 할당하는 것
    - var 키워드로 선언한 변수는 `undefined`로 암묵적인 초기화가 자동 수행된다.
    - 만약 초기화 단계를 거치지 않으면 확보된 메모리 공간에는 이전에 다른 애플리케이션이 사용했던 값이 남아 있을 수 있다. 이러한 값을 쓰레기 값이라고 한다.

    2) 할당

    - 변수 선언은 런타임 이전에 먼저 실행되고 값의 할당은 런타임에 실행된다. 따라서 2시점에는 undefined에서 새롭게 할당한 숫자 값 80으로 처음 값을 할당하는 단계도 사실상 재할당 단계이다.
    - 80이라는 값은 새로운 메모리 공간에 할당 된다. 이 경우 값이 들어 있는 메모리 공간은  확보되어 사용되고 있는 것을 allocated라고 하고,

    3) 재할당 

    - 변수에 저장된 값을 다른 값으로 변경한다.
    - score 값을 80->100->80으로 변경한다면 원래 80이 저장되어 있던 메모리에 다시 접근할 것 같지만 원칙적으로 원시 값은 항상 새롭게 만들기 때문에 새로운 메모리 공간에 다시 80 값을 저장한다.
2. 식별자 네이밍 규칙
    - 식별자의 명칭이 되는 문자열을 결정하기 위한 규칙
    - 식별자는 어떤 값을 구별해서 식별해 낼 수 있는 (파일인 경우 폴더 내에서) 고유한 이름
    - 식별자는 특수문자를 제외한 문자, 숫자, 언더스코어(_), 달러 기호($)를 포함할 수 있다.
    - 단 식별자는 숫자로 시작하는 것은 허용하지 않는다
    - 예약어는 식별자로 사용할 수 없다
3. 예약어
    - 프로그래밍 언어에서 사용되고 있거나 사용될 예정인 단어 ex) break class continue const 등
4. 네이밍 컨벤션
    - 카멜 케이스(camelCase) : 앞에 오는 단어 첫번째 글자는 소문자로, 뒤에 오는 단어 단어의 첫번째는 대문자로 사용
    - 스네이크 케이스(snake_case) : 언더바 _ 사용
    - 파스칼 케이스(PascalCase) : 단어의 첫번째 글자를 모두 대문자로 사용
    - 주로 변수와 함수 이름에는 카멜 케이스를, 생성자 함수, 클래스에는 파스칼 케이스를 많이 사용한다.
5. 값(value), 표현식(expression)

    ```jsx
    var a = 1+2;
    a // >> 3
    ```

    - 1+2를 3으로 만드는 행위를 '평가'라고 한다.
    - 이때 1+2는 표현식이라고 한다. 표현식은 평가되어져서 값을 만들어 내는 것이다.
    - 값은 표현식이 평가 되어져서 만들어진 결과이고 값이 메모리 안에 들어 간다.
    - 값도, 리터럴도 표현식이다.
    - 표현식은 값이지만 값은 표현식이 아니다. 즉 표현식은 값을 포괄하고 있다.
6. 리터럴(literal)

    ```jsx
    var x = 1;
    ```

    - 리터럴이란 사람이 이해하고 있는 기호를 값으로 인식하게 하는 표기 방법이다. 값 자체
    - `x`는 식별자라고 하는데, 식별자도 표현식이다.
    - `=` 연산자 뒤에 있는 값을 식별자에게 바인딩하라는 뜻
    - `1` 은 숫자값을 나타내는 리터럴이라고 한다.
    - `;`  `var x =1;`까지가 하나의 명령이라는 뜻이며 국어에서 마침표와 같은 의미를 가진다.
7. 문(statement), 토큰, 표현식인 문 

    ```jsx
    var sum = 1 + 2;
    ```

    - 문이란 프로그램을 구성하는 기본 단위이자 최소 실행 단위이다. 명령의 최소 단위를 말한다.
    - 토큰이란 의미가 있는 최소 단위를 토큰이라고 한다.
    - 세미콜론 `;`으로 끝난다.
    - `var x = 1;` 처럼 명령의 한 줄이 하나의 문이다.
    - 여기서 1은 토큰이라고 부를 수도 있고, 리터럴이라고도 부를 수 있다.
    - `1+2;` 는 표현식인 문(표현식이자 문), 값으로 평가될 수 있는 문이다.
8. 표현식이 아닌 문 
    - 표현식이 아닌 문은 변수에 할당 할 수 없다. 변수에 할당하면 에러가 생긴다.
    - if문은 표현식이 아니다.
    - 선언문은 표현식이 아니다.
    - 삼항 조건문은 표현식이므로 변수에  할당 할 수 있다.
9. 삼항 조건 연산자 

    `조건식 ? 조건식이 true일 때 반환할 값 : 조건식이 false일 때 반환할 값`

    - 표현식인 문이기 때문에 변수에 바로 할당이 가능하므로 if 대신 변수에 바로 할당할 때 사용한다.
10. 데이터 타입
    - 줄여서 타입이라고도 한다.
    - 자바스크립트는 6개의 원시 타입과 1개의 객체 타입 총 7개의 데이터 타입을 제공한다.
11. 원시 타입
    - 숫자 타입: 자바스크립트에서는 정수와 실수를 따로 구분하지 않기 때문에, number type이라고 통틀어 말한다. 숫자 타입에는 세가지의 특별한 값도 표현이 가능하다.
        - Infinity : 양의 무한대 / 8바이트 이상의 공간의 수를 표기할 때 무한대로 나타낼 수 있다.
        - Infinity : 음의 무한대
        - NaN : 산술 연산 불가(not-a-number)
    - 문자열 타입: 텍스트 데이터를 나타내는 데 사용한다. 문자열은 0개 이상의 16비트 유니코드 문자들의 집합으로 전 세계 대부분의 문자를 표현할 수 있다. 작은 따옴표(‘’), 큰따옴표(“”) 또는 백틱(``)으로 텍스트를 감싼다.
    - 불리언 타입: true, false로 표현할 수 있는 타입
    - undefined 타입: undefined 타입 값에는 undefined이 유일하다.
    - null 타입 : 변수 값이 없다는 것을 표현하고 싶을 때 null을 할당한다
    - symbol 타입: 외부에 노출되지 않으며 다른 값과 중복되지 않는 유일무이한 값
12. 왜 데이터 타입이 중요한가
    - 공간 크기를 결정하기 위해서
    - 값을 참조할 때 데이터 사이즈를 결정하기 위해서
    - 2진수를 어떻게 해석할지 결정하기 위해서
13. 언매니지드 언어(unmanaged language) vs 매니지드 언어(managed language)
    - 사실은 컴퓨터 입장에서 이야기를 하자면 개발자가 메모리 관리를 해서 스스로 메모리 관리를 할 수 있느냐 없느냐 방식에 따라 다르다.
    - 언매니지드 언어는 대표적으로 C가 있으며 개발자가 주도하여 메모리 관리가 가능하다.
    - 매니지드 언어는 대표적으로 Javascript가 있으며 가비지 컬렉터가 존재하며 개발자가 명시적으로 관리가 불가능하다.
14. 동적타이핑 vs 정적타이핑
15. 제어문
- 코드는 왼쪽에서 오른쪽으로, 위에서 아래쪽의 흐름(flow)으로 순차적으로 진행된다. 제어문은 주어진 조건에 따라 코드블록을 실행하거나 반복할 때 사용한다.
- 따라서 코드의 흐름을 이해하기 어렵게 하기 때문에 가독성을 해친다.
- 블록문 : 0개 이상의 문을 중괄호로 묶은 것으로, 코드 블록 또는 블록이라고 부르기도 한다. 보통의 문은 종료의 의미로 세미콜론을 ; 붙이지만 블록문은 ;을 붙이지 않는다.
- 조건문 : 조건식(conditional expression)의 값에 따라 코드 블록(블록문)의 실행을 결정한다. 조건식은 불리언 값 `True` `False`로 평가될 수 있는 표현식이다.
    - 조건문에는 if else문과 switch문이 있다.

        ```jsx
        if (조건식1) {
          // 조건식1이 참이면 이 코드 블록이 실행된다.
        } else if (조건식2) {
          // 조건식2가 참이면 이 코드 블록이 실행된다.
        } else {
          // 조건식1과 조건식2가 모두 거짓이면 이 코드 블록이 실행된다.
        }
        ```

    - if else 문에서는 코드 블록 내의 문이 하나뿐이라면 중괄호는 생략 가능하다.
    - else if 문과 else 문은 옵션이다. 즉, 사용할 수도 있고 사용하지 않을 수도 있다. if 문과 else 문은 한번만 사용할 수 있고, else if 문은 여러 번 사용할 수 있다.
    - if else 문은 삼항 조건 연산자로 대체 가능하다.

        ```jsx
        switch (표현식) {
          case 표현식1:
            switch 문의 표현식과 표현식1이 일치하면 실행될 문;
            break;
          case 표현식2:
            switch 문의 표현식과 표현식2가 일치하면 실행될 문;
            break;
          default:
            switch 문의 표현식과 일치하는 표현식을 갖는 case 문이 없을 때 실행될 문;
        }
        ```

    - default 문에는 break 문을 생략하는 것이 일반적이다. default 문은 switch 문의 맨 마지막에 위치하므로 default 문의 실행이 종료되면 switch 문을 빠져나간다. 따라서 별도로 break 문이 필요 없다.
- 반복문
    - 반복문(loop statement)은 조건식의 평가 결과가 참인 경우 코드 블록을 실행한다. 그 후 조건식을 다시 평가히여 여전히 참인 경우 코드 블록을 다시 실행한다. 이는 조건식이 거짓일 때까지 반복된다.
- 보조 제어문 : 보조제어문에는 break와 continue가 있다.