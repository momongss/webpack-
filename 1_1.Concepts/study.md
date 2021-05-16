## Entry

- 웹팩이 dependency graph 를 만들 시작점을 명시한다.

---

    module.exports = {
        entry: './path/to/my/entry/file.js',
    };

## Output

- 번들을 출력할 경로와 파일이름을 명시한다.

---

    const path = require('path');

    module.exports = {
        entry: './path/to/my/entry/file.js',
        output: {
            path: path.resolve(__dirname, 'dist'),
            filename: 'my-first-webpack.bundle.js',
        },
    };

## Loaders

- 브라우저는 JavaScript 와 JSON 파일 받에 알지 못한다.
- js 코드 안에 JS, json 파일이 아닌 다른 파일을 집어 넣을 수 있게 하는게 Loaders 의 기능이다.
- ex) import "./style.css";

---

    const path = require('path');

    module.exports = {
        output: {
            filename: 'my-first-webpack.bundle.js',
        },
        module: {
            rules: [{ test: /\.txt$/, use: 'raw-loader' }],
        },
    };

## Plugins

- ex) html 자동생성, 개발 서버, 핫인코딩 등.
- 아래 플러그인은 html 을 자동으로 생성해주는 플러그인이다.

---

    const HtmlWebpackPlugin = require('html-webpack-plugin');
    const webpack = require('webpack');

    module.exports = {
        module: {
            rules: [{ test: /\.txt$/, use: 'raw-loader' }],
        },
        plugins: [new HtmlWebpackPlugin({ template: './src/index.html' })],
    };

### html-webpack-plugin 사용법

1. src 폴더에 index.html 파일을 생성
2. 빌드
3. dist 폴더에 index.html 파일 생성됨.
   (별로 쓸모는 없는듯)

## Mode

- 개발, 프로덕션 각 모드에 최적화

---

## Browser Compatibility

- 웹팩은 ES5-compliant 한 모든 브라우저를 지원한다. (IE8 이하 제외.)

<br>
