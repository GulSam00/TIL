
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

#### 변수

* a = 2 / int(egar)(정수)
* b = "frog" / string(문자열)
* c = 3.12 / float(소수)
* d = True / Boolean(참 혹은 거짓)
* e = None / Nonetype(아무것도 없는 )

* 파이썬에서 변수 이름 지을 때 단어 사이에 '_' 넣기(snake case)

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
  ```
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

```
sam = {
    "age" : 21,
    "korean" : True, 
}
print (sam["korean"])
```
특정값만 추출할 수 있음

```
a = dict()
b = {}
print(type(a))
print(type(b))
```

[파이썬으로 할 수 있는 걸 찾으려면](https://docs.python.org/3/library/)
Mutable 바꿀 수 있는
Immutable 바꿀 수 없는

["key"] ["key value"]
키는 변수와는 관련이 없는 개념인가?
x=["c":True
추가할 때 한 번에 여러 개 못하나?

