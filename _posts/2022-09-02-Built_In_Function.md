# 내장함수
- import 없이 사용할수 있는 함수들
```
print()
del()
type()
등
```


```python
# abs 절대값
a = abs(-2)
print(a)
print(abs(2))
print(abs(-2))
```

    2
    2
    2
    


```python
# all
# 반복가능한 자료형안에 있는 모든 요소들이 참이면 참 / 거짓이 하나라도 있으면 거짓
# 논리 연산자 중 and와 유사
a = [1, 2, 3, 4, 5]
print(all(a))
a = [1, True, "참", 0, 5] # 0은 False값
print(all(a))
```

    True
    False
    


```python
# any
# 반복가능한 자료형안에 있는 요소들이 하나라도 참이면 참 / 모두 거짓이면 거짓
a = [1, True, "참", 0, 5] #참이 4개 거짓 1개
print(any(a))
a = [0, False, []] #모두 거짓
print(any(a))
```

    True
    False
    


```python
# chr
# 유니코드값을 입력받아 그 코드에 해당하는 문자를 출력
print(chr(97))
print(chr(65))
print(chr(0x41))

# 아스키코드값 중 문자를 출력한다. 
# 아스키코드의 문자는 1바이트만 표현되는데 한글은 한글자에 2바이트다
# 그래서 나온게 유니코드
print(chr(0xBC31))
print(chr(0xAE30))
print(chr(0xD638))

# 유니코드 안에 아스키코드가 들어간다 아스키코드는 256개밖에 안됨
```

    a
    A
    A
    백
    기
    호
    


```python
# ord
# chr반대개념
# 문자를 입력받아 유니코드로 출력
# 유니코드 값으로 돌려줌
print(ord("가"))
```

    44032
    


```python
# dir
# 객체가 가지고있는 변수나 함수를 보여줌
print(dir([1, 2, 3])) #리스트에서 할수있는 뭐 카피 리무브 이런거 다나옴
print('='*100)
print(dir((1, 2, 3))) #튜플은 변하지않는거라 리스트보다 몇개 없음
```

    ['__add__', '__class__', '__class_getitem__', '__contains__', '__delattr__', '__delitem__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__gt__', '__hash__', '__iadd__', '__imul__', '__init__', '__init_subclass__', '__iter__', '__le__', '__len__', '__lt__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__reversed__', '__rmul__', '__setattr__', '__setitem__', '__sizeof__', '__str__', '__subclasshook__', 'append', 'clear', 'copy', 'count', 'extend', 'index', 'insert', 'pop', 'remove', 'reverse', 'sort']
    ====================================================================================================
    ['__add__', '__class__', '__class_getitem__', '__contains__', '__delattr__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__getnewargs__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__iter__', '__le__', '__len__', '__lt__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__rmul__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__', 'count', 'index']
    


```python
# divmod
# 두개의 숫자를 입력받아 몫과 나머지를 튜플로 출력
# 나누긴데 나누고나서 몫과 나머지를 튜플로 출력해줌
print(divmod(9, 4))

# (몫, 나머지) 로 튜플로 나옴
```

    (2, 1)
    


```python
# enumerate 열거하다
# mutable자료형의 인덱스와 값을 반환
# 순서가 있는 자료형(리스트, 튜플, 문자열)의 입력을 받아서 그 값과 인덱스값을 출력해준다
for i, v in enumerate(["a", "b", "c"]):
    print(i, v)
    
# 인덱스값 문자 이렇게 쭉 나열해준다 언패킹된채로
```

    0 a
    1 b
    2 c
    


```python
# eval
# 실행가능한 문자열을 입력받아서 실행 후 출력
# 문자열인데 안에 계산해서 나옴 신기하네 근데 잘안씀
print(eval('1 + 2'))
print(eval("divmod(3, 4)"))
```

    3
    (0, 3)
    


```python
# hex
# 16진수 변환
# 16진수 코드로 넘겨줌
print(hex(234))
```

    0xea
    


```python
# oct
# 8진수 변환
print(oct(234))
```

    0o352
    


```python
# id
# 객체의 고유 주소값(참조값 = 레퍼런스)을 반환
print(id(3))
```

    1926154643824
    


```python
# int, str, float
# 데이터타입 변환시키는거

# 정수로 변환
# int
print(int(3.14))
```

    3
    


```python
# 실수로 변환
# float
print(float(3))
```

    3.0
    


```python
# 문자로 변환
# str
a = str(3)
print(type(a))
```

    <class 'str'>
    


```python
# isinstance
# class의 객체인지 판별하는 함수
class Myclass:
    pass
a = Myclass()
b = 3
print(isinstance(a, Myclass)) # 이게 a라는 객체가 Myclass의 객체가 맞냐 물어보는거
print(isinstance(b, Myclass))
```

    True
    False
    


```python
# len
# 요소의 길이, 요소 전체 갯수
# 길이구하는거
print(len("가나다라마바사아자")) # 문자열은 문자 하나하나를 센다
print(len('hello world'))# 띄어쓰기도 1로 포함
print(len([1, 2, 3, 4, 5, 6, 7, 8]))
```

    9
    11
    8
    


```python
# 통계부분

# max 최댓값
a = [1, 4, 67, 38, 79, 5]
print(max(a))
```

    79
    


```python
# min 최솟값
a = [1, 4, 67, 38, 79, 5]
print(min(a))
```

    1
    


```python
# sum 합계
# 리스트나 튜플 가능
print(sum([1, 3, 4]))
```

    8
    


```python
# 평균 구하는게 없다
# 총합 / 갯수
a = [2, 3, 4, 5, 6]
print(sum(a) / len(a))

# 아니면 numpy를 쓰면 평균낼수있다
import numpy as np
print(np.mean(a)) # mean()이 평균내는 넘파이함수
```

    4.0
    4.0
    


```python
# round 반올림
# round(실수, 반올림할 소숫점 자릿수)
print(round(123.12345, 1))
print(round(123.12345, -1)) # 이렇게 마이너스로 하면 정수자릿수 까지 반올림 해버린다
print(round(123.12345, -2))
```

    123.1
    120.0
    100.0
    


```python
# sorted 정렬
a = [1, 5, 2, 3, 7, 8, 6, 4]
print(sorted(a))
a.sort() #이거는 반환값이 없다 기능은 똑같다
```

    [1, 2, 3, 4, 5, 6, 7, 8]
    


```python
# zip
# 동일한 개수로 이루어진 자료형을 묶어주는 역할
print(list(zip([1, 2, 3], [5, 6, 7], ['a', 'b', 'c'])))

# 튜플로 묶어서 리스트로 출력
print(list(zip("abc", "qwe"))) # 이거도 문자열이 동일한 개수로 이루어졌기때문에 가능
```

    [(1, 5, 'a'), (2, 6, 'b'), (3, 7, 'c')]
    [('a', 'q'), ('b', 'w'), ('c', 'e')]
    
