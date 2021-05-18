## 기본 설정

1.  npm initialize (npm init)
2.  webpack, webpack-cli 설치 (npm i -D webpack, webpack-cli)
3.  기본 html, js 파일 생성
4.  **private 설정**

        package.json
        - "main": "index.js",
        + "private": true,

    -> 예기치 못한 배포를 막을 수 있다.
