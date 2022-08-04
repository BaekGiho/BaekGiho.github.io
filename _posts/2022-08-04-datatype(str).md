# 문자열(string)(str) 
- 문자, 단어 등으로 구성된 문자들의 집합)


```python
a="hello world"
b='hello world'
# 위 2가지가 가장 일반적인 문자열 표현방법

c="""hello world"""
d='''hello world'''
print(a)
print(b)
print(c)
print(d)
# 위 4가지는 다 똑같은 문자열이 출력되지만 사용  용도가 다르다
# 예를들면 python's 같은거 쓸때는 ""로 묶어주면 표현가능하다
e="python's"
print(e)
f='hello "python"'
print(f)
```

    hello world
    hello world
    hello world
    hello world
    python's
    hello "python"
    


```python
# \(백슬래쉬)-이스케이프 코드
g='python\'s'
print(g)
h="hello \"python\""
print(h)

# \n - 아래줄로 줄바꿈
a="hello \nworld"
print(a)

# \t - 수평으로 탭
a="hello \tworld"
print(a)
```

    python's
    hello "python"
    hello 
    world
    hello 	world
    


```python
# """""""는 그안에 뭐 안해도 그냥 그대로 출력해줌
# ''''''도 동일 여러줄문자열(멀티라인)쓸때 자주사용
c="""
hello

world
"""
print(c)
print(type(a))
```

    
    hello
    
    world
    
    <class 'str'>
    


```python
# 문자열 연산
a="hello"
b="world"
c=a+b
# 문자열 끼리 +연산자는 두개 붙여서 출력(뒤에 숫자오면 오류남 d=a+3안됨)
# 위 예시에서 3을 문자열로 바꿔주면 됨(d=a+str(3))
print(c)
c=a*3

# 문자열끼리 *연산자 뒤에 숫자는 그 숫자만큼 복사 붙여넣기
print(c)
d=a+"3"
d=a+str(3)
print(d)
a="10"
d=int(a)+3
print(d)
# 앞에 str(),int(),float() 등을 붙여서 같은 데이터로 맞춰준 후 연산작업!
```

    helloworld
    hellohellohello
    hello3
    13
    


```python
# 문자열 길이
print(len(b))
# b는 hello 5글자라서 5로 출력됨 len은 lenth의 줄임말
```

    5
    


```python
# 인덱싱([]에 숫자를 넣어 해당 부분을 찾아 출력)
a="동해물과 백두산이 마르고 닳도록"
print(a[3])

# 파이썬의 숫자는 0부터 시작해서 3이면 4번째 글자인 '과'가 출력
print(a[10])
print(a[-1])

# 인덱스 번호가 마이너스면 뒤에서부터 출력 - 뒤에서부터는 0부터 시작안함
print(a[-3])
print(a[1]+a[2]+a[3])
# 한글자씩만 되서 이렇게 더해야함 그게 불편해서 슬라이싱 쓴다
```

    과
    마
    록
    닳
    해물과
    


```python
# 슬라이싱([시작:끝-1:증가치] - 문자열 나누기)
print(a[0:6])
print(a[5:8])
print(a[:6])

# 시작값을 안적으면 디폴트값으로 0처리
print(a[-3:])

# 마찬가지로 끝값을 안적으면 끝까지!
print(a[:])

# 둘다 안적으면 전부 다인데 굳이 할 필요 없다

# 슬라이싱 예제
b="20220516windy"
date=b[:8]
weather=b[8:]
print(date)
print(weather)
month=b[4:6]
print(month)

# 증가치를 적을경우 슬라이싱
print(a[::2])
# 0,2,4 순서대로 출력
```

    동해물과 백
    백두산
    동해물과 백
    닳도록
    동해물과 백두산이 마르고 닳도록
    20220516
    windy
    05
    동물 두이마고닳록
    


```python
# 문자열 바꾸기(관련 함수로 해야 함)
# immutable 특징 - 자료형 - 안에 내용을 바꿀수 없다
a="동해물과 백두산이 마르고 닳도록"
# 에러 # a[0]="서" <- 이런거 안됨 에러남
print(a.replace("동","서"))
```

    서해물과 백두산이 마르고 닳도록
    


