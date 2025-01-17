---
published: true
layout: post
title:  파이썬 7-1장
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


# **나 혼자만 파이썬 레벨업 7-1화**



> **Lv.7**

>> **이경민**


## **모듈(module)**



##### 여러 변수와 함수를 가지고 있는 집합체



##### **표준 모듈**

- 파이썬에 기본적으로 내장되어 있는 모듈

##### **외부 모듈**

- 다른 사람들이 만들어서 공개한 모듈


### 


### **import 구문**

##### 모듈을 가져올 때 사용

> import 모듈 이름


### **모듈 사용의 기본 : math 모듈**

##### 수학과 관련된 기능

> import math



```python
import math
print(math.sin(1))
print(math.cos(1))
print(math.tan(1))
print(math.floor(2.5))  # 내림
print(math.ceil(2.5))   # 올림
```

<pre>
0.8414709848078965
0.5403023058681398
1.557407724654902
2
3
</pre>
### <u>모듈 순서</u>



변수 또는 함수|설명|

:---:|:---:

sin(x)|사인값을 구함

cos(x)|코사인값을 구함

tan(x)|탄젠트값을 구함

log(x[,base])|로그값을 구함

ceil(x)|올림

floor(x)|내림



##### round()

- 정수가 짝수일 때 소수점이 5면 내리고, 홀수면 소수점이 5면 올림;





```python
print(round(1.5))
print(round(2.5))
print(round(3.5))
print(round(4.5))
```

<pre>
2
2
4
4
</pre>
### **from 구문**

##### 이거하면 매번 앞에 모듈 이름 안붙여도 됨

> from 모듈 이름 import 가져오고 싶은 변수 또는 함수



```python
from math import sin, cos, tan, floor, ceil
print(sin(1))
print(cos(1))
print(tan(1))
print(floor(2.5))
print(ceil(2.5))
```

<pre>
0.8414709848078965
0.5403023058681398
1.557407724654902
2
3
</pre>
### 모두 가져오기



> from math import *



##### 모든 것을 가져오면 식별자 이름에서 충돌이 발생될 수 있다. from 구문을 사용할 때는 최대한 필요한 것들만 가져와서 사용하는 것이 좋다.





### **as 구문**

##### 모듈을 가져올 때 이름 충돌이 발생하는 경우가 있을 수 있다. 모듈의 이름이 길어서 짧게 줄여 쓰고 싶은 경우

> import 모듈 as 사용하고 싶은 식별자



```python
import math as m
print(m.sin(1))
print(m.cos(1))
print(m.tan(1))
print(m.floor(2.5))
print(m.ceil(2.5))
```

<pre>
0.8414709848078965
0.5403023058681398
1.557407724654902
2
3
</pre>
### **random 모듈**

##### 랜덤한 값을 생성할 때 사용

> import random



```python
import random
print('# random 모듈')

# random(): 0.0 <= x < 1.0 사이의 float를 리턴한다.
print('-random() :', random.random())

# uniform(min, max) : 지정한 범위 사이의 float를 리턴한다.
print('- uniform(10, 20) :', random.uniform(10, 20))

# randrange() : 지정한 범위의 int를 리턴한다.
# - randrange(max) : 0부터 max 사이의 값을 리턴한다.
# - randrange(min, max) : min부터 max 사이의 값을 리턴한다.
print('- randrange(10) :', random.randrange(10))

# choice(list) : 리스트 내부에 있는 요소를 랜덤하게 선택
print('- choice([1, 2, 3, 4, 5]) :', random.choice([1, 2, 3, 4, 5]))

# shuffle(list) : 리스트의 요소들을 랜덤하게 섞기
print('- shuffle([1, 2, 3, 4, 5]) :', random.shuffle([1, 2, 3, 4, 5]))

# sample(list, k=<숫자>) : 리스트의 요소 중에 k개 뽑기
print('- sample([1, 2, 3, 4, 5], k=2) :', random.sample([1, 2, 3, 4, 5], k=2))
```

<pre>
# random 모듈
-random() : 0.27772755404279326
- uniform(10, 20) : 15.795070244240655
- randrange(10) : 4
- choice([1, 2, 3, 4, 5]) : 1
- shuffle([1, 2, 3, 4, 5]) : None
- sample([1, 2, 3, 4, 5], k=2) : [1, 4]
</pre>
### 모듈 파일 이름 작성 시 주의 사항

##### 모듈과 같은 이름으로 파일을 저장하고 실행하면 **TypeError**가 발생

- ex) : random.py


### **sys 모듈** - WINDOW OS에서 사용

##### 시스템과 관련된 정보를 가지고 있는 모듈<br>명령 매개변수를 많이 받을 때 사용

##### strftime() 함수 사용 - 시간을 형식에 맞춰 출력 가능



```python
# 모듈을 읽어드리기
import sys

print(sys.argv)
print('---')

# 컴퓨터 환경과 관련된 정보를 출력
print('getwindowsversion :()', sys.get)
# print('---')
# print('copyright :', sys.copyright)
# print('---')
# print('version :', sys.version)

# # 프로그램 강제 종료
# sys.exit()
```

