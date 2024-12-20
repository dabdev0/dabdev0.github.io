---
title: "GitHub Blog 만들기"
date: 2024-11-04 21:00:00 +0900
categories: [Programing, Blog]
tags: [blog, chirpy, github, jekyll, ruby]
pin: true
image: 
    path: https://github.com/primer/brand/assets/19292210/0612e088-0394-421d-9266-2f6e1d12498e
---

> Jekyll의 Chirpy Theme를 활용하여 Github Blog를 개설하는 방법을 소개합니다.
{: .prompt-info }

[`Jekyll`]은 정적 사이트 생성기입니다. 마크업 언어로 작성된 텍스트를 레이아웃을 사용해 정적 웹사이트를 생성합니다. 사이트 URL 의 형식이나 어떤 데이터를 사이트에 표시할 것인지 등, 여러 동작을 조정할 수 있습니다.

다양한 테마가 있지만 디자인이 깔끔하며, 이용자와 정보가 많은 [`Chirpy`]를 선택했습니다.


<br>


## **시작하기에 앞서**
- [`Github`] 계정이 있어야 합니다.
- `Devkit` 이 포함된 [`Ruby`] 를 설치해야 합니다. (저는 3.1.4 버전을 사용했습니다.)
- [`VSCode`] 같은 소스 코드 편집기가 있으면 좋습니다.
- [`Github Desktop`] 을 사용하면 GUI 환경으로 쉽게 이용할 수 있습니다.


<br>


## **Chirpy Theme로 시작하기**
 Chirpy 공식 페이지에서 권장하는 사용방법은 두 가지가 있습니다.   
>[`chirpy-stater`] 는 업그레이드가 단순하며 최소한의 구성으로 사용 가능합니다. (특정 파일이 필요한 경우 불러와야 합니다.)

>[`fork-theme`] 는 기능이나 UI 디자인을 수정할 때는 편리하지만, 업그레이드 중에는 문제가 발생할 수 있습니다. Jekyll에 익숙하고 테마를 크게 수정할 계획이 아니라면 이 방법을 사용하지 마세요.

저는 Jekyll에 익숙지 않고, 최소한의 기능만 사용할 것이기에 [`chirpy-stater`] 를 사용하겠습니다.


<br>


### 1. 리포지토리 생성
[`chirpy-stater`] 에서 **Use this template** → **Create a new repository** 클릭하여 새 리포지토리 생성 페이지에서 **Owner** 에 사용자가 맞는지 확인하고 **Repository name** 에 **&lt;username&gt;.github.io** 입력하고 다른 사항은 변경하지 않고 **Create Repository** 을 클릭합니다.


<br>


### 2. 깃허브 데스크탑으로 불러오기
[`Github Desktop`] 에서 생성한 리포지토리를 선택하고 **Repository Clone** 합니다.


<br>


### 3. Site Configuration 수정
사용자에게 맞게 `_config.yml`{: .filepath} 파일을 수정합니다.

```yml
lang:                                    # ko or ko-KR
timezone: Asia/Seoul
title:                                   # sidebar title
tagline:                                 # sidebar subtitle
url: "https://username.github.io"        # github repository name

github:
  username:                              # github username

twitter:
  username:                              # 주석 처리했습니다.

social:
  name:                                  # social name
  email:                                 # email address
  links: 
    - https://github.com/username        # gitHub homepage

avatar: '/assets/img/~'                  # sidebar profile image
```


<br>


### 4. 사이드바 소셜 아이콘 수정
`_data/_contact.yml`{: .filepath} 파일을 수정하여 사이드바 하단 **소셜 아이콘**을 추가하거나 삭제할 수 있습니다.  
저는 인스타그램을 추가했습니다.

```yml
- type: instagram
  icon: "fa-brands fa-instagram"  # icons powered by <https://fontawesome.com/>
  url: "https://www.instagram.com/username" # instagram homepage
```


<br>


### 5. 로컬에서 블로그 실행
[`Ruby`] 로 사이트를 배포하기 전에 로컬에서 먼저 확인할 수 있습니다.
```shell
cd C:\username.github.io # 블로그 경로로 이동합니다.
bundle
```  
bundle 설치가 끝났다면 서버를 실행합니다.
```shell
bundle exec jekyll serve
```
**Ctrl+C** 로 종료할 수 있고, 파일을 수정했을 때 다시 실행해야 합니다.


<br>


### 6. 깃허브 커밋하기
먼저 [`Github`] 에 자신의 블로그 리포지토리로 가서 **Setting** → **Pages** 로 이동하고 **Build and deployment** 바로 밑에 **Source** 에서 **GitHub Actions** 로 변경합니다.

변경 후, [`Github Desktop`] 을 실행하면 추가, 삭제, 수정한 파일을 확인할 수 있습니다.  
**Summary (required)** 에 내용을 작성한 후, **Commit to main** 을 클릭하고 **Push origin** 을 클릭하면 됩니다.  


<br>


## References
* [`Github: chirpy-starter`]
* [`Github: jekyll-theme-chirpy`]
* [`Chirpy`]


[`Github: chirpy-starter`]: https://github.com/cotes2020/chirpy-starter
[`Github: jekyll-theme-chirpy`]: https://github.com/cotes2020/jekyll-theme-chirpy
[`fork-theme`]: https://github.com/cotes2020/jekyll-theme-chirpy
[`chirpy-stater`]: https://github.com/cotes2020/chirpy-starter
[`Github Desktop`]: https://desktop.github.com/download/
[`VSCode`]: https://code.visualstudio.com/
[`Github`]: https://github.com/
[`Ruby`]: https://www.ruby-lang.org/en/downloads/
[`Chirpy`]: https://chirpy.cotes.page/
[`Jekyll`]: https://jekyllrb.com/