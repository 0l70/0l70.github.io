---
published: true
layout: post
title:  파이썬 6-1장
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


# **나 혼자만 파이썬 레벨업 6-1화**



> **Lv.6**

>> **이경민**


### **오류** - 송유정 특기



##### **구문 오류(syntax error)**

- 프로그램 실행 전에 발생하는 오류

##### **예외(exception)** 또는 **런타임 오류(runtime error)**

- 프로그램 실행 중에 발생하는 오류


### **구문 오류(syntax error)**

- 괄호의 개수, 들여쓰기 문제 등



```python
#프로그램 시작
print("# 프로그램이 시작되었습니다!")

# 구문 오류 발생 코드
print("# 예외를 강제로 발생시켜 볼게요!)
```

#### SyntaxError

##### 구문에 문제가 있어 프로그램이 실행조차 되지 않는 오류

##### 닫는 따옴표로 문자열을 닫지 않음


### **예외(exception)**



- 예외 또는 런타임 오류는 실행 중에 발생하는 오류를 의미



```python
#프로그램 시작
print("# 프로그램이 시작되었습니다!")

# 예외 발생 코드
list_a[1]
```

<pre>
# 프로그램이 시작되었습니다!
</pre>
### NameError

##### **예외** 또는 **런타임 오류**

- 실행 중에 발생하는 오류


### **기본 예외 처리**

##### **예외 처리(exception handling)**

- 조건문을 사용하는 방법

- try 구문을 사용하는 방법

##### 구문 오류는 프로그램이 실행조차 되지 않기 때문에 예외 처리 방법으로 처리할 수 없다. <br>문법 문제가 발생한 코드 수정해야 됨


### **예외가 발생할 수 있는 코드**



```python
number_input_a = int(input('정수 입력 > '))

print('원의 반지름 :', number_input_a)
print('원의 둘레 :', 2 * 3.14 *number_input_a)
print('원의 넓이 :', 3.14 * number_input_a * number_input_a)
```

### **조건문으로 예외 처리하기**



##### 정수를 입력하지 않았을 때 해결

##### isdigit( ) 함수를 사용



```python
user_input_a = input('정수 입력 >')

# 사용자 입력이 숫자로만 구성되어 있을 때
if user_input_a.isdigit():
    # 숫자로 변환합니다.
    number_input_a = int(user_input_a)
    # 출력합니다.

    print('원의 반지름 :', number_input_a)
    print('원의 둘레 :', 2 * 3.14 *number_input_a)
    print('원의 넓이 :', 3.14 * number_input_a * number_input_a)    
else:
    print('어이 잠깐, 정수를 입력하지 않았다 애송이')
```

<pre>
어이 잠깐, 정수를 입력하지 않았다 애송이
</pre>
### **try except 구문**



> try:<br>&#160;&#160;&#160;&#160;&#160;&#160;&#160;<u>예외가 발생할 가능성이 있는 코드</u><br>except:<br>&#160;&#160;&#160;&#160;&#160;&#160;&#160;<u>예외가 발생했을 때 실행할 코드</u>



```python
# try except 구문으로 예외 처리
try:
    # 숫자 변환
    number_input_a = int(input('정수 입력 >'))
    # 출력
    print('원의 반지름 :', number_input_a)
    print('원의 둘레 :', 2 * 3.14 *number_input_a)
    print('원의 넓이 :', 3.14 * number_input_a * number_input_a)
except:
    print('어이 잠깐, 뭔가 이상하군')
```

<pre>
어이 잠깐, 뭔가 이상하군
</pre>
### try except 구문과 pass 키워드 

##### **pass 키워드**

> try:<br>&#160;&#160;&#160;&#160;&#160;&#160;&#160;<u>예외가 발생할 가능성이 있는 코드</u><br>except:<br>&#160;&#160;&#160;&#160;&#160;&#160;&#160;<u>pass</u>



```python
# 변수 선언
list_input_a = ['52', '273', '32', '스파이', '103']

# 반복을 적용
list_number = []
for item in list_input_a:
    # 숫자로 변환해서 리스트에 추가
    try:
        float(item)
        list_number.append(item)
    except:
        pass
# 출력
print('{} 내부에 있는 숫자는'.format(list_input_a))
print('{}입니다.'.format(list_number))
```

<pre>
['52', '273', '32', '스파이', '103'] 내부에 있는 숫자는
['52', '273', '32', '103']입니다.
</pre>
### **try except else**



> try:<br>&#160;&#160;&#160;&#160;&#160;&#160;&#160;<u>예외가 발생할 가능성이 있는 코드</u><br>except:<br>&#160;&#160;&#160;&#160;&#160;&#160;&#160;<u>예외가 발생했을 때 실행할 코드</u><br>else:<br>&#160;&#160;&#160;&#160;&#160;&#160;&#160;<u>예외가 발생하지 않았을 때 실행할 코드</u>



```python
# try except else 구문으로 예외 처리
try:
    # 숫자 변환
    number_input_a = int(input('정수 입력 >'))
except:
    print('어이어이 정수 입력은 어디갔냐구')
else:
    # 출력
    print('원의 반지름 :', number_input_a)
    print('원의 둘레 :', 2 * 3.14 *number_input_a)
    print('원의 넓이 :', 3.14 * number_input_a * number_input_a)
```

<pre>
어이어이 정수 입력은 어디갔냐구
</pre>
### **finally 구문**

