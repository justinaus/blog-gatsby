---
title: Vue 컴포넌트 패키지 npm에 배포
date: "2019-10-14"
description: Vue 컴포넌트 패키지 npm에 배포.
---

## npm에 배포할 vue 프로젝트

### 생성
```bash
vue create my-example
```
### 컴포넌트 구현
그냥 구현하면 됨.

#### package.json 수정

자세한 내용은 [여기](https://medium.com/justfrontendthings/how-to-create-and-publish-your-own-vuejs-component-library-on-npm-using-vue-cli-28e60943eed3) 참고

컴포넌트에 scss 사용할 경우 node-sass, sass-loader 설치.

```json
{
  "name": "@justinaus/vue-components",
  "version": "0.1.10",
  "private": false,
  "scripts": {
    "build-bundle": "vue-cli-service build --target lib --name justinaus ./src/index.js",
  },
  "devDependencies": {
    "node-sass": "^4.12.0",
    "sass-loader": "^8.0.0",
  },
  "main": "./dist/justinaus.common.js",
  "files": [
    "dist/*",
    "src/*",
    "public/*",
    "*.json",
    "*.js"
  ]
}
```

#### src/index.js (entry file)

```js
import Banner from './components/Banner.vue'
import Input from './components/Input.vue'

const components = [
  Banner,
  Input
]

export {
  Banner,
  Input
}

export const Plugin = {
  install: function(Vue) {
    components.forEach( component => {
      Vue.component( component.name, component );
    } );
  }
}

export default {
  Plugin,
  Banner,
  Input
};
```

## npm에 배포

#### npm 계정 생성/로그인/확인
```bash
npm adduser
npm login
npm whoami
```

#### 빌드
```bash
npm run build-bundle
```
dist 폴더 확인

#### 배포

npm publish --access=public

## troubleshooting

### css
npm 정상 배포 되었으나, 
인스톨해서 컴포넌트를 사용하니 css에 대한 내용이 빠져 있었다.

결론: vue.config.js 파일 생성.
아래 css 내용 입력. ([링크](https://cli.vuejs.org/guide/build-targets.html#library))

```js
module.exports = {
  css: { extract: false }
}
```

### version
package.json - version 꼭 올려줘야 함.

## npm에 배포한 패키지 사용

#### 설치
```bash
npm install @justinaus/vue-components
```

#### 사용
```js
import { Banner } from '@justinaus/vue-components'

// 그냥 사용하면 됨.
```

## 🔗 참고  
- https://medium.com/justfrontendthings/how-to-create-and-publish-your-own-vuejs-component-library-on-npm-using-vue-cli-28e60943eed3