---
published: true
layout: post
title:  파이썬 4-1장
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


# **나 혼자만 파이썬 레벨업 4-1화**



> **Lv.4**

>> **이경민**



## **리스트와 반복문**



#### **리스트(list)**

- 여러 가지 자료를 저장할 수 있는 자료




```python
array = [273, 32, 103, "문자열", True, False]
print(array)
```

<pre>
[273, 32, 103, '문자열', True, False]
</pre>
### **요소(element)**

- [ ] 내부에 넣는 자료



#### **인덱스(index)**

- [ ] 안에 있는 숫자(순번)



|list_a|273|32|103|'문자열'|True|False|

|:---:|:---:|:---:|:---:|:---:|:---:|:---:|

||[0]|[1]|[2]|[3]|[4]|[5]|



```python
list_a = [273, 32, 103, "문자열", True, False]

list_a[1:3]
```

<pre>
[32, 103]
</pre>

```python
list_a = [273, 32, 103, "문자열", True, False]
list_a[0] = "변경"
list_a
```

<pre>
['변경', 32, 103, '문자열', True, False]
</pre>

```python
list_b = [273, 32, 103, "문자열", True, False]
list_b[1] = "얏호~"
list_b
```

<pre>
[273, '얏호~', 103, '문자열', True, False]
</pre>

```python
list_a = [273, 32, 103, "문자열", True, False]
list_b[3][0]    #list_b의 [3] array의 [0] array 추출
```

<pre>
'문'
</pre>

```python
list_a = [[1,2,3],[4,5,6],[7,8,9]]
list_a[1]
```

<pre>
[4, 5, 6]
</pre>
### **리스트 연산하기 : 연결(+), 반복(*), len( )**



```python
list_a = [1, 2, 3]
list_b = [4, 5, 6]

print("#list")
print(list_a)
print(list_b)
print()

# 리스트 연산자
print("#리스트 기본 연산자")
print("list_a + list_b =",list_a+list_b)
print("list_a * 3 =",list_a*3)
print()

#함수
print("#길이 구하기")
print("len(list_a)=",len(list_a))
```

<pre>
#list
[1, 2, 3]
[4, 5, 6]

#리스트 기본 연산자
list_a + list_b = [1, 2, 3, 4, 5, 6]
list_a * 3 = [1, 2, 3, 1, 2, 3, 1, 2, 3]

#길이 구하기
len(list_a)= 3
</pre>
### 리스트 요소 추가하기



##### **append( )**

> 리스트명.append(요소)

##### **insert( )**

> 리스트명.insert(위치,요소)



```python
list_a = [1, 2, 3]

# 리스트 뒤에 요소 추가하기
print("# 리스트 뒤에 요소 추가하기")
list_a.append(4)
list_a.append(5)
print(list_a)
print()

# 리스트 중간에 요소 추가하기
print("# 리스트 중간에 요소 추가하기")
list_a.insert(0, 10)    #0번 index에 요소 10 추가
print(list_a)
```

<pre>
# 리스트 뒤에 요소 추가하기
[1, 2, 3, 4, 5]

# 리스트 중간에 요소 추가하기
[10, 1, 2, 3, 4, 5]
</pre>
### 여러 요소를 한 번에 추가하기



##### **extend( )**



> 리스트명.extend(추가 요소 리스트)



```python
list_a = [1, 2, 3]
list_a.extend([4, 5, 6])
print(list_a)
```

<pre>
[1, 2, 3, 4, 5, 6]
</pre>
#### 이와 같이 리스트 연산자는 비파괴적 : list_a, list_b가 그대로임

#### append( ), insert( ), extend( )는 파괴적 : list_a에 추가됨으로서 list_a는 다른 변수가 됨


### 리스트에 요소 제거하기



- 인덱스로 제거하기



- 값으로 제거하기


### **인덱스로 제거**



> del 키워드, pop( )

#### 요소의 위치를 기반으로 요소를 제거



### 형태

- del 키워드

> del 인덱스명[인덱스]

- pop( )

> 리스트명.pop(인덱스)



```python
list_a = [0, 1, 2, 3, 4, 5]
print("#리스트의 요소 하나 제거하기")

#제거 방법[1] - del 키워드
del list_a[1]
print("del list_a[1]:", list_a)

#제거 방법[2] - pop( )
list_a.pop(2)
print("pop(2):",list_a)
```

<pre>
#리스트의 요소 하나 제거하기
del list_a[1]: [0, 2, 3, 4, 5]
pop(2): [0, 2, 4, 5]
</pre>
## 여기서 잠깐~

### 리스트 슬라이싱



> 슬라이싱

- 리스트에 [:] 연산자로 리스트 범위를 지정하여 여러 요소를 선택



### 슬라이싱 형태

> 리스트[시작_인덱스 : 끝_인덱스 : 단계]




```python
list_b = [0, 1, 2, 3, 4, 5, 6]
del list_b[3:6]
list_b
```

<pre>
[0, 1, 2, 6]
</pre>

