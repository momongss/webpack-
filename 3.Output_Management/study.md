## HtmlWebpackPlugin

새로운 엔트리 포인트로 빌드를 하면, 새로운 output 이 생기고, output 을 불러오던 html 파일을 수정해야된다.
html 파일을 수정을 자동으로 수행해주는 플러그인.

- npm install --save-dev html-webpack-plugin

---

    const HtmlWebpackPlugin = require('html-webpack-plugin');
    ---------------------------------------------------------
    plugins: [
        new HtmlWebpackPlugin({
        title: 'Output Management',
        }),
    ],

작동결과

- dist 폴더(output 경로) 안에 index.html 파일을 생성한다.
- 이전에 dist 폴더에 있던 index.html 파일은 대체되게 된다.

---

    + 빌드마다 dist 폴더 초기화되게 하기.
    output {
        clean: true,
    }
    이렇게 하면 이전 빌드시에 생겨 남아있을 수 있는 필요없는 파일을 없앨 수 있다.

이렇게 하게되면 이제 html 파일은 개발시에 신경쓰지 않아도 될 것이다. 웹팩이 추구하는게 그런 것 같다.
