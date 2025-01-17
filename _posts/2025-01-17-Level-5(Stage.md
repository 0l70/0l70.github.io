---
published: true
layout: post
title:  파이썬 5-1장
date:   2025-01-17
categories: jekyll update
usemathjax: true
---

<head>
  <style>
    table.dataframe {
      white-space: normal;
      width: 100%;
      height: 240px;
      display: block;
      overflow: auto;
      font-family: Arial, sans-serif;
      font-size: 0.9rem;
      line-height: 20px;
      text-align: center;
      border: 0px !important;
    }

    table.dataframe th {
      text-align: center;
      font-weight: bold;
      padding: 8px;
    }

    table.dataframe td {
      text-align: center;
      padding: 8px;
    }

    table.dataframe tr:hover {
      background: #b8d1f3; 
    }

    .output_prompt {
      overflow: auto;
      font-size: 0.9rem;
      line-height: 1.45;
      border-radius: 0.3rem;
      -webkit-overflow-scrolling: touch;
      padding: 0.8rem;
      margin-top: 0;
      margin-bottom: 15px;
      font: 1rem Consolas, "Liberation Mono", Menlo, Courier, monospace;
      color: $code-text-color;
      border: solid 1px $border-color;
      border-radius: 0.3rem;
      word-break: normal;
      white-space: pre;
    }

  .dataframe tbody tr th:only-of-type {
      vertical-align: middle;
  }

  .dataframe tbody tr th {
      vertical-align: top;
  }

  .dataframe thead th {
      text-align: center !important;
      padding: 8px;
  }

  .page__content p {
      margin: 0 0 0px !important;
  }

  .page__content p > strong {
    font-size: 0.8rem !important;
  }

  </style>
</head>


# **나 혼자만 파이썬 레벨업 5-1화**



> **Lv.5**

>> **이경민**


### **함수 만들기**





##### **함수 호출** : 함수를 사용하는 것



##### **매개변수** : 함수 호출할 때 괄호 내부에 넣는 여러 가지 자료



##### **리턴값** : 마지막으로 함수를 호출해서 최종적으로 나오는 결과


### 함수 : 코드의 집합



##### 함수의 기본 형태

> def 함수 이름():<br>&#160;&#160;&#160;&#160;&#160;&#160;&#160;문장



```python
# 기본 함수
def print_3_times():
    print('hello')
    print('hello')
    print('hello')

print_3_times()
```

<pre>
hello
hello
hello
</pre>
### **매개변수**



- 식별자를 입력해서 만듦



> def 함수 이름(매개변수, 매개변수, ...):<br>&#160;&#160;&#160;&#160;&#160;&#160;&#160;문장



```python
# 매개변수의 기본
def print_n_times(value, n):
    for i in range(n):
        print(value)

print_n_times('Hello',5)
```

<pre>
Hello
Hello
Hello
Hello
Hello
</pre>
### **가변 매개변수**



- 매개변수 개수가 변할수 있음



> def 함수 이름(매개변수, 매개변수, ... , *가변 매개변수):<br>&#160;&#160;&#160;&#160;&#160;&#160;&#160;문장



##### 가변 매개변수 제약

- 가변 매개변수 뒤에는 일반 매개변수가 올 수 없다

- 가변 매개변수는 하나만 사용 가능



```python
def print_n_times(n, *values):
    # n번 반복
    for i in range(n):
        # values는 리스트처럼 활용
        for value in values:
            print(value)
        # 줄바꿈
        print()

# 함수를 호출
print_n_times(3, 'I','am','신뢰에요')
```

<pre>
I
am
신뢰에요

I
am
신뢰에요

I
am
신뢰에요

</pre>
### **기본 매개변수**



> print(value, ... , sep = ' ', end = '\n', file = sys.stdout, flush = False)<br>



> print(가변 매개변수, 매개변수 = 값, 매개변수 = 값, 매개변수 = 값)



##### 여기서 value는 가변 매개변수



##### '매개변수 = 값'은 기본 매개변수



- 기본 매개변수 뒤에는 일반 매개변수가 올 수 없다.



```python
def print_n_times(value, n = 2):
    # n번 반복
    for i in range(n):
        print(value)

# 함수 호출
print_n_times("WASSUP")
```

<pre>
WASSUP
WASSUP
</pre>
### **키워드 매개변수**



### <u>기본 매개변수가 가변 매개변수보다 앞에 올 때</u>

#### 오류남




### <u>가변 매개변수가 기본 매개변수보다 앞에 올 때</u>



#### 예상

- ['안녕하세요','올리버썜입니다','우와~']을 3번 출력



- ['안녕하세요','올리버썜입니다','우와~',3]을 두 번 출력



```python
def print_n_times(*values, n = 2):
    # n번 반복
    for i in range(n):
        # values는 리스트처럼 활용
        for value in values:
            print(value)
        # 줄바꿈
        print()

# 함수 호출
print_n_times('안녕하세요','올리버썜입니다','우와~',3)
```

<pre>
안녕하세요
올리버썜입니다
우와~
3

안녕하세요
올리버썜입니다
우와~
3

</pre>
### ['안녕하세요','올리버썜입니다','우와~',3]을 두 번 출력함



#### 두 가지를 함께 사용할 수 있는 방법 - 키워드 매개변수



```python
def print_n_times(*values, n = 3):
    # n번 반복
    for i in range(n):
        # values는 리스트처럼 활용
        for value in values:
            print(value)
        # 줄바꿈
        print()

i = input()
# 함수 호출
print(print_n_times('안녕하세요','올리버쌤입니다','우와~', i, n = 3))
```

<pre>
안녕하세요
올리버쌤입니다
우와~
유정이

안녕하세요
올리버쌤입니다
우와~
유정이

안녕하세요
올리버쌤입니다
우와~
유정이

None
</pre>
#### 기본 매개변수 중에서 필요한 값만 입력하기



##### 키워드 매개변수는 기본 매개변수들로 구성된 함수에서도 많이 쓰임



```python
def test(a, b=10, c=100):
    print(a+b+c)

# 1) 기본 형태
test(10, 20, 30)
# 2) 키워드 매개변수로 모든 매개변수를 지정한 형태
test(a=10, b=100, c=200)
# 3) 키워드 매개변수로 모든 매개변수를 마구잡이로 지정한 형태
test(c=10, a=100, b=200)
# 4) 키워드 매개변수로 일부 매개변수만 지정한 형태
test(10, c=200)
```

<pre>
60
310
310
220
</pre>
### **리턴(return)**



##### 함수의 결과값



```python
# input() 함수의 리턴값을 변수에 저장
value = input('> ')

#출력
print(value)
```

<pre>
ㅋ
</pre>
#### **자료 없이 리턴**



##### <u>return 키워드 사용</u>



- 함수를 실행했던 위치로 돌아가라는 뜻 (함수가 끝나는 위치를 의미)



```python
# 함수 정의
def return_test():
    print('사각편달 : 2800')
    return
    print('사각편달 : 3200')

# 함수 호출
return_test()
```

<pre>
사각편달 : 2800
</pre>
### **자료와 함께 리턴하기**



##### <u>리턴 뒤에 자료를 입력하면 자료를 가지고 리턴</u>



```python
# 함수 정의
def return_test():
    return 100

# 함수 호출
value = return_test()
print(value)
```

<pre>
100
</pre>
### **아무것도 리턴하지 않기**



##### None 출력 ('없다'라는 뜻)



```python
def return_test():
    return

value = return_test()
print(value)
```

<pre>
None
</pre>
### **기본적인 함수의 활용**



> def 함수(매개변수):<br>&#160;&#160;&#160;&#160;&#160;&#160;&#160;변수 = 초깃값<br>&#160;&#160;&#160;&#160;&#160;&#160;&#160;# 여러 가지 처리<br>&#160;&#160;&#160;&#160;&#160;&#160;&#160;# 여러 가지 처리<br>&#160;&#160;&#160;&#160;&#160;&#160;&#160;# 여러 가지 처리<br>&#160;&#160;&#160;&#160;&#160;&#160;&#160;return 변수



```python
# 범위 내부 정수 모두 더하기
def sum_all(start, end):
    output = 0
    for i in range(start, end + 1):
        output += i
    return output

print('0 to 100 :', sum_all(0, 100))
print('0 to 1000 :', sum_all(0, 1000))
print('50 to 100 :', sum_all(50, 100))
print('500 to 1000 :', sum_all(500, 1000))
```

<pre>
0 to 100 : 5050
0 to 1000 : 500500
50 to 100 : 3825
500 to 1000 : 375750
</pre>

```python
# 기본 매개변수와 키워드 매개변수를 활용해 범위의 정수를 더하는 함수
def sum_all(start = 0, end = 0, step = 1):
    output = 0
    for i in range(start, end + 1, step):
        output += i

    return output

print('A.', sum_all(0, 100, 10))
print('B.', sum_all(end = 100))
print('C.', sum_all(end = 100, step = 2))
```

<pre>
A. 550
B. 5050
C. 2550
</pre>