<pre>
['/Users/leekyungmin/Library/Python/3.11/lib/python/site-packages/ipykernel_launcher.py', '--ip=127.0.0.1', '--stdin=9018', '--control=9016', '--hb=9015', '--Session.signature_scheme="hmac-sha256"', '--Session.key=b"3f0610eb-c494-47c5-938d-e0884a4510a7"', '--shell=9017', '--transport="tcp"', '--iopub=9019', '--f=/Users/leekyungmin/Library/Jupyter/runtime/kernel-v2-27192UrKTfdUH3bE.json']
---
</pre>
### **datetime 모듈**



##### date(날짜), time(날짜) 관련 모듈



```python
# 모듈을 읽어들이기
import datetime

# 현재 시각을 구하고 출력하기
print('# 현재 시각 출력')
now = datetime.datetime.now()
print(now.year, '년')
print(now.month, '월')
print(now.day, '일')
print(now.hour, '시')
print(now.minute, '분')
print(now.second, '초')
print()

# 시간 출력 방법
print('# 시간을 포멧에 맞춰 출력하기')
output_a = now.strftime('%Y.%m.%d %H:%M:%S')
output_b = '{}년 {}월 {}일 {}시 {}분 {}초'.format(now.year,\
    now.month,\
    now.day,\
    now.hour,\
    now.minute,\
    now.second)
output_c = now.strftime('%Y{}.%m{}.%d{} %H{}:%M{}:%S{}').format(*'년월일시분초')
print(output_a)
print(output_b)
print(output_c)
print()
```

<pre>
# 현재 시각 출력
2023 년
11 월
9 일
15 시
15 분
7 초

# 시간을 포멧에 맞춰 출력하기
2023.11.09 15:15:07
2023년 11월 9일 15시 15분 7초
2023년.11월.09일 15시:15분:07초

</pre>
#### 시간 처리하기



##### timedelta() : 특정한 시간 이전 / 이후 구하기

##### replace() : 값 교체



```python
import datetime
now = datetime.datetime.now()

# 특정 시간 이후의 시간 구하기
print('# datetime.timedelta로 시간 더하기')
after = now + datetime.timedelta(\
    weeks = 1,\
    days = 1,\
    hours = 1,\
    minutes = 1,\
    seconds = 1)
print(after.strftime('%Y{}.%m{}.%d{} %H{}:%M{}:%S{}').format(*'년월일시분초'))
print()

# 특정 시간 교체하기
print('# now.replace()로 1년 더하기')
output = now.replace(year = (now.year + 1))
print(output.strftime('%Y{}.%m{}.%d{} %H{}:%M{}:%S{}').format(*'년월일시분초'))
```

<pre>
# datetime.timedelta로 시간 더하기
2023년.11월.17일 16시:37분:26초

# now.replace()로 1년 더하기
2024년.11월.09일 15시:36분:25초
</pre>
### **time 모듈**



##### 시간과 관련된 기능



##### **time.sleep()** - 어느 시간까지 코드 진행을 정지시키는 함수



```python
import time

print('5초 타임스톱~')
time.sleep(5)
print('현재 정복 완료')
```

<pre>
5초 타임스톱~
현재 정복 완료
</pre>
### **urllib 모듈** - ~~나중에 외부 모듈 request 깔자 ㅋ~~

##### URL을 다루는 라이브러리


```python

from urllib import request  # ---> import request 외부 모듈이나 사용하자



# urlopen()함수로 구글의 메인 페이지 읽기

target = request.urlopen('https://www.google.com')

output = target.read()



#출력

print(output)

```


### **operator.itemgetter() 함수**



##### 딕셔너리 형태 리스트에서 콜백 함수나 람다로 최댓값 최솟값 구하기 <Lv.5(Stage3)>




```python
#키워드 매개변수에 함수 전달하기 Level_5(Stage.3)
User = [{
    '이름' : '이경민',
    '레벨' : 5
}, {
    '이름' : '김현재',
    '레벨' : 4
}, {
    '이름' : '이아현',
    '레벨' : 3
}]

def 레벨추출함수(level):
    return level['레벨']

print('# 파이썬만 했더니 너무 강함')
print(max(User, key = 레벨추출함수))
print()

print('# 슬라임 그 자체')
print(min(User, key = 레벨추출함수))
```

#### **콜백 함수** : 코드를 위에서 아래로 읽어 내리다가 '레벨추출함수'가 <br>&#160;&#160;&#160;&#160;&#160;&#160;&#160;&#160;&#160;&#160;&#160;&#160;&#160;&#160;&#160;&#160;&#160;&#160;무엇인지 알기 위해 함수를 찾아서 내용을 살펴야 됨

#### **람다** : 람다는 어려운 문법


### **operator 모듈**의 **itemgetter() 함수**는 특정 요소를 추출하는 함수를 만드는 함수



##### 코드를 읽으면서 바로 이해할 수 있다.

##### 람다 함수를 사용하는 것 보다 코드 읽는 것이 쉽다. itemgetter() 함수가 무엇인지 몰라도 코드와 함수 이름만 봐도 '어떤 기능을 하겠다' 생각할 수 있음

