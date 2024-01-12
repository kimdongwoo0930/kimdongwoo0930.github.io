---
date: 2024-01-11 15:45:00 +0900
categories: [GitHub,GitBlog]
tags: [Git]
---


# 시작

깃블로그를 만들기위해 여러 플랫폼들중 고민을 많이했다. 그 중 마음에 가장 들었던것은 **GitHub**에서 지원하는 것을 이용해 하는 깃블로그를 하는게 좋아보였다. 내 깃허브에 직접 코드를 올려두고 하면서 직접 커스터마이징도 할 수 있다는 장점이 있어서 깃블로그를 선택했다. 이게 내 깃블로그의 첫 게시글이 될 것이다. 

- 이 글은 MacOS 기준으로 작성되었습니다.

<br/>

# 테마 고르기

먼저 Jekyll에 본다면 많은 테마들이 있다. 그 중 가장 마음에 드는건 Chirpy테마가 가장 마음에 들어서 이 테마로 선택했습니다.
![예시](https://camo.githubusercontent.com/8f2b30de2cccca73b48c4a424f0d83a9d2fed609738fa311e3e1f1f6c903e9bf/68747470733a2f2f6368697270792d696d672e6e65746c6966792e6170702f636f6d6d6f6e732f646576696365732d6d6f636b75702e706e67)
(출처 : https://github.com/cotes2020/jekyll-theme-chirpy)

<br/>

# 준비 작업

Github 페이지는 서버 없이 백그라운드에서 `Jekyll`를 이용해 작동된다. 
`Jekyll`은 Ruby라는 언어로 개발되었습니다. 이것들을 이용하면 markdown만으로 게시글을 작성할 수 있습니다.
`gem`은 Ruby의 패키지를 말하는 것이고, `bundler`는 패키지 관리 프로그램을 말한다.

1. 이러한것들을 모두 필요로 하기때문에 `Ruby`,`Gem`,`Jekyll`,`Bundler`를 설치해주어야 한다.
<br/>
2. 맥을 사용한다면 `Gem`은 설치되어 있어서 따로 설치가 필요없다.
<br/>
3. `gem` 설치하기
    ```bash
    gem install bundler
    ```
    맥에서 권한 오류가 뜰수 있기때문에 권한을 주고 설치해야 할수도 있다.  
<br/> 
4. `jekyll` 설치하기
    ```bash
    gem install jekyll
    ```
    <br/>

5.  `Jekyll`블로그가 github에서 렌더링되는데 필요한 의존성 패키지를 설치해야한다.
    ```bash
    gem install github-pages
    ```
<br/>

## Chirpy 테마 가져오기
테마를 가져오는 방법은 2가지가 있지만 커스텀을 해보기위해서  fork를 이용한 방법으로 진행 했습니다.

1. Fork Chirpy에서 리포지토리 이름을 `<Github 아이디>.github.io`로 설정한 후 리포지토리를 생성합니다.
<br/>

2. 터미널에서 소스를 clone 한다.
```bash
git clone https://github.com/<username>/<username>.github.io.git
```
<br/>

3. 프로젝트 루트 디렉토리로 들어가서 chirpy를 초기화 한다.
```bash
bash tools/init
```
위 명령어를 입력하면 다음과 같은 작업들이 실행된다.
- `.travis.yml`, `_posts` 파일및 디렉토리 삭제
- `.github/workflows/pages-deploy.yml.hook`에서 .hook 삭제하고 이를 제외한 .github내 다른 폴더와 파일들 삭제
- `Gemfile.lock`을 .gitignore에서 삭제
- 변경을 저장하기 위해 자동적으로 commit 생성

4. dependencies 설치
첫 구동을 하기 전에 루트 디렉토리로 이동하여 아래 명령어를 통해 의존성을 설치해준다.
```bash
bundle
```
<br/>

# 로컬에서 테스트하기
```bash
bundle exec jekyll s 
```
위 명령어를 실행 한 후 <http://localhost:4000>를 접속하면 볼 수 있습니다.

<br/>

# 깃 블로그 배포하는법
1. 배포를 하기위해서는 `_config.yml`에서`url`에 https://[username].github.io 형식을 입력한다.
<br/>
2. Github repository에서 **Setting -> Pages -> Build and deployment에서 Source에 있는 Github Actions를 선택** 해주어야 한다.
<br/>
3. 아까 url설절한 `_config.yml`에서 필요한 부분을 설정하고 커밋 후 푸쉬를 하면 된다.

- **lang** : 언어 선택
- **timezone** : 기준 시간 
- **title** : 블로그 제목 
- **tagline** : 제목 밑 부연 설명 
- **description** : 블로그 서브 타이틀
- **github** : 깃 허브 닉네임
- **twitter**: 트위터 닉네임
- **social: name:** 하단에 있는 네임, 기본작성자 바꾸기
- **social: email:** 이메일 넣기
- **social: links:** SNS 링크넣기
- **google_analytics**: 구글 애널리틱스 연결
- **google_analytics: pv:** 구글 애널리틱스 GA 연결
- **avatar**: 프로필 사진 넣기
- **disqus: shortname**: 닉네임 넣기
- **paginate**: 한 목록에 몇개의 글을 표시할 지


<br/>
<br/>

# 구조 설명
- **_config.yml** : 블로그의 기본 설정 파일입니다. 기본 환경세팅은 모두 여기에서 합니다. 
- **_data** : 왼쪽 사이드바와 포스트 하단의 공유하기 버튼등의 구성을 변경할 수 있습니다. 언어 설정에 따라 기본적으로 화면에 나오는 단어들을 변경할 수 있습니다. 
- **_include**: 사이드바, toc, 구글애널리틱스, footer, 댓글 등의 대부분의 모듈형으로 삽입되는 UI를 변경할 수 있습니다 
- **_layout** : 블로그 전역에 적용되는 기본 형식, 카테고리, 포스트 등에 적용되는 형식등을 변경할 수 있습니다. 
- **_posts** : 내가 작성한 블로그 글을 저장해 두는 곳입니다. 
- **_sass** : css 파일을 커스터마이징 할 수 있습니다. 
- **_site**: 로컬에서 실행할 때, 화면 UI를 구성하는 모든 내용이 들어 있습니다. 이곳의 내용을 변경하면 로컬에는 잘 반영되지만, git에는 올라가지 않습니다. 또한 다른 기본 디렉토리의 내용을 변경하고 빌드하게 되면 이곳의 내용이 바뀌게 됩니다.   
- **_tabs** : 왼쪽 사이드바의 기본 탭메뉴들에 대한 랜딩페이지가 들어 있습니다.  
- **assets** : css, img등이 있습니다. 포스팅에 들어갈 이미지는 assets/img 아래에 넣으면 됩니다.  
- **tools** : github에서 자동 배포를 위한 코드가 들어 있습니다. 이곳은 아예 건들지 맙시다  

<br/>

참고 (https://chirpy.cotes.page/posts/getting-started/)