> try:<br>&#160;&#160;&#160;&#160;&#160;&#160;&#160;<u>예외가 발생할 가능성이 있는 코드</u><br>except:<br>&#160;&#160;&#160;&#160;&#160;&#160;&#160;<u>예외가 발생했을 때 실행할 코드</u><br>else:<br>&#160;&#160;&#160;&#160;&#160;&#160;&#160;<u>예외가 발생하지 않았을 때 실행할 코드</u><br>finally:<br>&#160;&#160;&#160;&#160;&#160;&#160;&#160;<u>무조건 실행할 코드</u>    



```python
# try except 구문으로 예외 처리
try:
    # 숫자 변환
    number_input_a = int(input('정수 입력 >'))
    # 출력
    print('원의 반지름 :', number_input_a)
    print('원의 둘레 :', 2 * 3.14 *number_input_a)
    print('원의 넓이 :', 3.14 * number_input_a * number_input_a)
except:
    print('어이어이 정수 입력은 어디갔냐구')
else:
    print('예외 발생')
finally:
    print('일단 프로그램이 어떻게든 끝났다')

```

<pre>
어이어이 정수 입력은 어디갔냐구
일단 프로그램이 어떻게든 끝났다
</pre>
### **try, except, finally 구문의 조합**



##### - try 구문은 혼자 쓸 수 없고, 반드시 except구문 또는 finally 구문과 함께 써야 한다.

##### - else 구문은 반드시 except 구문 뒤에 사용해야한다.



- try + except 구문 조합

- try + except + else 구문 조합

- try + except + finally 구문 조합

- try + except + else +finally 구문 조합

- try + finally 구문 조합


##### 파일이 제대로 닫혔는지 확인하기



```python
# try except 구문 사용
try:
    # 파일 열기
    file = open('info.txt', 'w')
    # 여러 가지 처리 수행
    # 파일 닫기
    file.close()
except:
    print('으아아 공습경보~ 공습경보~')
print('# 파일이 제대로 닫혔는지 확인')
print('file.closed :', file.closed)
```

<pre>
# 파일이 제대로 닫혔는지 확인
file.closed : True
</pre>
##### 예외 발생



```python
# try except 구문 사용
try:
    # 파일 열기
    file = open('info.txt', 'w')
    # 여러 가지 처리 수행
    공습.경보()
    # 파일 닫기
    file.close()
except:
    print('으아아 공습경보~ 공습경보~')
print('# 파일이 제대로 닫혔는지 확인')
print('file.closed :', file.closed)
```

<pre>
으아아 공습경보~ 공습경보~
# 파일이 제대로 닫혔는지 확인
file.closed : False
</pre>
##### finally 이용해서 파일 닫기



```python
# try except 구문 사용
try:
    # 파일 열기
    file = open('info.txt', 'w')
    # 여러 가지 처리 수행
    공습.경보()
except:
    print('으아아 공습경보~ 공습경보~')
finally:
    file.close()

print('# 파일이 제대로 닫혔는지 확인')
print('file.closed :', file.closed)
```

<pre>
으아아 공습경보~ 공습경보~
# 파일이 제대로 닫혔는지 확인
file.closed : True
</pre>
##### try except 구문이 끝난 후 파일 닫기



```python
# try except 구문 사용
try:
    # 파일 열기
    file = open('info.txt', 'w')
    # 여러 가지 처리 수행
    공습.경보()
except:
    print('으아아 공습경보~ 공습경보~')

file.close()
print('# 파일이 제대로 닫혔는지 확인')
print('file.closed :', file.closed)
```

<pre>
으아아 공습경보~ 공습경보~
# 파일이 제대로 닫혔는지 확인
file.closed : True
</pre>
##### try 구문 내부에서 return 키워드를 사용하는 경우

- finally 구문은 반복문 또는 함수 내부에 있을 때 위럭을 발휘휘~



```python
# test() 함수 선언
def test():
    print('test() 함수의 첫 줄쓰')
    try:
        print('try 구문이 실행됨')
        return
        print('try 구문의 return 키워드 뒤')
    except:
        print('except 구문 실행됨')
    else:
        print('else 구문이 실행됨')
    finally:
        print('finally 구문이 실행됨')
    print('test() 함수의 마지막 줄쓰')

test()
```

<pre>
test() 함수의 첫 줄쓰
try 구문이 실행됨
finally 구문이 실행됨
</pre>
##### finally 키워드 활용



```python
# 함수 선언
def write_text_file(filename, text):
    try:
        # 파일 열기
        file = open(filename, 'w')
        # 여러 가지 처리 수행
        return
        # 파일에 텍스트 입력
        file.write(text)
    except:
        print('오류 발생')
    finally:
        # 파일 닫기
        file.close()

# 함수 호출
write_text_file('test.txt', '안녕')
```

### <u>반복문과 함께 사용하는 경우</u>



##### finally 구문은 무조건 실행 - 반복문에서 break로 빠져나갈 때도 같다.



```python
print('프로그램 시작')

while True:    
    try:
        print('try 구문이 실행됨')
        break
        print('try 구문의 break 키워드 뒤')
    except:
        print('except 구문 실행됨')
    finally:
        print('finally 구문이 실행됨')
    print('while 반복문의 마지막 줄쓰')
print('프로그램 종료')
```

<pre>
프로그램 시작
try 구문이 실행됨
finally 구문이 실행됨
프로그램 종료
</pre>