---
date: 2024-01-12 18:00:00 +0900
categories: [GitHub, GitBlog]
tags: [Git]
---

# Chirpy 테마 커스터마이징 하기

저번에는 Chirpy 테마를 적용하는법을 해보았으니 요번에는 테마를 커스터마이징 해보겠습니다.

<br/>

> 로컬에서 **jeckyll servce**로 구동했을 경우, 코드가 수정되는 경우 반드시 재구동을 해주어야 합니다.

<br/>

### \_config.yml로 커스터마이징 하기

| 항목           |     값      | 설명                                                                                                                                    |
| -------------- | :---------: | --------------------------------------------------------------------------------------------------------------------------------------- |
| `lang`         |     ko      | `ko`로 설정하면 언어를 한글로 설정합니다.                                                                                               |
| `timezone`     | Asia/Seoul  | 서울 표준시로 설정이 됩니다.                                                                                                            |
| `tile`         | 블로그 제목 | 이곳을 수정하면 블로그 제목으로 설정됩니다.                                                                                             |
| `tagline`      |  부연 설명  | title 밑에 작은 글씨로 부연 설명을 넣얼수 있다.                                                                                         |
| `description`  |   키워드    | SEO를 위한 키워드 입력합니다. 쉽게 생각하면 포털 검색에 어떤 키워드로 나의 블로그를 검색할 수 있게 할것인지 결정해서 입력하시면 됩니다. |
| `social.name`  |    이름     | 게시글에 표시될 이름을 적으시면 됩니다.                                                                                                 |
| `social.email` |   이메일    | 본인의 메일 주소를 적으시면 됩니다.                                                                                                     |
| `theme_mode`   | light, dark | 본인이 원하는 테마 모드를 정하시면 됩니다. 기본은 light입니다.                                                                          |
| `avatar`       |     url     | 블로그 상단에 표시될 프로필 사진을 설정합니다.                                                                                          |
| `toc`          |    true     | 게시글의 오른쪽 목차를 표시합니다.                                                                                                      |
| `paginate`     |     10      | 한 목록에 보여질 글의 개수를 정합니다.                                                                                                  |

<br/>

### 이미지 업로드 하기

외부 url을 입력을 해도 가능하지만, 블로그에 이미지를 업로드해서 설정하는 것도 방법중 하나입니다. 이미지를 `assets/img/` 폴더안에 넣어두면 됩니다.

<br/>

### 블로그 제목과 서브 설명 폰트/색상 바꾸기

`_sass/addon/commons.scss`에 제목과 서브 설명에 대한 설정들이 있습니다.

```css
/* 여기를 수정하면 제목의 색상이나 크기 글씨체를 변경 할 수 있다. */
.site-title {
  font-family: inherit;
  font-weight: 900;
  font-size: 1.75rem;
  line-height: 1.2;
  letter-spacing: 0.25px;
  margin-top: 1.25rem;
  margin-bottom: 0.5rem;
}
/* 여기를 수정하면 서브 설명의 색상이나 크기 글씨체를 변경 할 수 있다. */
.site-subtitle {
  font-size: 95%;
  color: var(--site-subtitle-color);
  margin-top: 0.25rem;
  word-spacing: 1px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}
```

<br/>

### 프로필 사진 바꾸기

`_config.yml` 파일에서 `avatar` 항목에 이미지의 경로를 입력해주면 됩니다.  
이미지의 경로는 `assets/img/`안에 있습니다. 이 폴더안에 필요한 이미지를 넣고 지정해주시면 됩니다.

<br/>

### 왼쪽 사이드바 배경 바꾸기

왼쪽에 있는 사이드바 배경을 사진으로 변경이 가능합니다.  
사이드 바에 대한 코드는 `_sass/addon/commons.scss`에 있습니다.

```css
#sidebar {
  /* 기본 배경 
  background: var(--sidebar-bg);
*/
  /* 밑에 코드로 변경하기 */
  background: url("/assets/img/파일명.jpg");
  background-size: 100% 100%;
  background-position: center;
}
```

<br/>

### About 변경하기

`_tabs` 디렉토리 안에 있는 `about.md`파일을 수정하면 About부분이 변경됩니다.  
같은 폴더 안에있는 `archives.md`,`categories.md`,`tags.md` 파일을 수정하면 왼쪽 사이드 탭메뉴 페이지도 수정할 수 있습니다.

<br/>

### favicon 변경하기

`favicon`은 브라우저 탭에 표시되는 이미지 입니다.
자신이 원하는 이미지로 변경하고 싶으면 적당한 크기로 이미지를 생성한 후 [여기](https://www.favicon-generator.org/)에서 favicon을 만들 수 있습니다.  
생성 후 `favicon`이라는 파일 4개를 `assets/img/favicon`디렉토리에 넣어주시면서 기존 파일을 덮으면 적용이 바로 됩니다.

<br/>

참고 (https://www.irgroup.org/posts/Chirpy-%ED%85%8C%EB%A7%88-%EC%BB%A4%EC%8A%A4%ED%84%B0%EB%A7%88%EC%9D%B4%EC%A7%95/)