```python
list_c = [0, 1, 2, 3, 4, 5, 6]
del list_c[:3]
print(list_c)

list_d = [0, 1, 2, 3, 4, 5, 6]
del list_d[3:]
print(list_d)
```

<pre>
[3, 4, 5, 6]
[0, 1, 2]
</pre>

```python
numbers = [1, 2, 3, 4, 5, 6, 7, 8]
print(numbers[0:5:2])

numbers_1 = [1, 2, 3, 4, 5, 6, 7, 8]
print(numbers_1[::-1])
```

<pre>
[1, 3, 5]
[8, 7, 6, 5, 4, 3, 2, 1]
</pre>
### 값으로 제거하기



#### 값을 지정해서 제거하는 것



##### **remove( )**

> 리스트.remove(갮)



```python
list_c = [1, 2, 1, 2]
list_c.remove(2)    #인덱스 2가 아닌 값 2 제거
list_c      # 맨 앞 2 제거 후 출력
```

<pre>
[1, 1, 2]
</pre>
### 모두 제거하기



#### **clear( )** : 리스트 내부 요소 모두 제거



> 리스트.clear( )



```python
list_d = [0, 1, 2, 3, 4, 5]
list_d.clear()
list_d
```

<pre>
[]
</pre>
### 리스트 정렬하기



#### **sort( )** : 기본 오름차순 정렬



> 리스트.sort( )



```python
list_e = [52, 273, 103, 32, 275, 1, 7]
list_e.sort()
print(list_e)

list_e.sort(reverse=True)
print(list_e)
```

<pre>
[1, 7, 32, 52, 103, 273, 275]
[275, 273, 103, 52, 32, 7, 1]
</pre>
### 리스트 내부에 있는지 확인하기



#### in/not in 연산자



> 값 in 리스트



> 값 not in 리스트



```python
list_a = [52, 273, 103, 32]
print(273 in list_a)
print(1000 in list_a)
print(273 not in list_a)
print(1000 not in list_a)
```

<pre>
True
False
False
True
</pre>
## **for 반복문**



```python
for i in range(10):
    print('출력')
```

<pre>
출력
출력
출력
출력
출력
출력
출력
출력
출력
출력
</pre>
### for 반복문 : 리스트와 함께 사용하기



> for 반복자 in 반복할 수 있는 것: <br> &nbsp;&nbsp;&nbsp;&nbsp; 코드



```python
#리스트 선언
array = [273, 32, 103, 57, 52]

# 리스트에 반복문을 적용
for element in array:
    #출력
    print(element)
```

<pre>
273
32
103
57
52
</pre>

```python
for character in "안녕하세요":
    print("-", character)
```

<pre>
- 안
- 녕
- 하
- 세
- 요
</pre>
### 중첩 리스트와 중첩 반복문



- [1, 2, 3] - 1차원 리스트

- [[1, 2, 3],[4, 5, 6]] - 2차원 리스트

- [[[1, 2] 3],[4, 5, [6]]] -3차원 리스트



#### n-차원 리스트 요소를 모두 확인하려면 반복문을 n번 중첩해야 함



```python
list_of_list = [
    [1, 2, 3],
    [4, 5, 6, 7], 
    [8, 9]
]

for items in list_of_list:
    for item in items:
        print(item)
```

<pre>
1
2
3
4
5
6
7
8
9
</pre>

```python
list_of_list = [
    [1, 2, 3],
    [4, 5, 6, 7], 
    [8, 9]
]

for items in list_of_list:
    for item in items:
        print(items)
```

<pre>
[1, 2, 3]
[1, 2, 3]
[1, 2, 3]
[4, 5, 6, 7]
[4, 5, 6, 7]
[4, 5, 6, 7]
[4, 5, 6, 7]
[8, 9]
[8, 9]
</pre>
#### zom the Araboza



## **전개 연산자**



- *리스트 -> 리스트[0], 리스트[1], ....


#### 1. 리스트 내부에 사용하는 경우



```python
a = [1, 2, 3, 4]
b = [a, a]
print(b)

a = [1, 2, 3, 4]
b = [*a, *a]
print(b)
```

<pre>
[[1, 2, 3, 4], [1, 2, 3, 4]]
[1, 2, 3, 4, 1, 2, 3, 4]
</pre>

```python
# append( ) 함수
a = [1, 2, 3, 4]
a.append(5)
print('a =', a) # -> a 내용 변경(파괴적)

b = [1, 2, 3, 4]
c = [*b, 5]
print('b =',b) # -> b 내용 그대로(비파괴적)
print('c =',c) # -> b 내용 + [5] 
```

<pre>
a = [1, 2, 3, 4, 5]
b = [1, 2, 3, 4]
c = [1, 2, 3, 4, 5]
</pre>
#### 2. 함수 매개변수 위치에 사용하는 경우



```python
a = [1, 2, 3, 4]
print(*a)   # print(1, 2, 3, 4)처럼 동작
print(a)
```

<pre>
1 2 3 4
[1, 2, 3, 4]
</pre>
### **for 반복문과 범위**



> for 숫자 변수 in 범위: <br> &nbsp;&nbsp;&nbsp;&nbsp; 코드


