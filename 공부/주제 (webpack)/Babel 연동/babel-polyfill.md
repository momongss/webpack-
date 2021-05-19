https://tech.kakao.com/2020/12/01/frontend-growth-02/
https://webpack.js.org/loaders/babel-loader/

## core-js

바벨은 ES6+ 코드를 ES5- 로 트랜스파일 한다. <Br>
그런데 ES6+ 에 완전히 새로 추가되어 ES5- 로 변환할 수 없는 경우는 어떻게 할까?. <br>
이 경우 구문 변환 뿐 아니라 **객체를 정의하는 browser polyfill** 을 추가해줘야 한다.

- npm i -D @babel/plugin-transform-runtime <br>

---
