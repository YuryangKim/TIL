# Type Casting

- 자료형을 변경하고 싶을 때 사용한다.

`int (3.4)
3`

  3.4의 자료형은 float 즉, 실수이다. 실수를 정수로 바꾸기 위해서는 int를 사용한다.

`float( 3 )` → 정수(int)를 실수(float)로
`int( 3.6 )` → 실수(float)를 정수(int)로
`str(1)`  → 정수(int)를 문자열(string)
`int('12')` → 문자열(string)을 정수(int)로

✔️`int('hello')` 는 인트로 바꿀 수 없다. (ValueError) 

# User input

> 사용자에게 값을 받기 위해서 input을 사용한다.

`input('How old are you?')`

How old are you? [            사용자가 입력한 나이  ex) 20                ]

'20'

사용자의 나이를 활용하고 싶다면?

`user_age = input('How old are you?')`

How old are you? 20

사용자의 12년 뒤의 나이를 알고 싶다면?

`print('당신의 12년 뒤 나이는', user_age + 12, '세 입니다.')`

- 이 경우 TypeError가 발생할 것이다.
- user_age를 int로 만들거나, 12를 str로 만들어야 한다.

### Type casting with input

   ✔️미리 타입 캐스팅을 해야 오류, 중복을 방지한다.

`int(input("How old are you?"))`

# String

- 한 번 선언하면 변경 불가

`'Python'`

Python

`'Python'[4]`

o

✔️ 0번부터 시작하므로 4번은 'h'가 아니라 'o'이다.

# String Functions

- Count - 특정 문자의 개수를 세는 메서드

문자열.count(x)
문자열.count(x, start)
문자열.count(x, start, end)

✔️ 대소문자를 구분한다.

✔️ 문자열이 없는 경우 0을 반환한다.

- Find - 특정 문자가 존재하는지 확인하고, 존재하는 위치의 index를 찾아주는 메서드

문자열.find(x)
문자열.find(x, start)
문자열.find(x, start, end)

✔️ 찾고자 하는 문자열이 없는 경우 -1을 반환한다.

- join - 문자열들을  String으로 합하는 메서드

subject = ['math', 'english', 'physics', 'biology']

👉 `result = ''.join(subject)`
    `print(result)`
👈 mathenglishphysicsbiology

   -  이 경우 공백 없이 join이 되었다.

   - 특정 문자열로 요소들을 join시키고 싶다면 `' '`안에 기준을 넣으면 된다.

subject = ['math', 'english', 'physics', 'biology']

👉 `result = ','.join(subject)`
    `print(result)`
👈`math,english,physics,biology`

- split - 문자열을 나눌 때 사용하는 메서드

`to_be_list = ' '.join('Fastcampus')
to_be_list.split(' ')`

`'F','a', 's', 't', 'c', 'a', 'm', 'p', 'u', 's'`

✔️ MEMO

조인 앞에 따옴표 그리고 join을 해주는 매개체
인의 대상이 되는거는 무조건 ()안
스플릿은 그 반대

- strip - 양쪽 문자열의 공백이나 문자열을 지워준다.
- lstrip - 가장 왼쪽에 있는 공백이나 문자열을 지워준다.
- rstrip - 가장 오른쪽에 있는 공백이나 문자열을 지워준다.

`target = '        ...,,,hello,python,,,...fastcampus,,'` 

`target.strip()`

`'...,,,hello, python...,,,fastcampus,,'`

 - 이처럼 white space를 지울 때는 `()` 안을 비워둔 채로 `strip( )`을 사용한다.

✔️문자열의 양쪽 끝에 있는 문자열을 지울 때 사용이 가능하지만, 문자열과 문자열 사이에 있는 것은 지워지지 않는다.

`target.strip(' .,')`

`'hello, pyhon,,,..fastcampus'`

# String Validator

-is가 앞에 있으면 의문형 / 맞다 틀리다

`str.isalnum()` 글자 혹은 숫자인가?
`str.isalpha()` 알파벳인가?
`str.isdigit()` 숫자로만 구성되어 있는가?
`str.islower()` 소문자?
`str.isupper()` 대문자인가?

# String Formatting

- old way

    `'I have a pen, I have a pineapple.'`
    `I have a %s, I have a %s. '%('apple','pen')`

    `'I have a apple, I have a pen.'`

- new way

    `'I have a {}, I have a {}'.format('pen','apple')`

    `'I have a apple, I have a apple.'`

    `'I have a {1}, I have a {0}'.format('pen',10)`

    `'I have a 10, I have a pen.'`

    - padding and align str

    `'{:>15}'.format('Python')`

    `'               Python'`

    -왼쪽에서부터 Python이라는 단어를 15번 띄워써라 

    `'{:15}'.format('Python')`

    `'Python               '`

    -Python이라는 단어로부터 오른쪽으로 15번 띄워써라

    `print('I have a {1:_>10}, I have a {0}'.format('pen','apple'))
    print('I have a {1:*^10}, I have a {0}'.format('pen','apple'))
    print('I have a {1:-<10}, I have a {0}'.format('pen','pineapple'))`

    `I have a _____apple, I have a pen
    I have a **apple***, I have a pen
    I have a pineapple-, I have a pen`
