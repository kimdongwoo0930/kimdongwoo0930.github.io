---
date: 2024-06-16 10:30:00 +0900
categories: [React]
tags: [리액트, React]
---

# [React] React Router를 사용해보자.

리액트 라우터를 사용해보기전에 라우팅이 무엇인지 알아보자.

## 1. 라우팅이란?

라우팅이란 사용자가 URL을 요청하면 해당 URL에 맞는 페이지를 사용자에게 보여주는 것이다.

## 2. React Router

리액트에서 라우팅을 해주는 라이브러리는 많이 있지만, 제가 사용할려는 라이브러리는 React Router입니다.  
라우터 컴포넌트는 `BrowserRouter` 와 `HashRouter`가 있는데 이번에 사용하는건 **BrowserRouter**입니다.

> 이글은 React Router v6를 기준으로 작성되었습니다.

그래도 사용하지 않지만 각각의 Router 종류에 대해서는 알아보자.

## Router

### BrowserRouter

- History API 사용
- 큰 프로젝트에 적합하다.

### HashRouter

- URL 주소에 해쉬값을 이용하는 라우터
- 검색 엔진이 읽지 못한다.
- history Api를 사용하지 않아서 동적 페이지에 불리하다.
- 작은 규모의 프로젝트에 접합하다.

<br/>

## 설치

- npm

```bash
npm install react-router-dom
# 타입스크립트
npm install @types/react-router-dom
```

- yarn

```bash
yarn add react-router-dom
# 타입스크립트
yarn add @types/react-router-dom
```

<br/>

## 코드

### 라우터 작성

저는 router.tsx로 파일을 별개로 만들어서 작성했습니다.  
따로 라우터 함수를 작성할경우 `createBrowserRouter`를 이용해야한다.

```tsx
// router.tsx
export const router = createBrowserRouter([
  {
    path: "/",
    element: <App />,
    children: [
      {
        index: true,
        element: <Home />
      },
      {
        path: "about",
        element: <About />
      }
    ]
  }
]);
```

> index : true를 작성하면 url: https://url/ 로 접속하면 해당 페이지로 이동  
> path : about을 작성하면 url: https://url/about 으로 라우팅시켜준다.

- path : 라우팅해줄 URL 이다.
- children : 라우팅 해줄 페이지가 많을 경우 묶어줄수 있다.
- errorElement : 없는 URL로 접속시 보여줄 페이지
- element : 페이지 기본 틀 Root.tsx로 만들어주었다.

```tsx
// Root.tsx
import { Outlet } from "react-router-dom";
import { Navigation } from "./Navigation";
import styled from "styled-components";

export const Root = () => {
  return (
    <Layout>
      <Navigation />
      <Outlet />
    </Layout>
  );
};
```

그리고 작성한 router파일을 App.tsx안에 `RouterProvider` 태그에 작성해주면 연결됩니다.

```tsx
// App.tsx
import { RouterProvider } from "react-router-dom";
import { router } from "./pages/router";

export const App = () => {
  return (
    <>
      <RouterProvider router={router} />
    </>
  );
};
```

<br/>

### 페이지 이동

1. **Link** 이용

```tsx
import { Link } from "react-router-dom";

<Link to="/url"></Link>;
```

2. **navigate** 이용

```tsx
const navigate = useNavigate();

navigate("/url");
```

나는 2번을 이용해서 페이지 이동을 했다.

Ex)

```tsx
// useNavigationLink.tsx
import { useNavigate } from "react-router-dom";

export const useNavigationLink = () => {
  const navigate = useNavigate();

  const navigationLink = (name: String): void => {
    switch (name) {
      case "강의실":
        navigate("/classroom", { replace: true });
        break;
      case "숙소":
        navigate("/room", { replace: true });
        break;
      case "설문 생성":
        navigate("/survey/create", { replace: true });
        break;
      case "설문 리스트":
        navigate("/survey/list", { replace: true });
        break;
    }
  };

  return navigationLink;
};

// Navigation.tsx
const navigationLink = useNavigationLink();

onClick={() => navigationLink('강의실')}
```

#### Link로 Data 보내기

```tsx
import { Link } from "react-router-dom";

<Link to="/url" state={보낼data}></Link>;
```

이렇게 React Router를 사용해보았습니다.

## 마무리

아직 모든걸 다루어보진 않았지만 다음에 로그인 여부나 데이터 여부를 페이지 이동전에 확인하는걸 구현할때 그때 추가로 작성하겠습니다.
