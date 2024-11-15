---
title: "GitHub Blog 댓글"
date: 2024-11-15 14:00:00 +0900
categories: [Programing, Blog]
tags: [blog, chirpy, giscus, github, jekyll, ruby]
pin: true
image: 
    path: https://www.devahoy.com/_next/image?url=%2Fstatic%2Fimages%2F2022%2Fgiscus.png&w=1080&q=75
---

> 게시글에 Comment 기능을 추가하는 방법을 소개합니다.
{: .prompt-info }

[`Chirpy Theme`]에서는 Comment 기능을 쉽게 적용할 수 있습니다.  

[`Disqus`]는 소셜 통합, 소셜 네트워킹, 사용자 프로필, 스팸 및 조정 도구, 분석, 이메일 알림, 모바일 댓글 달기와 같은 다양한 기능이 포함되어 있습니다.  
[`Utterances`]는 GitHub를 구동하는 CSS 툴킷인 Primer로 스타일링,  GitHub issue search API를 사용합니다.  
[`Giscus`]는 데이터베이스가 필요 없고, 모든 데이터는 GitHub Discussions에 저장됩니다.

3가지 중 `Giscus` 의 댓글 기능을 이용하려 합니다.


<br>


### 1. Giscus App을 리포지토리에 설치
[`Giscus App`]을 블로그 리포지토리에 설치합니다.
![GiscusApp](/assets/img/GiscusApp.PNG)


<br>


### 2. Github Discussion을 활성화
`Giscus App`을 설치한 리포지토리에서 **Settings**를 클릭하고 **Features** 영역에서 **Discussions**을 활성화합니다.  
![GiscusApp](/assets/img/Discussions.PNG)  

리포지토리에 **Discussions** 탭이 활성화된 것을 확인할 수 있습니다. 
![GiscusApp](/assets/img/DiscussionsTab.PNG)


<br>


### 3. Github Blog에 Giscus 추가
[`Giscus`]에서 설정을 하고 `Giscus 사용` 영역에 코드가 표시됩니다.
```yml
<script src="https://giscus.app/client.js"
        data-repo="[ENTER REPO HERE]"
        data-repo-id="[ENTER REPO ID HERE]"
        data-category="[ENTER CATEGORY NAME HERE]"
        data-category-id="[ENTER CATEGORY ID HERE]"
        data-mapping="pathname"
        data-strict="0"
        data-reactions-enabled="1"
        data-emit-metadata="0"
        data-input-position="bottom"
        data-theme="preferred_color_scheme"
        data-lang="ko"
        crossorigin="anonymous"
        async>
</script>
```
<br>

`_config.yml`{: .filepath} 파일에 사용자 설정에 맞게 작성된 위 코드를 기입합니다. 

```yml
comments:
  # Global switch for the post-comment system. Keeping it empty means disabled.
  provider: giscus # [disqus | utterances | giscus]
  # The provider options are as follows:
  disqus:
    shortname: # fill with the Disqus shortname. › https://help.disqus.com/en/articles/1717111-what-s-a-shortname
  # utterances settings › https://utteranc.es/
  utterances:
    repo: # <gh-username>/<repo>
    issue_term: # < url | pathname | title | ...>
  # Giscus options › https://giscus.app
  giscus:
    repo: # <gh-username>/<repo>
    repo_id: ""
    category: ""
    category_id: ""
    mapping: # optional, default to 'pathname'
    strict: # optional, default to '0'
    input_position: # optional, default to 'bottom'
    lang: # optional, default to the value of `site.lang`
    reactions_enabled: # optional, default to the value of `1`
```


<br>

### 4. Github Blog Giscus 확인
![Comment](/assets/img/Comment.PNG)

[`Giscus App`]: https://github.com/apps/giscus
[`Giscus`]: https://giscus.app/ko
[`Disqus`]: https://disqus.com/
[`Utterances`]: https://utteranc.es/
[`Chirpy Theme`]: https://chirpy.cotes.page/