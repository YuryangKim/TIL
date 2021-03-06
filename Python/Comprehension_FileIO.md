# Comprehension

> 리스트 안에 각각의 자료에 변형을 주고 싶을 때 사용

> 기존 리스트를 참고하여 새로운 리스트를 생성할 때 사용

- **비슷한 표현들**
    - Set Comprehension
    - Dictionary Comprehension
    - Parallel list Comprehension

- **List comprehension**
    - 문제1) numbers 자료 중 짝수일때만 제곱하여 new_numbers에 추가

        `numbers = [1,2,3,4,5]
        new_numbers = []

        for item i numbers:
              if item%2 == 0:
                   print(item**2)`

        `new_numbers = [item**2 for item in numbers if  item%2==0]
        new_numbers`

    - 문제2) numbers 짝수일 때만 제곱하여 new numbers에 추가하고, 그렇지 않을 경우 세제곱하여 new_numbers에 추가

        `numbers = [1,2,3,4,5]
        numbers = [item**2 if item%2==0 else item**3 for item in numbers] 
        new_numbers`

- **Dictionary comprehension**
    - 기존의 딕셔너리를 활용해 새로운 딕셔너리를 만들고 싶을 때 사용
    - 문제) value의 length가 6이 넘는 것만 가져와라

        `fruits = {'a':'apple', 'b':'banana','c':'coconut','d':'durian'}
        over_six_fruits = {}
        for k,v in fruits.items():
        if len(v) >  6:
        over_six_fruits['k'] = v #이거는 statement
        over_six_fruits`

        {'k': 'coconut'}

        - dict.get()
        - dict.setdefault()

# File IO

`f = open(filenmae, mode)
f.close()`

- mode(b:binary mode(default:text)
- r(b) - 읽기모드
- w(b) - 쓰기모드
- a(b) - 추가모두 (파일의 마지막에 새로운 내용 추가)
- **CSV format**

    `import csv

    with open('./customers.csv', newline='') as customer_csv:
        customers = csv.reader(customer_csv)
        for row in customers:
            print(row)`

- **file I/O with json(JavaScriopt Object Notation)**
    - 효율적으로 데이터를 저장하고 교환하는데 사용하는 텍스트 데이터의 포맷 중 하나

    `import jason

    data = {'users':[
    {'name':'KD Hong', 'locale':'Seoul, KR'},
    {'name': 'John Doe', 'locale':'New York, US'},
    {'name': 'Jane Doe', 'locale':'London, UK'}
    ]}`

    `with open('users.json', 'w', encoding='utf-8') as f: 
        json.dump(data, f)`  #저장

    `with open('users.json', 'r', encoding='utf-8') as f: 
        des_data = json.load(f)` #불러오기

    `for row in des_data['users']:
        print('{} is from {}.'.format(row['name'],row['locale']))`   

    KD Hong is from Seoul, KR.
    John Doe is from New York, US.
    Jane Doe is from London, UK.
