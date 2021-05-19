# webpack

## 개요

- 웹팩은 자바스크립트 모듈 번들러
- JS 파일 뿐만 아니라 CSS, image, font 등의 에셋들도 import 문으로 불러올 수 있다.
  <br>(브라우저가 알지 못하는 자산들을 브라우저가 알아보는 형태로 변환해줌.)

## 주제

- [에셋 사용하기 (img, font, css import)](https://github.com/momongss/webpack-/blob/main/%EA%B3%B5%EB%B6%80/Guides/2.Asset_Management/study.md)

- [babel 연동](<https://github.com/momongss/webpack-/blob/main/%EA%B3%B5%EB%B6%80/%EC%A3%BC%EC%A0%9C%20(webpack)/Babel%20%EC%97%B0%EB%8F%99/study.md>)

  - [기본 트랜스파일](<https://github.com/momongss/webpack-/blob/main/%EA%B3%B5%EB%B6%80/%EC%A3%BC%EC%A0%9C%20(webpack)/Babel%20%EC%97%B0%EB%8F%99/%EA%B8%B0%EB%B3%B8%ED%8A%B8%EB%9E%9C%EC%8A%A4%ED%8C%8C%EC%9D%BC%EB%A7%81.md>)

  - [polyfill](<https://github.com/momongss/webpack-/blob/main/%EA%B3%B5%EB%B6%80/%EC%A3%BC%EC%A0%9C%20(webpack)/Babel%20%EC%97%B0%EB%8F%99/babel-polyfill.md>)

- 빌드 자동화

  - [방법1. (watch mode).md](<https://github.com/momongss/webpack-/blob/main/%EA%B3%B5%EB%B6%80/%EC%A3%BC%EC%A0%9C%20(webpack)/%EB%B9%8C%EB%93%9C%20%EC%9E%90%EB%8F%99%ED%99%94/%EB%B0%A9%EB%B2%951.%20(watch%20mode).md>) (추천)
  - [방법2. (webpack-dev-server).md](<https://github.com/momongss/webpack-/blob/main/%EA%B3%B5%EB%B6%80/%EC%A3%BC%EC%A0%9C%20(webpack)/%EB%B9%8C%EB%93%9C%20%EC%9E%90%EB%8F%99%ED%99%94/%EB%B0%A9%EB%B2%952.%20(webpack-dev-server).md>)
  - [방법3. (webpack-dev-middleware).md](<https://github.com/momongss/webpack-/blob/main/%EA%B3%B5%EB%B6%80/%EC%A3%BC%EC%A0%9C%20(webpack)/%EB%B9%8C%EB%93%9C%20%EC%9E%90%EB%8F%99%ED%99%94/%EB%B0%A9%EB%B2%953.%20(webpack-dev-middleware).md>)

- SASS 사용하기

  - [방법1. (styled component).md](<https://github.com/momongss/webpack-/blob/main/%EA%B3%B5%EB%B6%80/%EC%A3%BC%EC%A0%9C%20(webpack)/Sass%20%EC%82%AC%EC%9A%A9%ED%95%98%EA%B8%B0/%EB%B0%A9%EB%B2%951.%20(styled%20component).md>)
  - [방법2. (vscode extension).md](<https://github.com/momongss/webpack-/blob/main/%EA%B3%B5%EB%B6%80/%EC%A3%BC%EC%A0%9C%20(webpack)/Sass%20%EC%82%AC%EC%9A%A9%ED%95%98%EA%B8%B0/%EB%B0%A9%EB%B2%952.%20(vscode%20extension).md>)

- [React 설정](<https://github.com/momongss/webpack-/blob/main/%EA%B3%B5%EB%B6%80/%EC%A3%BC%EC%A0%9C%20(webpack)/React%20%EC%84%A4%EC%A0%95/%EB%B0%A9%EB%B2%95.md>)

- [여러 개 entry point (none SPA)](<https://github.com/momongss/webpack-/blob/main/%EA%B3%B5%EB%B6%80/%EC%A3%BC%EC%A0%9C%20(webpack)/%EC%97%AC%EB%9F%AC%EA%B0%9C%EC%9D%98%20entryPoint/%EB%B0%A9%EB%B2%95.md>)

<br>

## 공식문서 가이드

1. [Getting_Started](https://github.com/momongss/webpack-/blob/main/%EA%B3%B5%EB%B6%80/Guides/1.Getting_Started/study.md)
2. [Asset_Management](https://github.com/momongss/webpack-/blob/main/%EA%B3%B5%EB%B6%80/Guides/2.Asset_Management/study.md)
3. [Output_Management](https://github.com/momongss/webpack-/blob/main/%EA%B3%B5%EB%B6%80/Guides/3.Output_Management/study.md)
4. [Development](https://github.com/momongss/webpack-/tree/main/%EA%B3%B5%EB%B6%80/Guides/4.Development)

<br>

# Babel

## 개요

- babel은 자바스크립트 컴파일러
- 2가지 주요 기능 수행
  1. 크로스 브라우징 이슈 해결
  2. JSX 같은 JS 프레임워크만의 문법을 js 로 컴파일
  - 크로스 브라우징을 위한 처리는 배포 직전에 1번만,
  - JS 프레임워크 컴파일은 개발 중에 처리할 수 있도록 <BR>
    환경을 설정하는게 더 효율적이고, 덜 헷갈리는 방법이라고 생각한다.

## 주제

- [크로스브라우징 처리(IE 등 지원)](<https://github.com/momongss/webpack-/blob/main/%EA%B3%B5%EB%B6%80/%EC%A3%BC%EC%A0%9C%20(babel)/%ED%81%AC%EB%A1%9C%EC%8A%A4%EB%B8%8C%EB%9D%BC%EC%9A%B0%EC%A7%95.md>) (.babelrc 에 설정해준다.)
- JS 프레임워크 문법 컴파일
  (webpack.config.js 에 설정해준다.)
  - [React](<https://github.com/momongss/webpack-/blob/main/%EA%B3%B5%EB%B6%80/%EC%A3%BC%EC%A0%9C%20(webpack)/React%20%EC%84%A4%EC%A0%95/%EB%B0%A9%EB%B2%95.md>)
