---
date: 2024-01-18 17:00:00 +0900
categories: [HTML / CSS]
tags: [HTML,CSS]
---

## Django 사이트
![장고 사이트](../../assets/img/HTML%20CSS/Django사이트.png)
- 장고 사이트 상단 네비게이션바 부분을 HTML로 작성하겠습니다.
- CSS는 없이 구조만 작성했습니다.


**CODE**
```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Django</title>
</head>
<body>
    <div class="header">
        <div class="container">
            <div class="container-left">
                <div class="logo">
                    <h1>Django</h1>
                    <p>The web framework for perfectionists with deadlines</p>
                </div>
                <div class="menu">
                    <div class="menu-item">OVERVIEW</div>
                    <div class="menu-item">DOWNLOAD</div>
                    <div class="menu-item">DOCUMENTATION</div>
                    <div class="menu-item">NEWS</div>
                    <div class="menu-item">COMMUNITY</div>
                    <div class="menu-item">CODE</div>
                    <div class="menu-item">ISSUES</div>
                    <div class="menu-item">ABOUT</div>
                    <div class="menu-item">♥ DONATE</div>
                </div>
            </div>
        </div>
    </div>
</body>
</html>
```

<br>

### Result
![Alt text](../../assets/img/HTML%20CSS/Django예시결과.png)

<br>

