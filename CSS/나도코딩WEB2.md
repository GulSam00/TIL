# CSS

* [CSS 등장 이전의 상황](#CSS-등장-이전의-상황)

* [CSS의 등장](#CSS의-등장)

* [혁명적 변화](#혁명적-변화)

* [CSS 속성(Property)을 스스로 알아내는 방법](#CSS-속성을-스스로-알아내는-방법)

* [CSS 선택자(Selector)를 스스로 알아내는 방법](#CSS-선택자를-스스로-알아내는-방법)

* [박스 모델](#박스-모델)

* [그리드](#그리드)

* [반응형 디자인](#반응형-디자인)

---

## CSS 등장 이전의 상황

웹을 더 아름답게 만드는 두 가지 방법

1. 쉽지만 한계있음
    - HTML에 디자인과 관련된 새로운 태그 추가 
2. 어렵지만 근본적인 해결책
    - 디자인에 최적화된 새로운 언어 개발

---

1. <font> 태그
```
<h1>Hello</h1>
<h1><font color="red">Hello</font></h1>
```
정보에 관련된 기존의 태그와는 달리 <font>는 디자인에 대한 코드, 정보로서의 가치가 떨어지게 된다.

지금은 거의 사용되지 않는다.

한계를 느끼며 CSS로 교체됨.

---

## CSS의 등장

최초의 웹브라우저는 HTML만을 해석해서 처리했다.

HTML과는 완전히 다른 CSS도 HTML로 간주한다.

그렇기에 컴퓨터에게 CSS를 CSS의 문법으로 해석해야 한다고  
HTML의 문법으로 알려주어야 한다.
```
<head>
    <style> h1 {
        color:red;
}
    </style>
</head>
```
중복된 작업을 단 하나의 코드로 제거할 수 있게 된다.

규모가 클수록 중복의 제거의 중요성도 커진다.

디자인과 관련된 코드는 <style>태그 안에 갖혀있게 된다.
    
HTML이 정보에 전념할 수 있게끔 하기 위해  
훨씬 효율적으로 웹페이지를 디자인하기 위해 CSS가 도입됨.

---

## 혁명적 변화

웹브라우저로 하여금 어디부터 어디까지가 CSS인지 구분되야 함.

1. <style>태그를 통해
```
<head>
    <style> h1 {
        color:red;
}
    </style>
</head>
``` 
효과만으로는 누구에게 지정할지를 모르기에

[] {} 코드가 추가로 필요하다.

[]를 효과를 누구에게 줄 것인가를 선택한다는 의미에서 **선택자(Selector)**라고 부른다.

선택자에게 지정될 {}안의 효과를 **선언(declaration)**이라고 부른다.


1. 속성을 통해

    ```
    <body>
    <li><a href="2.html" style="color:red">CSS</a></li>
    </body>  
    ```
    
<body>안에서의 *<style>*은 HTML의 속성이다.
    
값으로 반드시 CSS의 효과가 들어온다는 약속이 되어있다.

style 태그를 직접 사용하면 선택자를 사용할 필요가 없다.

밑줄을 없애고 싶다면
```
text-decoration: none;
```

밑줄을 만들고 싶다면

```
text-decoration: underline;
```

---

### 이론 정리

```
<!-- Selector(선택자) --> a{
    <!-- Declaration(선언, 효과) --> color:red;
    }                   <!-- Property(속성) --> <!-- Property Value(값) -->
```

---

## CSS 속성을 스스로 알아내는 방법

CSS + [] + property 로 검색

크기와 관련된 property

```
div.a {
  font-size: 15px;
}

div.b {
  font-size: large;
}

div.c {
  font-size: 150%;
}
```

정렬과 관련된 property

```
div.a {
  text-align: center;
}

div.b {
  text-align: left;
}

div.c {
  text-align: right;
}

div.c {
  text-align: justify;
}
```

! 모든 걸 기억하지 않아도 검색 몇 번이면 정보를 찾을 수 있다

! 뇌를 이기는 의지는 없다. 뇌를 혹사시키면 뇌는 수단과 방법을 가리지 않고 그 일을 하지 않을 방법을 찾을 것이다.

---

## CSS 선택자를 스스로 알아내는 방법

### class 선택자

```
  .saw {
    color:gray;
  }

#active {
  color:red;
}
  
  <li><a href="1.html"class="saw">HTML</a></li>
  <li><a href="2.html"class="saw" id="active">CSS</a></li>  <!-- class="[]", saw : html -->
  <li><a href="3.html">JavaScript</a></li>
```
saw라고만 쓰면 웹페이지의 모든 saw라는 이름의 태그를 선택하는 선택자

class가 saw인 태그만 선택하려면 앞에 .을 붙인다.

---

#### class란?

* 특정 의도에 따라 하나로 그룹핑한다 라는 뜻이 포함되어 있다.
* 여러 개의 값이 들어올 수 있다. 
* 띄어쓰기로 구분한다.
* 하나의 태그에 여러 개의 속성이 들어올 수 있다
* 여러 개의 선택자를 통해 하나의 태그를 공동으로 제어할 수 있다.

---

### id 선택자


```
  .saw {
    color:gray;
  }

#active {
  color:red;
}
  
  <li><a href="1.html"class="saw">HTML</a></li>
  <li><a href="2.html"class="saw" id="active">CSS</a></li>  <!-- class="[]", saw : html -->
  <li><a href="3.html">JavaScript</a></li>
```

---

### 이론 정리

* id 선택자의 값은 한 웹페이지에서 단 한 번만 등장할 수 있다. (중복등장해서는 안 된다)
* id 선택자는 class보다 우선순위에 있다.
* class 선택자는 tag(elements) 선택자보다 우선순위에 있다.
* 동일한 순위라면 마지막에 등장하는 선택자가 우선순위에 있다.
* **tag 선택자 < class 선택자 < id 선택자**

---

## 박스 모델

```
    <style>
      h1{
        border-width:5px;
        border-color:red;
        border-style:solid;
      }
      a{
        border-width:5px;
        border-color:red;
        border-style:solid;
      }
    </style>

```
제목 태그(h1)은 화면 전체를 사용하며 줄바꿈을 된다. 

링크(a)는 줄바꿈을 하지 않고 자기 콘텐츠만큼의 공간을 사용한다.

전체를 쓰는 태그 : block level element(tag)    
자기 크기만큼을 쓰는 태그 : inline element(tag)

```
h1{
        border-width:5px;
        border-color:red;
        border-style:solid;
        display:inline or block;
      }
```

block level element와 inline element는 display 속성의 기본값일 뿐 CSS를 통해 얼마든지 바꿀 수 있다.

---

### CSS 박스 모델

```
display:none;
```
으로 태그를 안보이게 할 수 있다.

   
```
hi, a {
  border:5px solid red;
}
```
선택자에서 콤마(,)를 통해 중복을 줄일 수 있다.

   
```
  width:100px;
  height:50px;
```
콘텐츠의 폭과 높이를 조절한다.

   
```
padding:20px;
```
콘텐츠와 테두리 사이의 간격을 조절한다.

   
```
border:5px solid:red;
```
테두리 값을 조절한다.

   
```
margin:20px;
```
테두리와 테두리 사이의 간격을 조절한다.

   
웹페이지에서 우클릭 후 검사를 누르면 태그가 어떤 CSS의 영향을 받는지 일목요연하게 알 수 있다.

---

## 박스 모델 응용

```
    <style>
h1 {
    font-size:80px;
    text-align:center;
    border-bottom:1px solid black;
    margin: 0px;
    padding: 20px;
  }
  ol {
    width:100px;
    border-right:1px solid black;
    margin:0px;
    padding:20px;
  }
  body{
    margin:0px;
  }
  </style>
  ```

---

## 그리드

순전히 디자인만을 위해 존재하는 아무런 의미도 없는 태그

div : block level element    
    
span : inline level element
    
```
  <head>
    <style>
      #grid{
        border:5px solid pink;
      }
      div{
        border:5px solid gray;
      }

    </style>
  </head>
  <body>
    <div id="grid">
    <div>NAAVAGATION</div> 
    <div>ARTICLE</div>
    </div id="grid">
  </body>
```

두 개 이상의 태그를 나란히 배치하고 싶다면 감싸는 부모 태그가 필요하다.

```
  #grid{
        border:5px solid pink;
        display:grid;
        grid-template-columns: 150px 1fr;
      }
```
첫 번째 element는 150px이라는 고정적인 크기를 가지고 나머지는 남은 공간을 가진다라는 뜻

fr : 화면 전체를 X만큼 화면 전체를 쓰게 자동으로 조정되는 단위

---

### 그리드 응용

```
<head>
  <style>
     #grid ol {
    width:100px;
    border-right:1px solid black;
    padding:20px;
    padding-left: 32px;
    margin:0px;
  }
  #grid{
    display: grid;
    grid-template-columns: 150px 1fr;
  }
  #article{
    padding-left: 25px;
  }
    </style>
  </head>
  
  <body>
  <div id="grid">
      <ol>
        <li><a href="1.html" >HTML</a></li>
        <li><a href="2.html">CSS</a></li>
        <li><a href="3.html">JavaScript</a></li>
      </ol>
  <div id="article">
      <h2>CSS</h2>
   <p>
    본문
   </p>
  </div>
  </div>
  </body>
```

- 본문의 요소들을 div 태그로 감싸고 본문의 div와 ol을 또 하나의 부모 태그인 div로 감싸준다.
- 그리드를 응용하여 요소(elements)들을 같은 열(columns)에 배치할 수 있다.
- 본문에서 리스트를 사용할 수도 있으니 선택자를 id grid의 자식태그라는 의미인 #grid ol이라고 수정한다.
- 열 : columns, 행 : rows

**창의 크기를 조절하거나 요소의 변화에 따라 그리드가 자동으로 조정된다.**

---

## 반응형 디자인

### 반응형 디자인과 미디어 쿼리 개요

**반응형 웹 or 디자인(Responsive Web) : 화면의 크기에 따라 웹페이지의 각 요소들이 반응해서 최적화된 모양으로 바뀌게 하는 것

웹은 거의 모든 정보 시스템 (운영 체제와 상관 없이)에서 동작하는 정보 시스템

수많은 형태의 화면에서 동작해야만 한다

여러 화면에 대응되는 웹페이지를 만들기 위해 탄생

다양한 환경에서 적응할 수 있는 기술의 집합체

---

#### 미디어 쿼리 (Media query)

반응형 디자인을 CSS를 통해서 구현하는데 핵심적인 개념



```
  <head>
    <style>
      div {
        border:5px solid green;
        font-size:60px;
      }
      @media(min-width:800px){
      div {
        display:none;
      }
    }
    </style>
  </head>
  <body>
    <div>
      responsive
    </div>
  </body>
```

- 화면의 폭이 최소 800px이라면 (800px 이상이라면) 중괄호 안의 값을 실행한다.
- **특정 조건을 만족했을 때면 CSS의 내용이 동작하도록 하게끔 할 수 있다.**<br/>
ㄴ미디어 쿼리

---

### 미디어 쿼리를 이용한 반응형 디자인 구현

직접 작성
```
  @media(max-width:400px)
    {
#grid{
  display: block;
  grid-template-rows: 100px 1fr;
}
#grid ol {
  border-right:0px;
}
#article {
  border-top:1px solid black;
  border-bottom:1px solid black;
}
    }
```
- 400px보다 작을 때 미디어쿼리 적용
- 기존 그리드는 그래도 두고 같은 열이 아닌 같은 행으로 변경
- 수직으로 있던 border(테두리)를 #article을 기준으로 위 아래로 변경

강의 예문
```
 @media(max-width:800px){
      #grid{
        display: block;
      }
      ol{
        border-right:none;
      }
      h1 {
        border-bottom:none;
      }
    }
```
