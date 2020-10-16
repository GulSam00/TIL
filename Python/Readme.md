
# 개요

[노마드코딩](https://nomadcoders.co/) 강좌를 통한 웹스크리퍼 제작

## 목차



### 시작하며

파이썬 - 가장 인기있는 프로그래밍 언어

웹 개발, GUI, 데이터 시각화, 데이터 사이엔스... 여러 분야에 사용

다양한 분야의 많은 커뮤니티

---

이론 - 프로젝트 - Django 팁

구글 크롬에서만 작동

---

잘 질문하는 것은 중요하다
* 무작정 안된다고 하면 도와줄 수 없다.
1. 목적이 뭔지
2. 뭐를 시도했는지
3. 어느 부분이 안되는지
4. 무슨 error인지

---

프로그래밍 언어인 Python을 컴퓨터가 이해할 수 있도록 가르쳐야 함.

[repl.it](repl.it)이라는 사이트를 통해 설치하지 않고도 Python을 칠 수 있음.

---

### 이론

---

#### 변수

* a = 2 / int(egar)(정수)
* b = "frog" / string(문자열)
* c = 3.12 / float(소수)
* d = True / Boolean(참 혹은 거짓)
* e = None / Nonetype(아무것도 없는 )

* 파이썬에서 변수 이름 지을 때 단어 사이에 '_' 넣기(snake case)

---

### 리스트

열거형 타입
1. list (Mutable)
  * 순서가 있는 수정가능한 객체의 집합.
  * 수정, 삭제, 추가가 가능.
  * list 는 [] 대괄호로 작성하고 ,로 구분.
  * 0으로 시작하는 인덱스로 접근 가능
  ```
  a = [1, 2, 3, 4, 5]
  print (a[0])
  >>> 1
  print (a[2])
  >>> 3
  ```
  * .append로 값을 추가할 수 있다.
  *.reverse로 역순으로 배열할 수 있다.
1. tuple (Immutable)
  * 소괄호()안에 값을 넣고 ,로 나눠준다.
  
1. dictonary 
  * 중괄호 안에 `x = {} or x=dict()`로 선언. 선언할 때 값을 넣으려면 `x = {"a" : 1, "b" : "B"}`로. 값을 추가할 때는 `x=["c":True]`로.
  ```python
  sam = {
  "name" : "sam",
    "age" : 21,
    "korean" : True,
    "fav_food" : ["potato chip", "chip"]
}
sam=["hobby":"watching movie"]
```
* 모든 변수를 string
, 쓰는 거 잊지 않기
= 를 : 로 바꾸기

```python
sam = {
    "age" : 21,
    "korean" : True, 
}
print (sam["korean"])
```
특정값만 추출할 수 있음

```python
a = dict()
b = {}
print(type(a))
print(type(b))
```

[파이썬으로 할 수 있는 걸 찾으려면](https://docs.python.org/3/library/)

Mutable 바꿀 수 있는  Immutable 바꿀 수 없는

?["key"] ["key value"]
키는 변수와는 관련이 없는 개념인가? 

[해설](https://dojang.io/mod/page/view.php?id=2213) ! 딕서너리에서 키와 키값에는 문자열 뿐만 아니라 정수, 실수, 불리안도 들어갈 수 있다.

?x=["c":True]
추가할 때 한 번에 여러 개 못하나?

---

#### 함수

특정 행동을 반복하기 위해서 사용

print(), type()... Bulit-in function. 기본적으로 파이썬에 내장되어 있는 함수들.

print () : 괄호 안의 값을 콘솔에 출력
len() : 괄호 안의 값의 길이를 출력
type() : 변수의 종류를 출력

```python
print(len("dasdsa"))
```
함수를 조합할 수도 있다.

```python
age = "18"
print (type(age))
age = int(age)
print (type(age))
n_age = (type(age))
```
?n_age의 값은 무엇인가? int? "<class 'int'>"

---

#### 함수

```python
def [함수의 이름]():
  print ("Hello")
  print ("bye")
  
```

* **파이썬에서는 {}가 아닌 들여쓰기로 함수의 시작과 끝을 판단한다. 주로 tap을 사용해 구분한다.**
* 함수를 정의한 후 이름 뒤에 ()를 붙이면 함수가 호출된다.

```python
say_hello()

def plus(a, b=0):
  print (a + b)

plus(2, 5)
```

* 함수를 호출할 때마다 전달인자(argument)를 통해 괄호 안 매개변수(parameter)에 값을 넣어줄 수 있다, 매개변수가 존재하는데 값을 넣지 않으면 에러가 발생한다.
* 파라미터를 여러 개 만들 수도 있다.
* 파라미터의 기본값을 지정해줄 수 있다.
* **parameter(매개변수)는 함수를 정의할 떄 나열하는 변수명이다.**
* **argument(전달인자)는 함수를 호출할 때 전달 또는 입력되는 변수값이다.**

```python
def p_plus(a, b):
  print (a + b)

def r_plus(a, b):
  return (a + b)

p_result = p_plus(2, 3)
r_result = r_plus(2, 3)

print (p_result, r_result)

# 응용
def passward(p):
  if p == 3:
    return True
  else:
    return False

result = passward(3)
print (result)
```
* return을 사용하면 함수를 호출할 때 return된 값으로 치환되어진다.
* 아무것도 return하지 않으면 변수의 값은 None이 된다.
* return은 함수를 즉시 종료시킨다. 두 번 return 시킬 수는 없다.
* **함수의 리턴값을 받는 변수 없이 아규먼트만 입력해도 에러가 나지 않는다.**

```python
def minus(a, b):
  return a - b
 
result = minus(b =30, a =1)
print(result)

def say_hello(name, age):
  return f"Hello {name} you age {age} years old"
 
hello = say_hello("sam", "21")
print (hello)
print (type(hello))
```
* 아규먼트에 키워드를 넣어 순서대로가 아닌 원하는 파라미터에 알규먼트 값를 입력할 수 있다. (Keyworded Arguments) 아규먼트가 많을 때 실수하는 것을 막아준다.
* 문자열 앞에 f를 넣어주면 {변수}의 값을 출력할 수 있다.

---

#### 코드 챌린지

---

#### 조건문

```python
def plus(a, b):

  if type(a) is int or type(a) is float:
    return a + b
  else:
    return None

result = plus(1.22, 10)
print (result)
```
* if, else의 끝에는 :를 입력해야 한다.
* ==는 is로도 쓸 수 있다.

```python
def age_check(age):
  print (f"you are {age}")
  if age < 18:
    print ("go away!")
  elif age == 18 or age == 19:
    print ("umm...")
  elif age > 20 and age < 25:
    print ("you are still kind of young.")
  else:
    print ("enjoy your drink!")

age_check(19)
```
* x or y - 둘 중 하나라도 참이면 참
* x and y - 둘 중 하나라도 거짓이면 거짓
* not x - 거짓이면 참, 참이라면 거짓
* elif(else if) - 모든 if문을 거치고 거짓이면 else로

? if 말고 elif를 쓰는 이유는? if 써도 되긴 되네? 

[해설](https://okky.kr/article/209530) ! if가 여러개 있으면 모든 조건문을 대입해야 하지만 elif는 if에 해당되지 않은 값들만 처리하게 된다.

---