```python
# 문자열 포매팅(% 붙여서 숫자만 바꾸고 하는거)

# 문자열 포매팅의 첫번째 방법
# %d는 정수
# %s는 문자열
# %f는 실수
# 근데 $s쓰면 거의 다됨 그냥 그게 다 문자열로 바꿔주기때문
number=55
a="현재 %s는 %d도 입니다."%("습도", number)
b="승률 %d%% 입니다."%39
# %를 문자그대로 쓸라면 %%써줘야 나옴 안그럼 에러뜸
print(a)
print(b)
a="현재 %10s는 %d도 입니다."%("습도", number)
print(a)
a="현재 %-10s는 %d도 입니다."%("습도", number)
print(a)
# %와s사이에 숫자넣으면 그만큼 공백 만들고 그 안에 뒤에 글자 넣음

a="%f"%3.1415
print(a)
a="%7.3f"%3.1415
print(a)
# 실수형에서는 소숫점 앞자리는 공백, 뒷자리는 표현할 자리수!


# 문자열 포매팅 두번째 방법
a="현재 {0}는 {1}도 입니다.".format("온도", 20)
print(a)
b="{0}는 {number}살 입니다.".format("나", number=29)
print(b)
# 정렬방법은 알아서 찾자(위키독스 점프투파이썬 02-2에 있음)


# 더 편한 문자열 포매팅 세번째 방법(파이썬 3.6인가 부터 나온 신상 포매팅 기능)
number=23
a=f"현재 온도는 {number*2}도 입니다."
# 맨앞에 f만 적어주자(연산도 가능)
print(a)
```

    현재 습도는 55도 입니다.
    승률 39% 입니다.
    현재         습도는 55도 입니다.
    현재 습도        는 55도 입니다.
    3.141500
      3.142
    현재 온도는 20도 입니다.
    나는 29살 입니다.
    현재 온도는 46도 입니다.
    


```python
# 문자열 관련 함수들
# 문자 개수 세기(count)-len이랑 다른게 전체 글자수 세는게 아니고 해당 알파벳이 몇갠지 찾는거
a="hello"
print(a.count("l"))
```

    2
    


```python
# 문자 위치 알려주기(find)
a="python"
print(a.find("h"))
# 같은 알파벳이 여러개 있으면 앞에서부터 처음 찾은거 기준으로 출력
# 해당 알파벳이 없으며 -1 출력
print(a.find("w"))
```

    3
    -1
    


```python
# 문자 위치 알려주기 두번째(index)
print(a.index("h"))
# 인덱스에서 해당 알파벳이 없으면 에러난다! <-이게 find와의 차이점
# print(a.index("w")) <- 에러!
# find 와 index가 따로 있는 이유가 있는데 그건 나중에
```

    3
    


```python
# 문자열 삽입(join)
a="hello"
a="_".join(a)
print(a)
```

    h_e_l_l_o
    


```python
# 소문자를 대문자로(upper)
a="hello"
print(a.upper())

# 대문자를 소문자로(lower)
b="WORLD"
print(b.lower())
```

    HELLO
    world
    


```python
# 공백 지우기(strip)
a="     python    "
print(len(a))
a=a.lstrip() # 왼쪽 공백 지우기
a=a.rstrip() # 오른쪽 공백 지우기
print(a)
print(len(a))
a="     sdfasfsf     "
a=a.strip() # 양쪽 공백 다 지우기
print(a)
```

    15
    python
    6
    sdfasfsf
    


```python
# 문자열 바꾸기(replace)
a="python"
print(a.replace("p","f"))
```

    fython
    


```python
# 문자열 나누기(split)
a= "just do it"
b= a.split()
# 괄호 안에 들어가는게 뭘 기준으로 나눌지 정하는거 안적으면 공백스페이스바 기준
print(b,type(b))
# 대괄호 안에 [1,2,3,4]이거는 list타입
```

    ['just', 'do', 'it'] <class 'list'>
    
