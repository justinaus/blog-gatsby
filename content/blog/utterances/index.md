---
title: utterances
date: "2019-10-25"
description: gatsby-cli로 만든 블로그에 댓글 기능 적용.
---

### gatsby-cli로 만든 블로그에 댓글 기능 적용.

## 원리

github issue api를 이용.
자세한 내용은 [https://utteranc.es](https://utteranc.es) 참고.


## 적용

1. 댓글 기능을 연결할 깃헙 repository에 [utterances app](https://github.com/apps/utterances) 설치 (리포는 public 이어야 한다)
1. 블로그 템플릿에 아래 스크립트 태그를 추가한다.
```js
<script src="https://utteranc.es/client.js"
        repo="[ENTER REPO HERE]"
        issue-term="pathname"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>
```

나의 경우는
```js
repo="justinaus/blog-gatsby"
```

## troubleshooting
gatsby-cli를 이용해서 만든 내 블로그는
템플릿이 React Component로 만들어져 있는데, 여기에 스크립트 태그를 넣는 방법을 몰랐다.
[검색](https://github.com/utterance/utterances/issues/161) 해서 알았다.

```js
import React, {Component} from "react";

export default class Comments extends Component {

  componentDidMount () {
      let script = document.createElement("script");
      let anchor = document.getElementById("inject-comments-for-uterances");
      script.setAttribute("src", "https://utteranc.es/client.js");
      script.setAttribute("crossorigin","anonymous");
      script.setAttribute("async", true);
      script.setAttribute("repo", "[ENTER REPO HERE]");
      script.setAttribute("issue-term", "pathname");
      script.setAttribute( "theme", "github-light");
      anchor.appendChild(script);
  }

  render() {
    return (
        <div id="inject-comments-for-uterances"></div>
    );
  }
}
```

## 기타
[utterances-react](https://www.npmjs.com/package/utterances-react) 라는 것도 있다고 한다.
써보진 않았다.





