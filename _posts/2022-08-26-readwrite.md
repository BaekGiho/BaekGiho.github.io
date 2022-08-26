# 파일 읽고 쓰기
- 파일객체 = open(파일명, 모드, 인코딩) 
- 모드랑, 인코딩은 없으면 안적어도 됨 대부분 파일 모드만 적음

### 파일객체 멤버함수
- write
- read
- readline
- readlines
- seek
- tell
- close

### 파일열기모드
- r : 읽기모드
- w : 쓰기모드
- a : 추가모드


```python
# c:/~ , d:/~로 경로지정 가능, 경로지정 안하면 지금 사용하는 파일이 있는 폴더로 감
# 파일 쓰기(write)
fp = open("test.txt",'w')

for i in range(1, 11):
    fp. write(f"{i} 입니다.\n")
    
fp.close()
```


```python
# 파일 읽기(read) - 파일포인터와 역할이 비슷비슷함
fp = open("test.txt",'r') #뒤에 'r'안적어도 디폴트가 r이라서 상관없음 그냥 볼려고 쓴거

rd = fp.read() #파일에 있는 데이터를 다 읽어오는거
print(rd)

fp.close()
```

    1 입니다.
    2 입니다.
    3 입니다.
    4 입니다.
    5 입니다.
    6 입니다.
    7 입니다.
    8 입니다.
    9 입니다.
    10 입니다.
    
    


```python
# 원하는 글자수만 읽어온다
# fp.read(숫자)
fp = open("test.txt",'r')

rd = fp.read(10) #int를 입력할수 있다 - 그 수만큼만 읽어온다
print(rd)

fp.close()
```

    1 입니다.
    2 입
    


```python
# 파일포인터 위치(tell) 
# 그니까 메모장의 경우 커서가 어디에 위치해있느냐 그런거같은데 파일에서 포인터가 어디에 위치해있냐
fp = open("test2.txt", "w")
print(fp.tell())

fp.write("godogdneoegidnekcodxk")
print(fp.tell())

fp.write("hello world")

fp.close()
```

    0
    21
    


```python
# 파일포인터 변경(seek) - 메모장의 경우 커서위치!
fp = open("test2.txt", "w")
print(fp.tell())

fp.write("sgfrerwtresdasdast") #파일포인터가 11위치에 있어야하는데
fp.seek(3) #seek을 통해서 3번위치로 옮김
print(fp.tell()) #확인하니까 3이라고 뜸

fp.write("helloWorld") 
# 뒤에 남은 글자가 오는게 아니고 파일포인터 위치부터 덮어쓴다!(기존에 rerwtret는 덮어써져 사라짐)

fp.close()
```

    0
    3
    


```python
# 파일읽기(readline) - 한줄씩 읽어오기
fp = open("test.txt", "r")

line = fp.readline() #요거 한번 실행하면 1줄, 2번실행하면 2줄, 3번실행하면 3줄 ~~~
print(line)

line = fp.readline()
print(line)

fp.close()
```

    1 입니다.
    
    2 입니다.
    
    


```python
# 여러줄 읽기
# for문으로 표현하면
fp = open("test.txt", "r")

for i in fp:
    print(i)
    
fp.close()
```

    1 입니다.
    
    2 입니다.
    
    3 입니다.
    
    4 입니다.
    
    5 입니다.
    
    6 입니다.
    
    7 입니다.
    
    8 입니다.
    
    9 입니다.
    
    10 입니다.
    
    


```python
# 파일읽기(readlines) - 이걸 이용해서 읽으면 list로 뽑아줌
fp = open("test.txt", "r")

rd = fp.readlines()
print(rd)

fp.close()

# 리스트로 출력! 근데 \n 같은 안봐도 될것들이 있다
# 그걸 없애보자
```

    ['1 입니다.\n', '2 입니다.\n', '3 입니다.\n', '4 입니다.\n', '5 입니다.\n', '6 입니다.\n', '7 입니다.\n', '8 입니다.\n', '9 입니다.\n', '10 입니다.\n']
    


```python
# \n 같은거 없애기
fp = open("test.txt", "r")
rd = fp.readlines()
for i in rd:
    i = i.strip()
    print(i)
fp.close()
```

    1 입니다.
    2 입니다.
    3 입니다.
    4 입니다.
    5 입니다.
    6 입니다.
    7 입니다.
    8 입니다.
    9 입니다.
    10 입니다.
    


```python
# 쓰기모드를 여러번 하면 계속 처음부터 덮어쓰기때문에
# 계속 파일포인터를 옮겨줄거 아니면
# 추가모드 사용하자
# 추가모드(a)
fp = open("test.txt", "a")

for i in range(11, 21):
    fp. write(f"{i} 입니다.\n")
    
fp.close()

# 여기서 "w"로 쓰기모드 해버리면 기존에 있던거 다 사라짐 그래서 "a"꼭 해줘야함
```


```python
# 함수로 만들어서 사용
def fileWrite(file, args, mode = "w"):
    fp = open(f"{file}.txt", mode)
    for i in args:
        fp.write(i)
    fp.close()

fileWrite("test1", "안되는구만", mode='a')

# 함수를 만들때 입력값 변수를 좀 알기 쉽게 만들어야 다른사람들과 공유할때 좋다
```


```python
# 원하는 줄수 출력하는 함수를 만들어보자
def fileReadline(filename, lines):
    fp = open(f"{filename}.txt", "r")
    a = 1
    while a <= lines:
        line = fp.readline()
        a += 1
        print(line)
        
fileReadline('test', 3)
```

    1 입니다.
    
    2 입니다.
    
    3 입니다.
    
    
