---
title: Prettier
date: "2019-12-04"
description: Hello Prettier.
---

## Prettier

코드 스타일 정리 도구.


## 필요성

- 혼자 개발할 때는 잘 모르겠는데, 코드 스타일에 ~~예민러~~민감한 동료와 함께 개발할 때 필요.
- 대세를 따른다.


## 내가 할 방식

vscode에서 글로벌하게 설정할 수도 있지만,

지금까지 고민한 바로는 코드 스타일 설정 파일이 프로젝트 내에 있는 게 좋은 것 같다.
(vue-cli 처음 프로젝트 생성할 때 manually로 선택할 수도 있다. (eslint + prettier))


## get started 

1. Eslint extension 설치
    - vscode - 확장 >  ESLint 설치

2. Prettier extension 설치
    - vscode - 확장 >  Prettier - Code formatter 설치


3. 프로젝트에 Prettier 설치

```bash
yarn add @vue/eslint-config-prettier eslint-plugin-prettier --dev
```


4. .eslintrc.js 파일 생성, package.json 파일에서 eslintConfig 분리

```js
// .eslintrc.js
module.exports = {
  root: true,
  env: {
    node: true,
  },
  extends: ['plugin:vue/essential', '@vue/prettier'],
  rules: {
    'no-console': process.env.NODE_ENV === 'production' ? 'error' : 'off',
    'no-debugger': process.env.NODE_ENV === 'production' ? 'error' : 'off',
  },
  parserOptions: {
    parser: 'babel-eslint',
  },
};
```


5. prettierrc.json 파일 생성

```json
{
  "singleQuote": true,
  "semi": true,
  "useTabs": false,
  "tabWidth": 2,
  "trailingComma": "all",
  "printWidth": 80
}
```


6. 프로젝트 내에 설정 파일 생성
    - 프로젝트 루트 위치에 .vscode 폴더 생성
    - 그 안에 settings.json 파일 생성
```js
// settings.json
{
  "editor.formatOnSave": true,
  "eslint.autoFixOnSave": true,
  "eslint.alwaysShowStatus": true,
  "eslint.validate": [
    {
      "language": "vue",
      "autoFix": true
    },
    {
      "language": "javascript",
      "autoFix": true
    },
    {
      "language": "javascriptreact",
      "autoFix": true
    }
  ]
}

```


~~개별 파일 수정~~

~~cmd + shift + P -> Format Document~~




## 🔗 참고  
- [Prettier Options](https://prettier.io/docs/en/options.html)

## 틀린 부분이 있다면 댓글로 알려주세요. 
