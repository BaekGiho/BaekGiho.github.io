# 시퀀스 데이터타입
- 리스트, 튜플, 딕셔너리, 세트 등(문자열은 시퀀스데이터타입 아님)


- 순서있는 데이터타입(순서가 있기때문에 인덱싱, 슬라이싱 가능)
    - (문자열), 리스트, 튜플


- 순서없는 데이터타입(순서가 없기때문에 인덱싱, 슬라이싱 불가능)
    - 딕셔너리, 세트


- 변경가능(mutable) 데이터타입
    - 리스트, 딕셔너리, 세트


- 변경불가능(immutable) 데이터타입
    - (문자열), 튜플


```python
# 집합 또는 세트(set)
# 집합자료형
# 중복없는 데이터를 저장
# 순서없고 변경 가능
a = set()
b = {1, 2, 3, 4}
c = set([1, 2, 3])
d = set("hello")
print(a)
print(b)
print(c)
print(d)
print(type(b))
# 세트도 중괄호{}인데 안에 콜론:이 있으면 딕셔너리 없으면 세트
# 순서가 없고 중복이 안되서 무작위+ 중복되면 하나만 저장(d)
# 세트는 중복이 안된다는 특징을 이용해서 중복데이터를 없앨때 사용하기도 한다
# 순서가 없어서 인덱싱 슬라이싱 안되는데 세트를 리스트나 튜플로 변환해서 인덱싱 슬라이싱 하는 방법이 있다
```

    set()
    {1, 2, 3, 4}
    {1, 2, 3}
    {'o', 'e', 'l', 'h'}
    <class 'set'>
    


```python
# 세트를 리스트나 튜플로 변환
s = {1, 2, 3, 4}
l = list(s)
print(l)
t = tuple(s)
print(t)
# 변환 하고나서는 슬라이싱 인덱싱 가능
```

    [1, 2, 3, 4]
    (1, 2, 3, 4)
    


```python
# 집합자료형
a = set([1, 2, 3, 4, 5, 6])
b = set([4, 5, 6, 7, 8, 9])

# 교집합
print(a & b)
print(a.intersection(b)) # 교집합 내장 함수 어떤걸 써도 똑같으니 &쓰자 그냥

# 합집합
print(a | b) # 중복은 당연히 안나온다 set로 출력되니까
print(a.union(b)) # 내장함수 상동

# 차집합
print(a - b) # a에서 교집합 빼기
print(a.difference(b)) # 내장함수 상동

# 대칭차집합
print(a ^ b) # 합집합에서 교집합 빼기
print(a.symmetric_difference(b)) # 내장함수 상동
```

    {4, 5, 6}
    {4, 5, 6}
    {1, 2, 3, 4, 5, 6, 7, 8, 9}
    {1, 2, 3, 4, 5, 6, 7, 8, 9}
    {1, 2, 3}
    {1, 2, 3}
    {1, 2, 3, 7, 8, 9}
    {1, 2, 3, 7, 8, 9}
    


```python
# 세트 관련 함수
# 값 1개 추가하기(add)
a = set([1, 2, 3, 4, 5, 6])
a.add(10)
print(a)
# 가장 뒤에 하나씩 추가되는거

# 값 여러 개 추가하기(update)
a.update([22, 33, 44])
print(a)
# 순서가 없으니 무작위로 막 들어감 순서없이

# 특정 값 제거하기(remove)
a.remove(4)
print(a)
```

    {1, 2, 3, 4, 5, 6, 10}
    {1, 2, 3, 4, 5, 6, 33, 10, 44, 22}
    {1, 2, 3, 5, 6, 33, 10, 44, 22}
    


```python
# 리스트나 튜플을 세트로 변환
a = [1, 2, 3, 4, 5, 3, 4, 6, 7]
b = set(a)
print(b)
a = (1, 2, 3, 4, 5, 3, 4, 6, 7, 8)
b = set(a)
print(b)

# 앞에 데이터를 살리고 뒤에거를 제거하는 식으로 중복치를 제거한다
```

    {1, 2, 3, 4, 5, 6, 7}
    {1, 2, 3, 4, 5, 6, 7, 8}
    