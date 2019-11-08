---
title: Browserslist- caniuse-lite is outdated.
date: "2019-11-08"
description: Browserslist- caniuse-lite is outdated. Please run next command `yarn upgrade`.
---

## 에러 메시지

```bash
Browserslist- caniuse-lite is outdated. Please run next command `yarn upgrade`
/Users/{username}/{프로젝트 폴더}/{프로젝트 이름}/index.js: Unknown version 69 of firefox
at Function.select (/Users/{username}/.config/yarn/global/node_modules/@babel/preset-env/node_modules/browserslist/index.js:942:17)
```

에러 메시지대로 yarn upgrade 쳐도 해결이 안됐다.

## 검색/해결

https://github.com/postcss/autoprefixer/issues/1184

에러 메시지 맨 위쪽 보면 글로벌에 설치 된 yarn 안에 @babel/preset-env 이게 뭐 문제 있나보다.

그 폴더 위치로 이동해서, 거기서 업데이트하면 된다. ex) yarn upgrade

