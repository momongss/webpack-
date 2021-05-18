## HtmlWebpackPlugin

새로운 엔트리 포인트로 빌드를 하면, 새로운 output 이 생기고, output 을 불러오던 html 파일을 수정해야된다.
html 파일을 자동수정 플러그인.

- npm install --save-dev html-webpack-plugin

---

    const HtmlWebpackPlugin = require('html-webpack-plugin');
    ---------------------------------------------------------
    plugins: [new HtmlWebpackPlugin({})],
    => index.html 자동생성. (npm run build 시에만. npm start 로 열면 생성되지 않음.)

    plugins: [
        new HtmlWebPackPlugin({
            template: './input.html',
            filename: 'output.html'
        })
    ]
    => input, output 을 지정해줄 수 있다.

작동결과

- dist 폴더(output 경로) 안에 index.html 파일을 생성한다.
- 이전에 dist 폴더에 있던 index.html 파일은 대체되게 된다.

---

    + 빌드마다 dist 폴더 초기화되게 하기.
    output {
        clean: true,
    }
    이렇게 하면 이전 빌드시에 생겨 남아있을 수 있는 필요없는 파일을 없앨 수 있다.
