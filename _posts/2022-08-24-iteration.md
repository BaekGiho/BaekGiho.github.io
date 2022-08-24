# 반복문


```python
# while문(반복문)
# 초기값, 조건식, 증감(증감이 있어야 무한반복에 빠지지 않는다)
# 쓰는방식은 if문이랑 비슷
# 조건이 참인동안에 출력문을 반복해서 수행
a = 0

while a < 10:
    print("hello")
    a += 1
```

    hello
    hello
    hello
    hello
    hello
    hello
    hello
    hello
    hello
    hello
    


```python
# break문(반복문을 제어) - 반복문을 탈줄할때 쓰는거
a = 0
while a < 10:
    if a == 3:
        break
    print('hello')
    a += 1
    
# 주로 if문과 같이 쓴다
```

    hello
    hello
    hello
    


```python
# else문
a = 0
while a < 10:
    print(a)
    a += 1
else:
    print("else")
```

    0
    1
    2
    3
    4
    5
    6
    7
    8
    9
    else
    


```python
# 응용
# 합계
n = 1
sum = 0

while n <= 10:
    print(n)
    sum += n
    n += 1

print("합계 : ", sum)
```

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    합계 :  55
    


```python
# for문(반복문)
'''
for 변수 in 반복가능데이터:
    수행문장1
    수행문장2
'''

# while문과 비슷하다 하지만 조건이 없다! 반복가능 데이터 안에 요소가 얼마나 있느냐 따라 다름
# 리스트, 튜플, 세트, 딕셔너리 등을 돌려주는 반복문
# 리스트 데이터
a = [1, 2, 3, 4, 5]

for i in a: 
    #in 뒤에 반복시켜줄 리스트나 튜플이나 등등이 온다
    print(i)
```

    1
    2
    3
    4
    5
    


```python
# 리스트 안에 튜플이 들어있는 데이터
a = [(1, 2), (3, 4), (5, 6)]
for i, j in a:  
    #튜플이 나오면서 언패킹됨
    print(i, j)
    
for t in a:  
    #이렇게 하면 언패킹 안되고 튜플로 그냥 나오는데 나중에 또 풀려면 귀찮으니까 언패킹 하는게 편함
    print(t)
```

    1 2
    3 4
    5 6
    (1, 2)
    (3, 4)
    (5, 6)
    


```python
# 튜플 데이터
a = (1, 2, 3, 4, 5)
for i in a:
    print(i)
```

    1
    2
    3
    4
    5
    


```python
# 세트 데이터
a = {1, 2, 3, 4, 5}
for i in a:
    print(i)
```

    1
    2
    3
    4
    5
    


```python
# 딕셔너리 데이터
a = {1:'a', 2:'b', 3:'c'}
for i in a:
    print(f'key : {i}') 
    #key값만 출력된다
    
for i in a.values():
    print(f'values : {i}')
    
for i in a.items():
    print(f'(key, value) : {i}')
    
for i, j in a.items(): 
    #언패킹
    print(i, j)
```

    key : 1
    key : 2
    key : 3
    values : a
    values : b
    values : c
    (key, value) : (1, 'a')
    (key, value) : (2, 'b')
    (key, value) : (3, 'c')
    1 a
    2 b
    3 c
    


```python
# for문 응용
score = {'홍길동':80, '황길동':30, '김길동':25, '고길동':48, 
         '이길동':65, '최길동':100, '박길동':37, '조길동':55}

# 60점이 이상이면 '합격', 안넘으면 '불합격'
# 합격인 사람의 명단 출력

for a in score.values():
    print(a)
    if a >= 60:
        print("합격")
    elif a < 60:
        print("불합격")
```

    80
    합격
    30
    불합격
    25
    불합격
    48
    불합격
    65
    합격
    100
    합격
    37
    불합격
    55
    불합격
    


```python
# 심화
# 합격자 수 출력
# 전체 평균 출력

count = 0
sum = 0
for b, c in score.items():
    sum += c
    # print(b, c)
    if c >= 60:
        print("{0}님은 {1}점으로 합격입니다.".format(b, c))
        count += 1
    else:
        print("{0}님은 {1}점으로 불합격입니다.".format(b, c))
else:
    print("합격자수 : {0}명, 전체평균 : {1}점".format(count, sum/len(score)))
```

    홍길동님은 80점으로 합격입니다.
    황길동님은 30점으로 불합격입니다.
    김길동님은 25점으로 불합격입니다.
    고길동님은 48점으로 불합격입니다.
    이길동님은 65점으로 합격입니다.
    최길동님은 100점으로 합격입니다.
    박길동님은 37점으로 불합격입니다.
    조길동님은 55점으로 불합격입니다.
    합격자수 : 3명, 전체평균 : 55.0점
    


