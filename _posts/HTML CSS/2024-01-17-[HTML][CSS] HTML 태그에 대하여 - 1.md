---
date: 2024-01-17 16:00:00 +0900
categories: [HTML / CSS]
tags: [HTML,CSS]
---

# Tag
---

### !DOCTYPE 
우리가 html 문서를 작성할 때 항상 맨 윗줄에 있어야 하는 `선언문`입니다.

`!DOCTYPE`은 태그가 아니라 이 HTML파일이 `HTML5`버전이라는것을 알려주는 것이다.  

<br/>

### HTML 
앞에서 말했던 `!DOCTYPE`을 제외한 모든 `HTML Elements`는 `<html> </html>`으로 감싸져 있습니다.

그래서 문서를 읽을때 `HTML태그`가 시작되면 요소들을 그릴준비를 합니다.  

<br/>

## `<head>`
`<head>`태그는 메타데이터들을 감싸고 있는 태그여서 화면에 표시되지 않습니다.  

**CODE**
```html
    <html>
        <head>
            <meta charset="utf-8">
            <meta name="viewport" content="width=device-width">
            <title>Test</title>
        </head>
    </html>
```

<br/>

## `<meta>`
`<meta>`태그는 메타데이터들을 정의하는데 사용한다. 메타데이터는 브라우저, 검색엔진, 키워드에서 사용되고, `charset`은 브라우저가 사용할 문자셋을 정의해준다.

> 만약 한글,중국어,일본어가 포함된 페이지 파일이라면 `utf-8`이라는 값으로 문자 인코딩 설정을 해주어야 합니다.

**CODE**
```html
    <meta charset="utf-8">
```

<br/>

## `<title>` 
`<title>`태그는 문서의 제목을 정의해주고 브라우저 탭에 표시될 제목입니다.

**CODE**
```html
    <title> 제목 </title>
```

<br/>

## `<style>`
`<style>`태그는 HTML에 대한 `style`정보들을 정의할 수 있다.

* CSS는 별도로 css파일을 만들어서 정의할 수 있다.

**CODE**
```html
    <head>
        <style>
            body{
            background-color: skyblue;
            width : "100%";
            }
        </style>
    </head>
```

<br/>

## `<link>`
`<link>`는 외부 리소스를 가져와 사용하기 위한 태그입니다.
HTML하고 외부 CSS를 연결하여 사용할 수 있다.

**CODE**
```html
    <head>
        <meta charset="utf-8">
        <title>제목</title>
        <link rel="stylesheet" href="style.css">
    </head>
```

<br/>

## `<script>`
`<script>`는 문서 내에서 자바스크립트를 사용할때 쓰는 태그입니다.

**CODE**
```html 
    <head>
        <meta charset="utf-8">
        <script>
            document.addEventListener('click', function () {
            alert('Clicked!');
            });
        </script>
    </head>
```
---

<br/>

### 마무리
다음에는 `<body>`부분 태그에 대해 알아보도록 하자