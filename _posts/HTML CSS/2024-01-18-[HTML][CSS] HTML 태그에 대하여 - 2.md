---
date: 2024-01-18 12:00:00 +0900
categories: [HTML / CSS]
tags: [HTML,CSS]
---

## `<body>`
`<body>`태그는 `<head>`태그 밑에 위치한 태그입니다.  
`<body>`태그안에 페이지에 보여질 요소들을 작성한다.

<br/>

### `<h1>, <h2>, <h3>, <h4>, <h5>`
이 태그는 주로 제목같은 텍스트를 보여주기위해 사용합니다.
숫자가 높아질 수록 글씨크기가 작아집니다.

**CODE**
```html
    <h1>Title</h1>
```

<br/>

### `<span>`
`<span>`태그는 텍스트를 보여주기위해 사용합니다.
이 태그사이에 텍스트를 쓰면 개행이 되지 않고 글자 그대로 출력하여 보여줍니다.

**CODE**
```html
    <span>제목: Title</span>
```

<br/>

### `<p>`
`<p>`태그도 텍스트를 보여주기위해 사용합니다.
p는 paragraph으로 주로 문단을 통채로 넣습니다.

**CODE**
```html
    <p>여기에 내용을 적습니다.</p>
```

<br/>

### `<br>`
`<br>`태그는 강제로 line break을 합니다.  
`<br>`은 따로 종료태그가 존재하지 않습니다.

**CODE**
```html
    <p>1번째 줄<br>2번째 줄<br>3번째 줄</p>
```

<br/>

### `<pre>`
`<pre>`태그는 형식화 Text를 지정할 수 있습니다.  
그래서 태그 사이에 쓰는 text 그대로 화면에 출력됩니다.

**CODE**
```html
    <pre>
        이렇게 적으면 
        줄바꿈도 알아서 되서
        출력이 가능하다
    </pre>
```

<br/>

### `<hr>`
`<hr>`태그는 수평줄을 넣고 줄바꿈을 합니다.

**CODE**
```html
    <p>Text 1</p>
    <hr>
    <p>Text 2</p>
```

<br>

### `<q>`
`<q>`태그는 짦은 인용문을 쓸때 사용합니다.  
그래서 태그를 사용하면 `<q>`태그 사이에 있는 글씨를 "로 감싸진다.

**CODE**
```html
    <p>Dong: <q>Hello everybody.</q></p>
```

<br>

### `<blockquote>`
`<blockquote>`태그는 긴 인용문을 지정할때 사용합니다.

브라우저는 `blockquote` 엘리먼트를 들여쓰기가 됩니다. 

**CODE**
```html
    <blockquote>
        <p>들여쓰기될 문장</p>
    </blockquote>
```

<br>

### `<a>`
`<a>`태그는 클릭시 주소로 이동시켜주는 태그입니다.
그래서 태그 속성값 `href`에는 이동할 주소를 기입해주어야합니다.

**CODE**
```html
    <a href="https://kimdongwoo0930.github.io" target="_blank">동로그 이동</a>
```

<br>

### `<div>`
`<div>`태그는 여러 태그들을 그룹을 지어주거나 섹션을 나누어줄때 사용합니다.
`<div>` 사용 의도
* 같은 부분끼리 그룹을 만들어서 구별하기 위해
* 디자인을 맞게 레이아웃을 분리해주기위해서
* `<div>`에 class나 id를 부여해서 css스타일을 적용할수 있다.

<br>

---

## 부모와 자식의 관계

A라는 태그가 B라는 태그의 콘텐츠로 사용이 된다면, B태그는 A태그의 부모 요소이고, A태그는 B태그의 자식 요소라고 합니다.
* `<section>`는 `<h1>`, `<ul>`의 부모 요소입니다.
* `<ul>`는 `<li>`의 부모 요소입니다.
* `<li>`는 `<ul>`의 자식 요소입니다.
* `<section>`은 `<li>`의 조상요소입니다.

**CODE**
```html
    <section class="List">
        <h1>List Title</h1>
        <ul id="list">
            <li>Item 1</li>
            <li>Item 2</li>
            <li>Item 3</li>
            <li>Item 4</li>
        </ul>
    </section>
```
<br>

---


### 마무리

다음에는 예시 사이트로 한번 html구조만 짜보겠습니다.