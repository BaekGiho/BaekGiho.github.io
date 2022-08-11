# 불 자료형(boolean)
- 참(True)과 거짓(False) ->영어로 쓸때 첫글자는 무조건 대문자 T,F


```python
a = True  # 문자형 같아보이지만 문자형이 아닌 불형의 값, 하나의 값
print(a)
print(type(a))
```

    True
    <class 'bool'>
    


```python
# 간단한 연산자
print(1 == 2) # == 앞뒤가 같냐 물어보는거
print(1 < 2) # < > 앞뒤 비교 물어보는거
```

    False
    True
    


```python
# 자료형의 참과 거짓(bool)
a = "python" #참
b = "" #거짓
c = [1, 2, 3, 4] #참
d = [] #거짓
e = () #거짓
f = {} #거짓
g = 1 #참
h = 0 #거짓
i = None #거짓

print(bool(a))
print(bool(b))
print(bool(c))
print(bool(d))
print(bool(e))
print(bool(f))
print(bool(g))
print(bool(h))
print(bool(i))
# bool함수는 참, 거짓 체크용이므로 다른 연산이나 추가,수정,제거 등의 작업은 안된다
```

    True
    False
    True
    False
    False
    False
    True
    False
    False
    
