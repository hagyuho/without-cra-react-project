# CRA 없이 react + typescript 환경 구축하기

1. 폴더 생성

2. React 설정 
//package.json 생성
npm init -y
//react 라이브러리 설치
npm i react react-dom

3. react 기본 파일 생성 
- index.html
- index.tsx
- App.tsx

4. typescript 설정
// react 관련 typescript 라이브러리 설치
npm i -D typescript @types/react @types/react-dom
// tsconfig.json 파일 초기화 생성 (혹은 직접 만들어서 세팅)
tsc --init

5. babel 설정
// 브라우저 환경에서 es6문법이 동작되도록 es5로 변환
npm i -D babel-loader @babel/core @babel/preset-env
// 각각 react와 ts에 적용되도록 적용
npm i -D @babel/preset-react @babel/preset-typescript

- babel.config.js

6. webpack 설정
// webpack 자체 페키지
npm i -D webpack webpack-cli 
// hot-loading 가능한 개발 서버 및 머지 처리 
npm i -D webpack-dev-server webpack-merge
// html 파일 템플릿 생성 돕는 플러그인
npm i -D html-webpack-plugin 
// 타입스크립트 코드를 자바스크립트 코드로 변환
npm i -D ts-loader css-loader style-loader file-loader

- webpack.common.js
- webpack.dev.js
- webpack.prod.js

7. 명령어 설정

  "scripts": {
    "dev": "webpack-dev-server --config webpack.dev.js --open --hot",
    "build": "webpack --config webpack.prod.js",
    "start": "webpack --config webpack.dev.js",
    "tsc": "tsc"
  },

  8. ESlint, Prettier 설정
// ESLint
// Prettier
npm install eslint --save-dev
npm install prettier --save-dev --save-exact
npm install eslint-plugin-prettier eslint-config-prettier --save-dev