```python
# range 함수 - 숫자 리스트를 자동 생성
a = range(10)
print(a, type(a))

for i in range(10):
    print(i)

for i in range(5, 44):
    print(i)

score = [30, 70, 50, 90, 25]
for i in range(len(score)):
    # 인덱싱을 사용
    if score[i] >= 60:
        print(f"{score[i]}점은 합격입니다.")
```

    range(0, 10) <class 'range'>
    0
    1
    2
    3
    4
    5
    6
    7
    8
    9
    5
    6
    7
    8
    9
    10
    11
    12
    13
    14
    15
    16
    17
    18
    19
    20
    21
    22
    23
    24
    25
    26
    27
    28
    29
    30
    31
    32
    33
    34
    35
    36
    37
    38
    39
    40
    41
    42
    43
    70점은 합격입니다.
    90점은 합격입니다.
    


```python
# 다중for문
for i in range(10):
    for j in range(10):
        print(i, j)
```

    0 0
    0 1
    0 2
    0 3
    0 4
    0 5
    0 6
    0 7
    0 8
    0 9
    1 0
    1 1
    1 2
    1 3
    1 4
    1 5
    1 6
    1 7
    1 8
    1 9
    2 0
    2 1
    2 2
    2 3
    2 4
    2 5
    2 6
    2 7
    2 8
    2 9
    3 0
    3 1
    3 2
    3 3
    3 4
    3 5
    3 6
    3 7
    3 8
    3 9
    4 0
    4 1
    4 2
    4 3
    4 4
    4 5
    4 6
    4 7
    4 8
    4 9
    5 0
    5 1
    5 2
    5 3
    5 4
    5 5
    5 6
    5 7
    5 8
    5 9
    6 0
    6 1
    6 2
    6 3
    6 4
    6 5
    6 6
    6 7
    6 8
    6 9
    7 0
    7 1
    7 2
    7 3
    7 4
    7 5
    7 6
    7 7
    7 8
    7 9
    8 0
    8 1
    8 2
    8 3
    8 4
    8 5
    8 6
    8 7
    8 8
    8 9
    9 0
    9 1
    9 2
    9 3
    9 4
    9 5
    9 6
    9 7
    9 8
    9 9
    


```python
# 구구단을 외자
for a in range(2, 10):
    for b in range(2, 10):
        print(f"{a} * {b} =", a * b)
```

    2 * 2 = 4
    2 * 3 = 6
    2 * 4 = 8
    2 * 5 = 10
    2 * 6 = 12
    2 * 7 = 14
    2 * 8 = 16
    2 * 9 = 18
    3 * 2 = 6
    3 * 3 = 9
    3 * 4 = 12
    3 * 5 = 15
    3 * 6 = 18
    3 * 7 = 21
    3 * 8 = 24
    3 * 9 = 27
    4 * 2 = 8
    4 * 3 = 12
    4 * 4 = 16
    4 * 5 = 20
    4 * 6 = 24
    4 * 7 = 28
    4 * 8 = 32
    4 * 9 = 36
    5 * 2 = 10
    5 * 3 = 15
    5 * 4 = 20
    5 * 5 = 25
    5 * 6 = 30
    5 * 7 = 35
    5 * 8 = 40
    5 * 9 = 45
    6 * 2 = 12
    6 * 3 = 18
    6 * 4 = 24
    6 * 5 = 30
    6 * 6 = 36
    6 * 7 = 42
    6 * 8 = 48
    6 * 9 = 54
    7 * 2 = 14
    7 * 3 = 21
    7 * 4 = 28
    7 * 5 = 35
    7 * 6 = 42
    7 * 7 = 49
    7 * 8 = 56
    7 * 9 = 63
    8 * 2 = 16
    8 * 3 = 24
    8 * 4 = 32
    8 * 5 = 40
    8 * 6 = 48
    8 * 7 = 56
    8 * 8 = 64
    8 * 9 = 72
    9 * 2 = 18
    9 * 3 = 27
    9 * 4 = 36
    9 * 5 = 45
    9 * 6 = 54
    9 * 7 = 63
    9 * 8 = 72
    9 * 9 = 81
    


```python
# break - 중간에 있는 조건에 걸리면 그대로 스탑
for i in range(10):
    if i == 5:
        break
    print(i)
```

    0
    1
    2
    3
    4
    


```python
# continue - 중간에 있는 조건 하나 쏙 빼고 나머지 진행
for i in range(10):
    if i == 5:
        continue
    print(i)
```

    0
    1
    2
    3
    4
    6
    7
    8
    9
    


```python
# 짝수만 출력되게
for i in range(1, 11):
    if i % 2 == 1:
        continue
    print(i)
```

    2
    4
    6
    8
    10
    


```python
# 축약 내장리스트 - for문이 list 안에 들어간다
a = [i * 2 for i in range(1, 10)] # 연산도 가능하다 좀편하긴하네
print(a)

# 이런 문법이 있다는거만 알아놓자 잘 안쓰는거같다
```

    [2, 4, 6, 8, 10, 12, 14, 16, 18]
    


```python
#여기에 if문도 들어갈수 있다
a = [i for i in range(1, 10) if i % 2 == 0]
print(a)

# 보기에는 간결해 보일수 있으나 하는사람이 어렵다
```

    [2, 4, 6, 8]
    
