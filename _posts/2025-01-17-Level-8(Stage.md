---
published: true
layout: post
title:  파이썬 8장
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


# **나 혼자만 파이썬 레벨업 8-1화**



> **Lv.8**

>> **이경민**


<table>

    <tr>

        <td align = 'center'><font size = '5'><b>클래스</b></font></td>

        <td><font size = '5'>객체를 쉽고 편리하게 쓰기 위한 구문</font></td>

    </tr>

    <tr>

        <td align = 'center'><font size = '5'><b>객체</b></font></td>

        <td><font size = '5'>속성과 메소드를 갖는 것</font></td>

    <tr>

        <td align = 'center'><font size = '5'><b>인스턴스</b></font></td>

        <td><font size = '5'>클래스를 기반으로 생성한 객체</font></td>

    <tr>

        <td align = 'center'><font size = '5'><b>생성자</b></font></td>

        <td><font size = '5'>클래스 이름과 같은 인스턴스를 생성할 때 쓰는 함수</font></td>

    <tr>

        <td align = 'center'><font size = '5'><b>메소드</b></font></td>

        <td><font size = '5'>클래스를 가진 함수</font></td>

    </tr>

</table>



### **객체**

##### 속성과 메소드를 갖는 것



```python
students = [
    {"name": '이경민', "DC" : 98, "DS" : 92, "Python" : 90, "Semiconductor" : 95},
    {"name": '김현재', "DC" : 88, "DS" : 72, "Python" : 80, "Semiconductor" : 89},
    {"name": '배현진', "DC" : 97, "DS" : 80, "Python" : 80, "Semiconductor" : 75},
    {"name": '허유림', "DC" : 90, "DS" : 85, "Python" : 80, "Semiconductor" : 78}
]

# 학생 한 명씩 반복
print("이름", "총점", "평균", sep = "\t")

for student in students:
    # 점수의 총합과 평균 구하기
    score_sum = student["DC"] + student["DS"] + \
        student["Python"] + student["Semiconductor"]
    score_average = score_sum / 4
print(student['name'], score_sum, score_average, sep="\t")
```

<pre>
이름	총점	평균
허유림	333	83.25
</pre>
### **클래스**

##### 객체를 쉽고 편리하게 쓰기 위한 구문


```python

class 클래스 이름:

    클래스 내용

```

---


### **생성자**

##### 클래스 이름과 같은 인스턴스를 생성할 때 쓰는 함수



~~~python

class 클래스 이름:

    def __init__(self, 추가적인 매개변수):

        pass

~~~

---


~~~python

# 클래스 선언

class Student:

    def __init__(self, name, korean, math, english, science):

        self.name = name

        self.korean = korean

        self.math = math

        self.english = english

        self.science = science

# 학생 리스트 선언

students = [

    Student('이경민', 98, 92, 90, 95),

    Student('김현재', 88, 72, 80, 89),

    Student('배현진', 97, 80, 80, 75),

    Student('허유림', 90, 85, 80, 78)

]



# Student 인스턴스의 속성에 접근하는 방법

Students[0].name

Students[0].korean

Students[0].math

Students[0].english

Students[0].science

~~~

##### 이렇게 만들면 student 인스턴스가 생성될 때 속성이 직접 추가된다.

---


#### <u>여기서 잠깐~</u>

### **소멸자(destructor)**

##### _ _ del _ _ (self)

##### 생성자와 반대로 인스턴스가 소멸될 때 호출하는 함수



```python
class Test:
    def __init__(self,name):
        self.name = name
        print('{} - 생성됐음'.format(self.name))
    def __del__(self):
        print('{} - 파괴됐음'.format(self.name))

test = Test("A")
```

<pre>
A - 생성됐음
A - 파괴됐음
</pre>
### **메소드**

##### 클래스를 가진 함수



```python

class 클래스 이름:

    def 메소드 이름(self, 추가적인 매개변수):

        pass

```

---



```python
class Student:
    def __init__(self, name, korean, math, english, science):
        self.name = name
        self.korean = korean
        self.math = math
        self.english = english
        self.science = science

    def get_sum(self):
        return self.korean + self.math +\
            self.english + self.science

    def get_average(self):
        return self.get_sum()/4
    
    def to_string(self):
        return '{}\t{}\t{}'.format(\
            self.name,\
            self.get_sum(),\
            self.get_average())

students = [
    Student('이경민', 98, 92, 90, 95),
    Student('김현재', 88, 72, 80, 89),
    Student('배현진', 97, 80, 80, 75),
    Student('허유림', 90, 85, 80, 78)
]

print('이름', '총점', '평균', sep ='\t')
for student in students:
    print(student.to_string())
```

<pre>
이름	총점	평균
이경민	375	93.75
김현재	329	82.25
배현진	332	83.0
허유림	333	83.25
</pre>
### **인스턴스**

##### 클래스를 기반으로 생성한 객체



