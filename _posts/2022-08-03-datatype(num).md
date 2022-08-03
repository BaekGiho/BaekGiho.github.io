# 숫자형(number) - 숫자형태로 이루어진 자료형
- 정수, 실수, 2진수, 8진수, 16진수
- 연산자
- 복소수


```python
# 정수(int)
a = 10
b = -10
c = 0
print(type(a))

# type 파이썬 내장함수 데이터 타입 알려주는거
print(type(c))
```

    <class 'int'>
    <class 'int'>
    


```python
# 실수(float)
d = 3.141592
print(type(d))
```

    <class 'float'>
    


```python
# 2진수(0b를 붙여서 2진수임을 표현)
e = 0b01100011
print(e)
print(type(e))
```

    99
    <class 'int'>
    


```python
# 8진수(0o를 붙여서 8진수임을 표현)
f = 0o177
print(f, type(f))
```

    127 <class 'int'>
    


```python
# 16진수(0x~~~)
g = 0x8ff
print(g, type(g))
```

    2303 <class 'int'>
    


```python
# 연산자
a = 9
b = 4
print(a+b)
print(a-b)
print(a*b)
print(a/b)
print(a//b)
# //는 몫만 나옴 소수점 자르고

print(a%b)
# %는 나머지만 알려줌

print(a**b)
# a의 b승 **

```

    13
    5
    36
    2.25
    2
    1
    6561
    


```python
# 복소수(complex)
a = 3 + 4j
print(a)

# 튜플처럼 출력되는데?
print(type(a))

# 알고보면 컴플렉스 타입이다!

print(a.imag) #허수부
print(a.real) #실수부
print(a.conjugate()) #켤레복소수
```

    (3+4j)
    <class 'complex'>
    4.0
    3.0
    (3-4j)
    


```python
b = complex(3, -4) #요로케도 복소수 만들 수 있다 함수 이용해서
print(b)
```

    (3-4j)
    
